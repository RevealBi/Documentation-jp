## Java v1.1.0 での重大な変更のリスト

### 削除されたクラス

- **RVBaseUserContextProvider** - そこから拡張するクラスは、代わりに `IRVUserContextProvider` インターフェースまたは `RVContainerRequestAwareUserContextProvider` を実装する必要があります。

- **RVBaseAuthenticationProvider** - そこから拡張するクラスは、代わりに `IRVAuthenticationProvider` インターフェースを実装する必要があります。

- **RVBaseDashboardAuthorizationProvider** - そこから拡張するクラスは、代わりに `IRVDashboardAuthorizationProvider` インターフェースを実装する必要があります。

- **RVBaseDataSourceProvider** - そこから拡張するクラスは、代わりに `IRVDataSourceProvider` インターフェースを実装する必要があります。

- **RVBaseDashboardProvider** - そこから拡張するクラスは、代わりに `IRVDashboardProvider` インターフェースを実装する必要があります。

- **RVBaseDataProvider** - そこから拡張するクラスは、代わりに `IRVDataProvider` インターフェースを実装する必要があります。


### 削除されたメソッド

- **RVContainerRequestAwareUserContextProvider#getUserId(ContainerRequestContext requestContext)** - 拡張機能は代わりに `getUserContext (ContainerRequestContext requestContext)` を実装する必要があります。

- **RevealEngineInitializer#Initialize(IRVAuthenticationProvider authProvider、IRVUserContextProvider userContextProvider、IRVDashboardProvider dashboardProvider、IRVDataSourceProvider dataSourceProvider、IRVDataProvider dataProvider)** - 代わりに `initialize(InitializeParameter parameterObject)` を使用してください。


### 変更を伴うインターフェース

- `IRVAuthenticationProvider`、`IRVDashboardAuthorizationProvider`、`IRVDataSourceProvider`、`IRVDashboardProvider`、`IRVDataProvider`、`IRVAuthenticationResolver`。これらのインターフェースはすべて、メソッド シグネチャを変更し、以前は String 型パラメータのユーザー ID を受け取りましたが、現在は代わりに `IRVUserContext` の「userContext」パラメータを受け取ります。

- **IRVDataSourceProvider** - 以前は、`changeVisualizationDataSourceItem` と `changeDashboardFilterDataSourceItem` を実装する必要がありました。これら 2 つは、`changeDataSourceItem` という 1 つのメソッドに置き換えられました (ダッシュボード フィルターで使用されるデータ ソース項目と視覚化で使用されるデータ ソース項目は区別されません)。

### Reveal の初期化の変更

`RevealEngineInitializer#Initialize(IRVAuthenticationProvider authProvider, IRVUserContextProvider userContextProvider, IRVDashboardProvider dashboardProvider, IRVDataSourceProvider dataSourceProvider, IRVDataProvider dataProvider)` が削除されました。代わりに、`initialize(InitializeParameter parameterObject)` を使用してください。

### 動作の変更

- RevealBi によって発行されたすべてのログ カテゴリが「io.revealbi」の下になりました。

- RevealBi は、HTTP 応答で Java 例外の詳細を返さなくなりました。代わりに、サーバー ログで例外の詳細を識別するために使用できる相関 ID とともに、一般的なエラー メッセージが表示されます。

- **[JS Client]** the onVisualizationLinkingDashboard event was removed from the RevealView class in favor of `onLinkedDashboardProviderAsync` which serves the same purpose and is used when creating the dashboard link in the editor.