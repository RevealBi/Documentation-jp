# セットアップと構成

<a name='maven-dependency'></a>

## 前提条件 (Maven)

Reveal Java SDK は、[Maven (英語)](https://maven.apache.org/what-is-maven.html) モジュールのセットとして配布されます。SDK ライブラリを操作するには、Reveal の Maven リポジトリへの参照と、Maven pom.xml ファイルの依存関係を追加する必要があります。

以下のリポジトリを追加します:

```xml
<repositories>
  <repository>
    <id>reveal.public</id>
    <url>https://maven.revealbi.io/repository/public</url>
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

Maven ついてご不明な点がございましたら、次の[リンク (英語)](https://maven.apache.org/guides/getting-started/maven-in-five-minutes.html) を参照してください。

> [!NOTE]
> Oracle データベースを使用している場合は、アプリケーションにドライバーを追加する必要があります。

## セットアップと構成 (汎用サーバー)

Reveal を既存のアプリケーションと統合するには、次の一般的な手順に従う必要があります:

1.  既存のアプリの実装に依存関係を追加します。
2.  Reveal SDK に依存関係を追加します。
3.  Reveal を初期化します。
4.  サーバー側エクスポートを有効にします。

Tomcat または Spring の構成については、以下のリンクを参照してください。
- [Tomcat サーバー](setup-configuration-tomcat.md)
- [Spring サーバー](setup-configuration-spring.md)
- [Oracle サーバー](setup-configuration-oracle.md)

### 手順 1 – アプリケーションに依存関係を追加します。

必要な手順に従って、既存のアプリケーションに依存関係を追加します。

### 手順 2 - Reveal SDK に依存関係を追加します。

*reveal-sdk* に依存関係を追加し、SDK のバージョンを指定します。

``` java
<dependency>
    <groupId>com.infragistics.reveal.sdk</groupId>
    <artifactId>reveal-sdk</artifactId>
    <version>version_number</version>
</dependency>
```

version_number を **1.0.1821** のような番号に置き換えます。

### 手順 3 - Reveal を初期化します。

Reveal を初期化するには、**RevealEngineInitializer.initialize** を使用します。

初期パラメーターなしでメソッドを呼び出すことが可能です。

``` java
RevealEngineInitializer.initialize();
```
ただし、ほとんどの場合、以下の例のようにパラメーターを使用します。

``` java
RevealEngineInitializer.initialize(
    new InitializeParameterBuilder()
        .setAuthProvider(new RevealAuthenticationProvider())
        .setUserContextProvider(new RevealUserContextProvider())
        .setDashboardProvider(new RevealDashboardProvider())
        .setDataSourceProvider(new UpMediaDataSourceProvider())
        .setDataProvider(new UpMediaInMemoryDataProvider())
        .setMaxConcurrentImageRenderThreads(2)
        .setLicense("SERIAL_KEY_TO_BE_USED")
        .build());
```
これらのパラメーターは Reveal のカスタマイズに使用される**プロバイダー**です。Reveal をアプリケーションに統合する場合は、独自のプロバイダーを作成する必要があります。

**RevealEngineInitializer.initialize** に渡される利用可能なパラメーターは次のとおりです:
- *setAuthProvider*。ここで、認証を解決し、IRVAuthenticationProvider を実装するカスタム クラスを含める必要があります。
- *setUserContextProvider*。IRVUserContextProvider を実装するユーザーに関する情報を提供するカスタム クラス。
- *setDashboardProvider*。ダッシュボードを置換または変更するカスタム クラス。IRVDashboardProvider を実装します。
- *setDataSourceProvider*。データソースを置換または変更するカスタム クラス。IRVDataSourceProvider を実装します。
- *setDataProvider*。ダッシュボードのインメモリ データを返すカスタム クラス。IRVDataProvider を実装します。
- *setLicense*。ここでは、シリアル キーを含めて SDK ライセンスを構成できます。

ダッシュボード プロバイダーを実装する方法の詳細については、GitHub の [UpMedia サンプル (英語)](https://github.com/RevealBi/sdk-samples-java) を参照してください。

### 手順 4 - サーバー側エクスポートを有効にします。

Java SDK は、ダッシュボードをさまざまな形式 (Image、PDF、PPT、Excel) にエクスポートするためにいくつかのネイティブ コンポーネントを使用します。

これらの形式の 1 つ以上にサーバー側をエクスポートする場合は、[サーバー側のエクスポート構成](export-server-side.md)を参照してください。


## セットアップと構成 (クライアント)

以下は、Reveal Web クライアント SDK を設定するための手順です。

1.  [**依存関係を確認します**](#check-dependencies)。

2.  [**Web クライアント SDK を参照します**](#reference-web-client-sdk)。

3.  [**Web クライアント SDK をインスタンス化します**](#instantiate-web-client-sdk)。


<a name='check-dependencies'></a>

### 1\. 依存関係の確認

Reveal Web クライアント SDK には、次のサードパーティの参照があります:

- [jQuery](https://jquery.com) 2.2 またはそれ以降
- [Day.js](https://day.js.org) 1.8.15 またはそれ以降
- [Quill RTE](https://quilljs.com/) 1.3.6 またはそれ以降
- **(オプション)** [Spectrum](https://github.com/bgrins/spectrum) v 1.8.0 以降 - これは、エンド ユーザーが特定の可視化の背景色を設定できるように UI を有効にする場合にのみ必要です。
[canChangeVisualizationBackgroundColor](~/jp/developer/web-sdk/using-the-client-sdk/showing-hiding-elements.html#canChangeVisualizationBackgroundColor) をご覧ください。

<a name='reference-web-client-sdk'></a>

### 2\. Web クライアント SDK の参照

Web ページで **\$.ig.RevealView** コンポーネントを有効にするには、いくつかのスクリプトを含める必要があります。これらのスクリプトは Reveal Web クライアント SDK の一部として提供されます。

```html
<script src="~/Reveal/infragistics.reveal.js"></script>
```

使用のバージョンの Java SDK の JavaScript ファイルをダウンロードする必要があります。すべての Java SDK バージョンのダウンロード リンクを含む表を以下に示します。各バージョンのリリース ノートへのリンクも表に記載されています。 

|                                                                  **JS ファイルのダウンロード**                                                                   |                                 **リリース ノート**                                 |
| :----------------------------------------------------------------------------------------------------------------------------------------------------------: | :-------------------------------------------------------------------------------: |
| [JAVA SDK 1.0.7](https://maven.revealbi.io/repository/public/com/infragistics/reveal/sdk/reveal-sdk-distribution/1.0.7/reveal-sdk-distribution-1.0.7-js.zip) | [バージョン 1.0.7](~/jp/developer/release-information/release-notes.html#java-sdk-1.0.7) |
| [JAVA SDK 1.0.6](https://maven.revealbi.io/repository/public/com/infragistics/reveal/sdk/reveal-sdk-distribution/1.0.6/reveal-sdk-distribution-1.0.6-js.zip) | [バージョン 1.0.6](~/jp/developer/release-information/release-notes.html#java-sdk-1.0.6) |
| [JAVA SDK 1.0.5](https://maven.revealbi.io/repository/public/com/infragistics/reveal/sdk/reveal-sdk-distribution/1.0.5/reveal-sdk-distribution-1.0.5-js.zip) | [バージョン 1.0.5](~/jp/developer/release-information/release-notes.html#java-sdk-1.0.5) |
| [JAVA SDK 1.0.4](https://maven.revealbi.io/repository/public/com/infragistics/reveal/sdk/reveal-sdk-distribution/1.0.4/reveal-sdk-distribution-1.0.4-js.zip) | [バージョン 1.0.4](~/jp/developer/release-information/release-notes.html#java-sdk-1.0.4) |
| [JAVA SDK 1.0.3](https://maven.revealbi.io/repository/public/com/infragistics/reveal/sdk/reveal-sdk-distribution/1.0.3/reveal-sdk-distribution-1.0.3-js.zip) | [バージョン 1.0.3](~/jp/developer/release-information/release-notes.html#java-sdk-1.0.3) |
| [JAVA SDK 1.0.0](https://maven.revealbi.io/repository/public/com/infragistics/reveal/sdk/reveal-sdk-distribution/1.0.0/reveal-sdk-distribution-1.0.0-js.zip) | [バージョン 1.0.0](~/jp/developer/release-information/release-notes.html#java-sdk-1.0.0) |

> [!NOTE] **Reveal JS クラスの参照**
> **$.ig.** または **RevealApi.** を介して JS クラスを参照できます。
> ドキュメント全体を通して、クラスを参照するために「$.ig.」プレフィックスを使用しています。
>「$.ig.」の代わりに RevealApi プレフィックスを使用できます。

<a name='instantiate-web-client-sdk'></a>

### 3\. Web クライアント SDK のインスタンス化

ダッシュボードのプレゼンテーションは、Web クライアント SDK を介してネイティブに処理されます。

以下の手順に従って作業を開始します:

1. "id" を指定して \<div /\> 要素を定義し、**\$.ig.RevealView** コンストラクターを呼び出します。

    > [!NOTE] 
    > **サーバー側とクライアント側のパーツを個別にホストする**
    > 別々のサーバーでクライアント側とサーバー側のパーツをホストする場合は、次の手順を続行する**前に**[こちら](~/jp/developer/web-sdk/overview.html#host-client-server-separate)を参照してください。

2.  _dashboardId_ と成功およびエラー ハンドラーを指定して **\$.ig.RVDashboard.loadDashboard** を呼び出します。

3.  成功ハンドラーで、ダッシュボードが描画される DOM 要素のセレクターを渡すことにより、**\$.ig.RevealView** コンポーネントをインスタンス化します。

    最後に、取得したダッシュボードを使用し、**\$.ig.RevealView** のダッシュボード プロパティに設定する必要があります。

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

## Oracle データベースの操作

上記のように、Reveal Java SDK は、[Maven](https://maven.apache.org/what-is-maven.html) モジュールのセットとして配布されます。SDK ライブラリを操作するには、Maven pom.xml ファイルに 2 つの参照と依存関係を追加する必要があります。

以下のリポジトリを追加します:

```xml
<repositories>
  <repository>
    <id>reveal.public</id>
    <url>http://revealpackages.eastus.cloudapp.azure.com/repository/public</url>
  </repository>	
  <repository>
    <id>jeecg</id>
    <url>http://maven.jeecg.org/nexus/content/repositories/jeecg/</url> 
  </repository>
</repositories>
```

そして、次の依存関係を追加します:

```xml
<dependencies>
  <dependency>
    <groupId>com.infragistics.reveal.sdk</groupId>
    <artifactId>reveal-sdk</artifactId>
    <version>version_number</version>
  </dependency>
  <dependency>
    <groupId>com.oracle</groupId>
    <artifactId>ojdbc14</artifactId>
    <version>10.2.0.5.0</version>
  </dependency>
</dependencies>
```
