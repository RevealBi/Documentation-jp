# Spring サーバーのセットアップと構成

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

既存の Spring Boot アプリケーションで Reveal をセットアップするには、次のことを行う必要があります:

1.  spring-starter-jersey の実装に依存関係を追加します。
2.  Reveal SDK に依存関係を追加します。
3.  Reveal を初期化します。
4.  サーバー側エクスポートを有効にします。

### 手順 1 - spring-starter-jersey の実装に依存関係を追加します。

まだ追加されていない場合は、*spring-starter-jersey* に依存関係を追加します。

``` java
<dependency>
    <groupId>org.springframework.boot</groupId>
    <artifactId>spring-boot-starter-jersey</artifactId>
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

Reveal リソースを使用して Jakarta RESTful Web サービス (JAX-RS) アプリケーションを初期化する **JerseyConfig** コンポーネントを追加します。
これを行うには、パッケージ *com.pany.analytics.upmedia.reveal* 内にある *upmedia-backend-spring* ソース コードからクラス **RevealJerseyConfig** をコピーできます。

**@ApplicationPath** 注釈は、Reveal サービスを利用できるパスを構成します。これを変更する場合は、クライアント側のパスも変更する必要があります。React アプリケーションの場合、これは index.html で構成されます。

``` js
$.ig.RevealSdkSettings.setBaseUrl("http://localhost:8080/upmedia-backend/reveal-api/");
```

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