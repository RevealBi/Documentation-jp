# Tomcat サーバーのセットアップと構成

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

## セットアップと構成

既存の Tomcat アプリケーションまたはその他の JEE コンテナーを使用して Reveal を設定するには、次のことを行う必要があります:

1.  JAX-RS 実装に依存関係を追加します。
2.  Reveal SDK に依存関係を追加します。
3.  Reveal を初期化します。
4.  サーバー側エクスポートを有効にします。

### 手順 1 - JAX-RS 実装に依存関係を追加します。

Jakarta RESTful Web サービス (JAX-RS) 実装に依存関係を追加します。Jersey、RESTeasy、Apache CXF などの複数のオプションから選択できます。ご希望のプロバイダーが説明する手順に従ってください。

例として、Jersey に追加する必要のある依存関係を次に示します:

``` java
<dependency>
    <groupId>org.glassfish.jersey.containers</groupId>
    <artifactId>jersey-container-servlet</artifactId>
    <version>2.32</version>
</dependency>
<dependency>
    <groupId>org.glassfish.jersey.inject</groupId>
    <artifactId>jersey-cdi2-se</artifactId>
    <version>2.32</version>
</dependency>
```

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

Reveal を初期化するため、**ServletContextListener** クラスを追加します。
これを行うには、パッケージ *com.pany.analytics.upmedia.reveal* 内にある *upmedia-backend-tomcat* ソース コードからクラス **WebAppListener** をコピーできます。

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