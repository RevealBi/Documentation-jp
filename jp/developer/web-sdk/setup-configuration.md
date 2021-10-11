# セットアップと構成 (Web)

## 前提条件

The Reveal Server SDK requires .NET Core 3.1 or newer.

## セットアップと構成の概要 

以下は、Reveal Web Server SDK 設定の手順です。

1.  [**Reveal SDK のインストール**](#installing-reveal-sdk')

2.  [**サーバー コンテキストを定義**](#defining-server-context)

3.  [**サーバー SDK を初期化**](#initializing-server-sdk)

4.  [**サーバー側画像生成の有効化**](#server-side-image-export).

<a name='installing-reveal-sdk'></a>

### 1\. アセンブリと依存関係パッケージの準備

You need to run the Reveal Sdk installer on you r machine.


After that, you should be able to find a new NuGet
package source added to your **nuget.config** called _Infragistics
(Local)_ that points to “%public%\\Documents\\Infragistics\\NuGet”.

<img src="images/addingNugetPackage_web.png" alt="addingNugetPackage_web" class="responsive-img"/>

Infragistics (Local) フィードがインストーラーによって正しく設定されていることを確認後:

  - **Reveal.Sdk.Web.AspNetCore(.Trial)** NuGet パッケージを プロジェクトにインストールします。
  - NuGet パッケージ参照を System.Data.SQLite バージョン 1.0.111 以降に追加します。

Trial nuget package is available on nuget.org - [**Reveal.Sdk.Web.AspNetCore.Trial**](https://www.nuget.org/packages/Reveal.Sdk.Web.AspNetCore.Trial/)

ビルドに問題がある場合は、この[**リンク**](#sqlite-fix)を参照してください。

<a name='defining-server-context'></a>

<a name='defining-server-context'></a>

### 2\. DashboardProvider を定義する

After installing hte nuget package, you need to create a class that
implements
**IRVDashboardProvider** interface. The class handles loading and saving dashboards.

```csharp
    using Reveal.Sdk;
    public class DashboardProvider : IRVDashboardProvider
    {
        private string _ext = ".rdash";
        readonly string _dashboardsDirectoryPath;

        public DashboardProvider(string dashboardsDirectoryPath = "Dashboards")
        {
            _dashboardsDirectoryPath = dashboardsDirectoryPath;
        }
        public Task<Dashboard> GetDashboardAsync(IRVUserContext userContext, string dashboardId)
        {
            var fileToLoad = Directory.EnumerateFiles(_dashboardsDirectoryPath)
                                        .Where(f => f == dashboardId || f == dashboardId + _ext)
                                        .FirstOrDefault(f => f.EndsWith(_ext));
            if (fileToLoad != null)
            {
                return Task.FromResult(new Dashboard(fileToLoad));
            }
            throw new ArgumentException($"No rdash file with name \"{dashboardId}\" was found in the dashboards folder:{_dashboardsDirectoryPath}.");
        }

        public Task SaveDashboardAsync(IRVUserContext userContext, string dashboardId, Dashboard dashboard)
        {
            string dashboardFileName = dashboardId.Contains(_ext) ? dashboardId : dashboardId + _ext;

            return dashboard.SaveToFileAsync(Path.Combine(_dashboardsDirectoryPath, dashboardFileName));
        }
    }
```

The code above implements a simple file system based provider.
It accepts an argument in its constructor that should specify the directory that dashboards would get loaded/saved from/to.
Also it's forgiving in case you miss or don't want to specify file extension.

<a name='initializing-server-sdk'></a>

In the **Startup.cs**, in the **ConfigureServices** method of the
application you'll need to add to the services some of the AspNetCore services that returns an IMvcBuilder interface.
The most used ones are AddMvc, AddControllersWithViews and Add Controllers. So after you add one of these services
you need to call .AddReveal on top of it. AddReveal is an extension method extending IMvcBuilder.

AddReveal extension method is located in the Reveal.Sdk namespace so make sure you add a using for it in your Startup.cs.

AddReveal is your way to register reveal server component and provide settings to. Look at the snippet bellow
to see a basic call registering the DashboardProvider we defined in the previous step:

```csharp
services
    .AddMvc()
        .AddReveal(builder =>
        {
            builder
              .AddDashboardProvider<AddDashboardProvider>()
              .AddSettings(settings =>
              {
                  settings.LocalFileStoragePath = "Data";
                  settings.DataCachePath = settings.CachePath = @"C:\Temp\Reveal\Cache";
              });
        });
```

In the snippet above we're registering the DashboardProvider class.\
Also we specify LocalFileStoragePath - path for static data source files like Excel or CSV will be located and setting default caching locations to be used.

As you might have noted we're registering the type and not a particular instance. That's because the type will be registered in the AspNetCore Di container.
Which gives you the flexibility to inject any other services you might be using into the implementation of the DashboarProvider and in other Reveal provider.
You are free to register the instance if you prefer so - just us the other overload AddDashboardProvider method like:
```csharp
builder.AddDashboardProvider(new DashboardProvider())
```

<a name='server-side-image-export'></a>

### 4\. サーバー側画像生成の有効化

**画像エクスポート**機能 (プログラム上およびユーザー操作の両方により) を使用するには、以下の手順を実行する必要があります。

1.  **\<InstallationDirectory\>\\SDK\\Web\\JS\\Server** から以下の 3 つのファイルを取得します。

      - package.json
      - packages-lock.json
      - screenshoteer.js

2.  ファイルをプロジェクトのルート レベル (「wwwroot」の親フォルダー) にコピーします。

3.  **npm** (Node.js のパッケージ マネージャー) がインストールされていることを確認してください。

画像エクスポート機能が必要ない場合は、ファイルをプロジェクトにコピーする必要はありません。ただし、プロジェクトをビルドする場合、*npm* が見つからない警告メッセージが表示され、プロジェクトが正しく動作しません。

このエラーを解決するには、以下のプロパティをプロジェクトに追加します。

```xml
<PropertyGroup>
  <DisableRevealExportToImage>true</DisableRevealExportToImage>
</PropertyGroup>
```

<a name='sqlite-fix'></a>
### NuGet 使用時のビルドの問題

**SQLite.Interop.dll** に関連するデプロイメントの問題を処理するために、NuGet パッケージでカスタムの .targets ファイルが使用されています。

ビルドに問題がある場合は、プロジェクトに次のプロパティを追加してこの動作を無効にできます。

``` xml
<DisableSQLiteInteropFix>true</DisableSQLiteInteropFix>
```

## セットアップと構成 (クライアント)  

以下は、Reveal Web Client SDK を設定するための手順です。

1.  [**依存関係の確認**](#check-dependencies)

2.  [**Web Client SDK の参照**](#reference-web-client-sdk)

3.  [**Web Client SDK のインスタンス化**](#instantiate-web-client-sdk)

<a name='check-dependencies'></a>

### 1\. 依存関係の確認
Reveal Web Client SDK には、サードパーティーの参照が 2 つあります。

- [jQuery](https://jquery.com) 2.2 またはそれ以上
- [Day.js](https://day.js.org) 1.8.15 またはそれ以上
- [Quill RTE](https://quilljs.com/) 1.3.6 またはそれ以上
- [Marker Clusterer](https://developers.google.com/maps/documentation/javascript/examples/markerclusterer/markerclusterer.js) 3 またはそれ以上
- [Google Maps](https://maps.googleapis.com/maps/api/js?key=AIzaSyBpcuViSxzlScwOBZy5ln5iIvRl9TYn4y0&libraries=drawing,visualization) 3 またはそれ以上

<a name='reference-web-client-sdk'></a>

### 2\. Web Client SDK の参照

Web ページで **$.ig.RevealView** コンポーネントを有効にするには、いくつかの クリプトを含める必要があります。これらのスクリプトは Reveal Web Client SDK の一部として提供されます。

```html
<script src="~/Reveal/infragistics.reveal.js"></script>
```

JavaScript ファイル は \<InstallationDirectory\>\\SDK\\Web\\JS\\Client にあります。

<a name='instantiate-web-client-sdk'></a>

### 3\. Web Client SDK のインスタンス化

ダッシュボードのプレゼンテーションは、Web Client SDK を介してネイティブに処理されます。

以下の手順に従って作業を開始します。

1.  id を指定して \<div /\> 要素を定義し、**\$.ig.RevealView** コンストラクターを呼び出します。

    > [!NOTE]
    > **サーバー側とクライアント側のパーツを個別にホスト**
    > 個別のサーバーでクライアント側とサーバー側のパーツをホストする場合は、次の手順を続行する前に[こちら](~/jp/developer/web-sdk/overview.html#host-client-server-separate)を参照してください。

2.  **\$.ig.RVDashboard.loadDashboard** を呼び出して _dashboardId_ と成功およびエラー ハンドラを指定します。

3.  成功ハンドラーで、ダッシュボードが描画される DOM 要素のセレクターを渡すことにより、**\$.ig.RevealView** コンポーネントをインスタンス化します。最後に、取得したダッシュボードを使用し、**\$.ig.RevealView** のダッシュボード プロパティに設定する必要があります。

### サンプル コード

```html
<!DOCTYPE html>
<html>
  <head>
    ⋮
    <script type="text/javascript">
      var dashboardId = "dashboardId";

      $.ig.RVDashboard.loadDashboard(
        dashboardId,
        function (dashboard) {
          var revealView = new $.ig.RevealView("#revealView");
          revealView.dashboard = dashboard;
        },
        function (error) {
          //ここで発生する可能性があるエラーを処理します。
        }
      );
    </script>
  </head>
  <body>
    <div id="revealView" style="height:500px;" />
  </body>
</html>
```

