# セットアップと構成 (Web)

## 前提条件

Reveal Server SDK には、.NET Core 3.1 以降が必要です。

## セットアップと構成の概要 

以下は、Reveal Web Server SDK 設定の手順です。

1.  [**Reveal SDK をインストールします。**](#installing-reveal-sdk)

2.  [**DashboardProvider を定義します。**](#defining-dashboardprovider)

3.  [**サーバー SDK を初期化します。**](#initializing-server-sdk)

4.  [**サーバー側画像生成を有効化します。**](#server-side-image-export)

<a name='installing-reveal-sdk'></a>

### 1\. Reveal SDK のインストール

マシンで Reveal Sdk インストーラーを実行して、アセンブリと依存関係パッケージを準備します。

インストールが完了すると、**nuget.config** に追加された _Infragistics (Local)_ という新しい NuGet パッケージ ソースが見つかります。
これは、「%public%\\Documents\\Infragistics\\NuGet」を指します。

<img src="images/addingNugetPackage_web.png" alt="addingNugetPackage_web" class="responsive-img"/>

Infragistics (Local) フィードがインストーラーによって正しく設定されていることを確認後:

- **Reveal.Sdk.Web.AspNetCore(.Trial)** NuGet パッケージをアプリ プロジェクトにインストールします。
- NuGet パッケージ参照を System.Data.SQLite バージョン 1.0.111 以降に追加します。

> [!NOTE] 
> トライアル nuget パッケージは nuget.org で入手できます: [**Reveal.Sdk.Web.AspNetCore.Trial**](https://www.nuget.org/packages/Reveal.Sdk.Web.AspNetCore.Trial/)。


ビルドに問題がある場合は、この[**リンク**](#sqlite-fix)に従ってください。

<a name='defining-dashboardprovider'></a>

### 2\. DashboardProvider の定義

nuget パッケージをインストールした後、**IVRDashboardProvider** インターフェイスを実装するクラスを作成する必要があります。このクラスは、ダッシュボードの読み込みと保存を処理します。

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

上記のコードは、単純なファイル システム ベースのプロバイダーを実装しています。基本的に、ダッシュボードの読み込み元/保存先のディレクトリを指定するコンストラクター内の引数を受け入れます。また、ファイル拡張子を指定し忘れたり、指定したくない場合でも問題ありません。

<a name='initializing-server-sdk'></a>

### 3\. サーバー SDK の初期化

**Startup.cs** のアプリケーションの **ConfigureServices** メソッドで、IMvcBuilder インターフェイスを返す 1 つ以上の AspNetCore サービスを追加する必要があります。最もよく使用されるサービスは、AddMvc、AddControllersWithViews、および AddControllers です。これらのいずれかを追加した後、その上に *.AddReveal* を呼び出す必要があります。**AddReveal** は、IMvcBuilder を拡張するために使用される拡張メソッドです。


> [!NOTE]
> AddReveal 拡張メソッドは Reveal.Sdk 名前空間にあるため、Startup.cs にその使用法を追加する必要があります。

**AddReveal** を使用すると、Reveal サーバー コンポーネントを登録したり、設定を提供したりできます。以下のコード スニペットは、前の手順で定義された DashboardProvider クラスを登録する基本的な呼び出しを表しています:

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

DashboardProvider クラスの登録に加えて、LocalFileStoragePath も指定されました。これは、Excel や CSV などの静的データ ソース ファイルが配置されるパスであり、使用されるキャッシュ場所のデフォルト設定です。

特定のインスタンスではなく、タイプを登録する必要があることに注意してください。これは、タイプが AspNetCore Di コンテナーに登録されるためです。
このアプローチにより、DashboarProvider の実装や他の Reveal プロバイダーで使用している可能性のある他のサービスを柔軟に注入できます。必要に応じてインスタンスを自由に登録できます。他のオーバーロード AddDashboardProvider メソッドを使用するだけです。以下に示すように:
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

Web ページで **RevealView** コンポーネントを有効にするには、いくつかの クリプトを含める必要があります。これらのスクリプトは Reveal Web Client SDK の一部として提供されます。

```html
<script src="~/Reveal/infragistics.reveal.js"></script>
```

JavaScript ファイル は \<InstallationDirectory\>\\SDK\\Web\\JS\\Client にあります。
デフォルトのインストール ディレクトリは次のとおりです:
```cmd
"%public%\\Documents\\Infragistics"
```

> [!NOTE] 
> **Reveal JS クラスの参照**
> **$.ig.** または **RevealApi.** を介して JS クラスを参照できます。
> ドキュメント全体を通して、クラスを参照するために「$.ig.」プレフィックスを使用しています。
>「$.ig.」の代わりに RevealApi プレフィックスを使用できます。

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

