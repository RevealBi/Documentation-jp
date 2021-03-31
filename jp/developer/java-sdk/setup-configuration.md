## セットアップと構成

<a name='maven-dependency'></a>

### 前提条件 (Maven)

Reveal Java SDK は、[Maven](https://maven.apache.org/what-is-maven.html) モジュールのセットとして配布されます。SDK ライブラリを操作するには、Reveal の Maven リポジトリへの参照と、Maven pom.xml ファイルの依存関係を追加する必要があります。

以下のリポジトリを追加します:

```xml
<repositories>
  <repository>
    <id>reveal.public</id>
    <url>http://revealpackages.eastus.cloudapp.azure.com/repository/public</url>
  </repository>	
</repositories>
```

以下の依存関係を追加します:

```xml
<dependency>
  <groupId>com.infragistics.reveal.sdk</groupId>
  <artifactId>reveal-sdk</artifactId>
  <version>version_number</version>
</dependency>
```

version_number を **0.9.6** のような番号に置き換えます。

Maven ついてご不明な点がございましたら、次の[リンク](https://maven.apache.org/guides/getting-started/maven-in-five-minutes.html)を参照してください。


### セットアップと構成 (汎用サーバー)

Reveal を既存のアプリケーションと統合するには、次の一般的な手順に従う必要があります:

1.  既存のアプリの実装に依存関係を追加します。
2.  Reveal SDK に依存関係を追加します。
3.  Reveal を初期化します。
4.  Enable server-side export

#### 手順 1 - Adding a dependency to the app implementation

Add a dependency to the existing application implementation, following the steps needed for the server of your preference.

#### 手順 2 - Reveal SDK に依存関係を追加します。

*reveal-sdk* に依存関係を追加し、SDK のバージョンを指定します。

``` java
<dependency>
    <groupId>com.infragistics.reveal.sdk</groupId>
    <artifactId>reveal-sdk</artifactId>
    <version>version_number</version>
</dependency>
```

version_number を **1.0.1821** のような番号に置き換えます。

#### 手順 3 - Reveal を初期化します。

To initialize Reveal, you can either **?????**

---
``` java
RevealEngineInitializer.initialize(
new RevealEngineInitializer.InitializeParameter()
      .withAuthProvider(new RevealAuthenticationProvider())
      .withUserContextProvider(new RevealUserContextProvider())
      .withDashboardProvider(new RevealDashboardProvider())
      .withDataSourceProvider(new UpMediaDataSourceProvider())
      .withDataProvider(new UpMediaInMemoryDataProvider())
      .setMaxConcurrentImageRenderThreads(2));
```

---

RevealEngineInitializer.initialize に渡されるパラメーターは次のとおりです:
- IRVAuthenticationProvider
- IRVUserContextProvider
- IRVDashboardProvider
- IRVDataSourceProvider
- IRVDataProvider

これらは Reveal のカスタマイズに使用される**プロバイダー**です。Reveal をアプリケーションに統合する場合は、独自のプロバイダーを作成する必要があります。

If you are interested in the configuration of Tomcat or Spring, follow the links below:
- [Tomcat Server](setup-configuration-tomcat.md)
- [Spring Server](setup-configuration-spring.md)

---
#### Step 4 - Enabling server-side export

The Java SDK uses some native components for exporting dashboards to different formats: Image, PDF, PPT and Excel.

If you are interested in exporting server-side to one or more of those formats, please refer to [Server-side Export Configuration](export-server-side.md)


### セットアップと構成 (クライアント)

以下は、Reveal Web クライアント SDK を設定するための手順です。

1.  [**依存関係を確認します**](#check-dependencies)。

2.  [**Web クライアント SDK を参照します**](#reference-web-client-sdk)。

3.  [**Web クライアント SDK をインスタンス化します**](#instantiate-web-client-sdk)。


<a name='check-dependencies'></a>

#### 1\. 依存関係の確認

Reveal Web クライアント SDK には、次のサードパーティの参照があります:

- [jQuery](https://jquery.com) 2.2 またはそれ以上
- [Day.js](https://day.js.org) 1.8.15 またはそれ以上
- [Quill RTE](https://quilljs.com/) 1.3.6 またはそれ以上

<a name='reference-web-client-sdk'></a>

#### 2\. Web クライアント SDK の参照

Web ページで **\$.ig.RevealView** コンポーネントを有効にするには、いくつかのスクリプトを含める必要があります。These scripts will be provided as part of Reveal Web Client SDK.

```html
<script src="~/Reveal/infragistics.reveal.js"></script>
```

JavaScript files can be found in "\<InstallationDirectory\>\\SDK\\Web\\JS\\Client".

<a name='instantiate-web-client-sdk'></a>

#### 3\. Web クライアント SDK のインスタンス化

ダッシュボードのプレゼンテーションは、Web クライアント SDK を介してネイティブに処理されます。

以下の手順に従って作業を開始します:

1. "id" を指定して \<div /\> 要素を定義し、**\$.ig.RevealView** コンストラクターを呼び出します。

    > [!NOTE] > **サーバー側とクライアント側のパーツを個別にホストする**
    > 別々のサーバーでクライアント側とサーバー側のパーツをホストする場合は、次の手順を続行する**前に**[こちら](~/jp/developer/web-sdk/overview.html#host-client-server-separate)を参照してください。

2. _dashboardId_ と成功およびエラー ハンドラーを指定して **\$.ig.RVDashboard.loadDashboard** を呼び出します。

3. 成功ハンドラーで、ダッシュボードが描画される DOM 要素のセレクターを渡すことにより、**\$.ig.RevealView** コンポーネントをインスタンス化します。最後に、取得したダッシュボードを使用し、**\$.ig.RevealView** のダッシュボード プロパティに設定する必要があります。

#### サンプル コード

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
          //Process any error that might occur here
        }
      );
    </script>
  </head>
  <body>
    <div id="revealView" style="height:500px;" />
  </body>
</html>
```
