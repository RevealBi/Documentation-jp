# ダッシュボードの読み込み

アプリケーションに埋め込まれた `RevealView` コントロールに既存の Reveal ダッシュボードを表示する場合は、4 つのオプションから選択できます。
- ファイル パスからダッシュボードを読み込み
- ファイル ストリームからダッシュボードを読み込み
- 埋め込まれたリソースからダッシュボードを読み込み
- json からダッシュボードを読み込み

ダッシュボードはサーバー上にあります。クライアント アプリケーションは `$.ig.RVDashboard.loadDashboard` メソッドを呼び出し、読み込むダッシュボードの名前を渡します。ダッシュボードのリクエストがサーバーに送信され、サーバーはリクエストされたダッシュボードでクライアントに応答します。クライアントは、サーバーの応答で提供されたダッシュボードを取得し、`RevealView.dashboard` プロパティを設定します。

**.rdash** ダッシュボード ファイルは次の方法で作成できます:
- ダッシュボードを [Reveal BI Web サイト](https://app.revealbi.io/)から .rdash ファイルとしてエクスポートします。
- ダッシュボードをネイティブの Reveal アプリケーションの 1 つから .rdash ファイルとしてエクスポートします。
- Reveal SDK を使用してアプリケーションで作成されたダッシュボードを保存またはエクスポートします。
- [サンプル ダッシュボード](https://github.com/RevealBi/sdk-samples-wpf/raw/master/SampleDashboards.zip)のダウンロード

## ファイル パスから読み込み

デフォルトでは、Reveal SDK は規則を使用して、ファイル パスからダッシュボードを読み込みます。具体的には、Reveal SDK は、サーバーの **Dashboards** フォルダーでダッシュボードを検索します。このフォルダーの作成方法については、[サーバーの設定](getting-started-server.md#step-3---create-the-dashboards-folder)トピックを参照してください。

1 - In the ASP.NET Core Web Api server application, create a folder named **Dashboards** and place a dashboard file within the folder.

![](images/loading-dashboards-default-directory.jpg)

2 - In the client application, call the `$.ig.RevealSdkSettings.setBaseUrl` method and pass in your server URL. When debugging, the server URL will be `https://localhost` followed by a port number. For example:

```javascript
$.ig.RevealSdkSettings.setBaseUrl("https://localhost:/7111");   
```

> [!IMPORTANT]
> サーバーがクライアント アプリケーションとは異なる URL で実行されている場合は、`$。ig.RevealSdkSettings.setBaseUrl` を呼び出す必要があります。サーバー アプリケーションとクライアント アプリケーションの両方が同じ URL で実行されている場合、このメソッドは必要ありません。このメソッドを呼び出す必要があるのは 1 回だけです。

3 - Make a call to the `$.ig.RVDashboard.loadDashboard` method and pass the name of the dashboard file without the .rdash extension. This method has a callback which will provide the dashboard being requested from the server. Once you have received the dashboard from the callback, get an instance of the `$.ig.RevealView` and set the `RevealView.dashboard` property to the dashboard in the response.

```javascript
$.ig.RVDashboard.loadDashboard("Sales", (dashboard) => {
    var revealView = new $.ig.RevealView("#revealView");
    revealView.dashboard = dashboard;
});
```

> [!NOTE]
> このサンプルのソース コードは [GitHub](https://github.com/RevealBi/sdk-samples-javascript/tree/main/LoadingDashboards) にあります。

## カスタム ファイル パスから読み込み

デフォルトの **Dashboards** ファイル ディレクトリがアプリケーションのオプションではない場合は、代わりにダッシュボードを読み込むためのカスタム ファイル パスを指定できます。

1 - In the ASP.NET Core Web API server application, create a new class that implements the `IRVDashboardProvider` interface. Add the logic to load dashboards from your custom file directory in the `GetDashboardAsync` method. In this example, the ASP.NET Core Web API server application uses a folder named **MyDashboardsFolder** to store all dashboards.

```cs
public class DashboardProvider : IRVDashboardProvider
{
    public Task<Dashboard> GetDashboardAsync(IRVUserContext userContext, string dashboardId)
    {
        var filePath = Path.Combine(Environment.CurrentDirectory, $"MyDashboardsFolder/{dashboardId}.rdash");
        var dashboard = new Dashboard(filePath);
        return Task.FromResult(dashboard);
    }

    public Task SaveDashboardAsync(IRVUserContext userContext, string dashboardId, Dashboard dashboard)
    {
        throw new NotImplementedException();
    }
}
```

2 - Update the `AddReveal` method in the `Program.cs` file to add the `IRVDashboardProvider` you just created to the `RevealSetupBuilder` using the `RevealSetupBuilder.AddDashboardProvider` method.

```cs
builder.Services.AddControllers().AddReveal( builder =>
{
    builder.AddDashboardProvider<DashboardProvider>();
});
```

3 - In the client application, call the `$.ig.RevealSdkSettings.setBaseUrl` method and pass in your server URL. When debugging, the server URL will be `https://localhost` followed by a port number. For example:

```javascript
$.ig.RevealSdkSettings.setBaseUrl("https://localhost:/7111");   
```

> [!IMPORTANT]
> サーバーがクライアント アプリケーションとは異なる URL で実行されている場合は、`$。ig.RevealSdkSettings.setBaseUrl` を呼び出す必要があります。サーバー アプリケーションとクライアント アプリケーションの両方が同じ URL で実行されている場合、このメソッドは必要ありません。このメソッドを呼び出す必要があるのは 1 回だけです。

4 - Make a call to the `$.ig.RVDashboard.loadDashboard` method and pass the name of the dashboard file without the .rdash extension. This method has a callback which will provide the dashboard being requested from the server. Once you have received the dashboard from the callback, get an instance of the `$.ig.RevealView` and set the `RevealView.dashboard` property to the dashboard in the response.

```javascript
$.ig.RVDashboard.loadDashboard("Sales", (dashboard) => {
    var revealView = new $.ig.RevealView("#revealView");
    revealView.dashboard = dashboard;
});
```

> [!NOTE]
> このサンプルのソース コードは [GitHub](https://github.com/RevealBi/sdk-samples-javascript/tree/main/LoadingDashboards-File).

## ファイル ストリームから読み込み

ファイル ストリームからの Reveal ダッシュボードの読み込みは、ファイル パスからのダッシュボードの読み込みと非常によく似ています。この場合、ダッシュボード ファイルのファイル パスを取得したら `Dashboard` オブジェクト インスタンスを作成する前に、それを `FileStream` に読み込みます。

1 - In the ASP.NET Core Web API server application, create a new class that implements the `IRVDashboardProvider` interface. Add the logic to load dashboards from your custom file directory in the `GetDashboardAsync` method. In this example, we are using the `File.OpenRead` method to load the dashboard files into a file stream. We then create a new `Dashboard` object by passing the file stream as a constructor argument and return the newly created `Dashboard` instance.

```cs
public class DashboardProvider : IRVDashboardProvider
{
    public Task<Dashboard> GetDashboardAsync(IRVUserContext userContext, string dashboardId)
    {
        var filePath = Path.Combine(Environment.CurrentDirectory, $"Dashboards/{dashboardId}.rdash");
        using (var stream = File.OpenRead(filePath))
        {
            var dashboard = new Dashboard(stream);
            return Task.FromResult(dashboard);
        }
    }

    public Task SaveDashboardAsync(IRVUserContext userContext, string dashboardId, Dashboard dashboard)
    {
        throw new NotImplementedException();
    }
}
```

2 - Update the `AddReveal` method in the `Program.cs` file to add the `IRVDashboardProvider` you just created to the `RevealSetupBuilder` using the `RevealSetupBuilder.AddDashboardProvider` method.

```cs
builder.Services.AddControllers().AddReveal( builder =>
{
    builder.AddDashboardProvider<DashboardProvider>();
});
```

3 - In the client application, call the `$.ig.RevealSdkSettings.setBaseUrl` method and pass in your server URL. When debugging, the server URL will be `https://localhost` followed by a port number. For example:

```javascript
$.ig.RevealSdkSettings.setBaseUrl("https://localhost:/7111");   
```

> [!IMPORTANT]
> サーバーがクライアント アプリケーションとは異なる URL で実行されている場合は、`$。ig.RevealSdkSettings.setBaseUrl` を呼び出す必要があります。サーバー アプリケーションとクライアント アプリケーションの両方が同じ URL で実行されている場合、このメソッドは必要ありません。このメソッドを呼び出す必要があるのは 1 回だけです。

4 - Make a call to the `$.ig.RVDashboard.loadDashboard` method and pass the name of the dashboard file without the .rdash extension. This method has a callback which will provide the dashboard being requested from the server. Once you have received the dashboard from the callback, get an instance of the `$.ig.RevealView` and set the `RevealView.dashboard` property to the dashboard in the response.

```javascript
$.ig.RVDashboard.loadDashboard("Sales", (dashboard) => {
    var revealView = new $.ig.RevealView("#revealView");
    revealView.dashboard = dashboard;
});
```

> [!NOTE]
> このサンプルのソース コードは [GitHub](https://github.com/RevealBi/sdk-samples-javascript/tree/main/LoadingDashboards-FileStream).

## リソースから読み込み

アプリケーションでファイルを配布するためのもう 1 つのオプションは、ファイルをリソースとしてサーバー アプリケーションに埋め込むことです。

1 - To embed a Reveal dashboard **.rdash** file as a resource in your server application, open the Properties for the dashboard file in Visual Studio, and set the **Build Action** of the .rdash file to **EmbeddedResource**.

![](images/loading-dashboard-as-resource.jpg)

ダッシュボードが **EmbeddedResource** として定義されたら、`Assembly.GetManifestResourceStream` メソッドを使用してダッシュボードを読み込むことができます。このメソッドは、`Dashboard` オブジェクトの作成に使用できる `Stream` オブジェクトを返します。`Assembly.GetManifestResourceStream` メソッドで指定するリソースの`名前`には、.rdash ファイルの`名前空間`とファイル名が含まれている必要があることに注意してください。

2 - In the ASP.NET Core Web API server application, create a new class that implements the `IRVDashboardProvider` interface. Add the logic to load dashboards from the embedded resources in the `GetDashboardAsync` method. In this example, the name of the resource starts with the application root namespace **RevealSdk.Server**, plus **Dashboards** which is the directory that contains the dashboard files, followed by the name of the .rdash file which is built using the `dashboardId` parameter.

```cs
public class DashboardProvider : IRVDashboardProvider
{
    public Task<Dashboard> GetDashboardAsync(IRVUserContext userContext, string dashboardId)
    {
        var resource = Assembly.GetExecutingAssembly().GetManifestResourceStream($"RevealSdk.Server.Dashboards.{dashboardId}.rdash");
        using (resource)
        {
            var dashboard = new Dashboard(resource);
            return Task.FromResult(dashboard);
        }
    }

    public Task SaveDashboardAsync(IRVUserContext userContext, string dashboardId, Dashboard dashboard)
    {
        throw new NotImplementedException();
    }
}
```

3 - Update the `AddReveal` method in the `Program.cs` file to add the `IRVDashboardProvider` you just created to the `RevealSetupBuilder` using the `RevealSetupBuilder.AddDashboardProvider` method.

```cs
builder.Services.AddControllers().AddReveal( builder =>
{
    builder.AddDashboardProvider<DashboardProvider>();
});
```

4 - In the client application, call the `$.ig.RevealSdkSettings.setBaseUrl` method and pass in your server URL. When debugging, the server URL will be `https://localhost` followed by a port number. For example:

```javascript
$.ig.RevealSdkSettings.setBaseUrl("https://localhost:/7111");   
```

> [!IMPORTANT]
> サーバーがクライアント アプリケーションとは異なる URL で実行されている場合は、`$。ig.RevealSdkSettings.setBaseUrl` を呼び出す必要があります。サーバー アプリケーションとクライアント アプリケーションの両方が同じ URL で実行されている場合、このメソッドは必要ありません。このメソッドを呼び出す必要があるのは 1 回だけです。

5 - Make a call to the `$.ig.RVDashboard.loadDashboard` method and pass the name of the dashboard file without the .rdash extension. This method has a callback which will provide the dashboard being requested from the server. Once you have received the dashboard from the callback, get an instance of the `$.ig.RevealView` and set the `RevealView.dashboard` property to the dashboard in the response.

```javascript
$.ig.RVDashboard.loadDashboard("Sales", (dashboard) => {
    var revealView = new $.ig.RevealView("#revealView");
    revealView.dashboard = dashboard;
});
```

> [!NOTE]
> このサンプルのソース コードは [GitHub](https://github.com/RevealBi/sdk-samples-javascript/tree/main/LoadingDashboards-Resource).

## JSON から読み込み

上級ユーザー、または Reveal ダッシュボードを .rdash ファイルではなく .json ファイルにシリアル化するユーザーの場合、サーバー アプリケーションで `Dashboard.LoadFromJsonAsync` メソッドを使用してこれらの JSON ベースのファイルを読み込むことができます。

1 - In the ASP.NET Core Web API server application, create a new class that implements the `IRVDashboardProvider` interface. Add the logic to load dashboards from your json dashboard files in the `GetDashboardAsync` method. In this example, we are using the `File.ReadAllText` method to load the dashboard files into a JSON string. We then create a new `Dashboard` object by passing the JSON string as an argument to the `Dashboard.FromJsonString` method and return the newly created `Dashboard` instance.

```cs
public class DashboardProvider : IRVDashboardProvider
{
    public Task<Dashboard> GetDashboardAsync(IRVUserContext userContext, string dashboardId)
    {
        var filePath = Path.Combine(Environment.CurrentDirectory, $"Dashboards/{dashboardId}.json");
        var json = File.ReadAllText(filePath);
        var dashboard = Dashboard.FromJsonString(json);
        return Task.FromResult(dashboard);
    }

    public Task SaveDashboardAsync(IRVUserContext userContext, string dashboardId, Dashboard dashboard)
    {
        throw new NotImplementedException();
    }
}
```

> [!WARNING]
> JSON にシリアル化された後に Reveal ダッシュボードのコンテンツを操作または変更すると、ダッシュボードの完全性が損なわれ、ダッシュボードのコンテンツに取り返しのつかない損傷が生じる可能性があります。これにより、エラーやダッシュボードの読み込みの失敗により、アプリケーションで実行時に例外がスローされる可能性があります。

2 - Update the `AddReveal` method in the `Program.cs` file to add the `IRVDashboardProvider` you just created to the `RevealSetupBuilder` using the `RevealSetupBuilder.AddDashboardProvider` method.

```cs
builder.Services.AddControllers().AddReveal( builder =>
{
    builder.AddDashboardProvider<DashboardProvider>();
});
```

3 - In the client application, call the `$.ig.RevealSdkSettings.setBaseUrl` method and pass in your server URL. When debugging, the server URL will be `https://localhost` followed by a port number. For example:

```javascript
$.ig.RevealSdkSettings.setBaseUrl("https://localhost:/7111");   
```

> [!IMPORTANT]
> サーバーがクライアント アプリケーションとは異なる URL で実行されている場合は、`$。ig.RevealSdkSettings.setBaseUrl` を呼び出す必要があります。サーバー アプリケーションとクライアント アプリケーションの両方が同じ URL で実行されている場合、このメソッドは必要ありません。このメソッドを呼び出す必要があるのは 1 回だけです。

4 - Make a call to the `$.ig.RVDashboard.loadDashboard` method and pass the name of the dashboard file without the .rdash extension. This method has a callback which will provide the dashboard being requested from the server. Once you have received the dashboard from the callback, get an instance of the `$.ig.RevealView` and set the `RevealView.dashboard` property to the dashboard in the response.

```javascript
$.ig.RVDashboard.loadDashboard("Sales", (dashboard) => {
    var revealView = new $.ig.RevealView("#revealView");
    revealView.dashboard = dashboard;
});
```

> [!NOTE]
> このサンプルのソース コードは [GitHub](https://github.com/RevealBi/sdk-samples-javascript/tree/main/LoadingDashboards-Json).
