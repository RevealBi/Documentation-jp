## Java 1.1.0 での重大な変更のリスト

### 削除されたクラス

- **RVBaseUserContextProvider** - そこから拡張するクラスは、代わりに `IRVUserContextProvider` インターフェースまたは `RVContainerRequestAwareUserContextProvider` を実装する必要があります。

- **RVBaseAuthenticationProvider** - そこから拡張するクラスは、代わりに `IRVAuthenticationProvider` インターフェースを実装する必要があります。

- **RVBaseDashboardAuthorizationProvider** - そこから拡張するクラスは、代わりに `IRVDashboardAuthorizationProvider` インターフェースを実装する必要があります。

- **RVBaseDataSourceProvider** - そこから拡張するクラスは、代わりに `IRVDataSourceProvider` インターフェースを実装する必要があります。

- **RVBaseDashboardProvider** - そこから拡張するクラスは、代わりに `IRVDashboardProvider` インターフェースを実装する必要があります。

- **RVBaseDataProvider** - そこから拡張するクラスは、代わりに `IRVDataProvider` インターフェースを実装する必要があります。


### メソッドが削除されました。

- **RVContainerRequestAwareUserContextProvider#getUserId(ContainerRequestContext requestContext)** - 拡張機能は代わりに `getUserContext (ContainerRequestContext requestContext)` を実装する必要があります。


### 変更を伴うインターフェース

- `IRVAuthenticationProvider`、`IRVDashboardAuthorizationProvider`、`IRVDataSourceProvider`、`IRVDashboardProvider`、`IRVDataProvider`、`IRVAuthenticationResolver`。
これらのインターフェースはすべて、メソッド シグネチャを変更し、以前は String 型パラメータのユーザー ID を受け取りましたが、現在は代わりに `IRVUserContext` の 「userContext」 パラメータを受け取ります。

- **IRVDataSourceProvider** - 以前は、`changeVisualizationDataSourceItem` と `changeDashboardFilterDataSourceItem` を実装する必要がありました。これら 2 つは、`changeDataSourceItem` という 1 つのメソッドに置き換えられました (ダッシュボード フィルターで使用されるデータ ソース項目と視覚化で使用されるデータ ソース項目は区別されません)。

### Reveal の初期化の変更

`RevealEngineInitializer#Initialize(IRVAuthenticationProvider authProvider, IRVUserContextProvider userContextProvider, IRVDashboardProvider dashboardProvider, IRVDataSourceProvider dataSourceProvider, IRVDataProvider dataProvider)` が削除されました。代わりに、 `initialize(InitializeParameter parameterObject)` を使用してください。

### 動作の変更

- RevealBi によって発行されたすべてのログ カテゴリが「io.revealbi」の下になりました。

- RevealBi は、http 応答で Java 例外の詳細を返さなくなりました。代わりに、サーバー ログで例外の詳細を識別するために使用できる相関 ID とともに、一般的なエラー メッセージが表示されます。






## プロジェクトをアップグレードする方法

**RevealEngineInitializer.initialize** を使用して Reveal を初期化するのではなく、**initialize(InitializeParameter parameterObject)** を使用するようになりました。

使用可能なパラメーターは同じままで、以下の例に示すように使用できます。

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

利用できるパラメーター:
- *setAuthProvider*。ここで、認証を解決し、IRVAuthenticationProvider を実装するカスタム クラスを含める必要があります。
- *setUserContextProvider*。IRVUserContextProvider を実装するユーザーに関する情報を提供するカスタム クラス。
- *setDashboardProvider*。ダッシュボードを置換または変更するカスタム クラス。IRVDashboardProvider を実装します。
- *setDataSourceProvider*。データソースを置換または変更するカスタム クラス。IRVDataSourceProvider を実装します。
- *setDataProvider*。ダッシュボードのインメモリ データを返すカスタム クラス。IRVDataProvider を実装します。
- *setLicense*。ここでは、シリアル キーを含めて SDK ライセンスを構成できます。

独自のダッシュボード プロバイダーを実装する方法の詳細については、GitHub の [UpMedia サンプル](https://github.com/RevealBi/sdk-samples-java)を確認してください。