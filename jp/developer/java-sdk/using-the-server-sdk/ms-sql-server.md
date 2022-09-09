# MS SQL Server データ ソースの置き換え

**手順 1** - Java Web API サーバー アプリケーションで、`IRVDataSourceProvider` を実装するクラスを作成します。このクラスは、MS SQL Server 設定の実際の置換を実行します。 

```java
public class LocalSampleDataSourceProvider implements IRVDataSourceProvider {

	public RVDashboardDataSource changeDataSource(IRVUserContext userContext, RVDashboardDataSource dataSource) {

		return null;
	}

	public RVDataSourceItem changeDataSourceItem(IRVUserContext userContext, String dashboardsID, RVDataSourceItem dataSourceItem) {

		return null;
	}
}
```

このクラスの `changeDataSourceItem` メソッドは、表示形式がデータを取得するために使用する `RVDataSourceItem` を返します。`changeDataSourceItem` メソッドで引数として提供される `RVDataSourceItem` 項目を変更することにより、データを取得するサーバーまたはテーブルを変更できます。

**手順 2** - `WebAppListener.java` ファイルの `contextInitialized` 関数を更新して、`setDataSourceProvider(new LocalSampleDataSourceProvider()).` メソッドを使用して、作成したばかりの `IRVDataSourceProvider` を `RevealEngineInitializer` に追加します。

```java
	public void contextInitialized(ServletContextEvent ctx) {
		RevealEngineInitializer.initialize(new InitializeParameterBuilder().
				setDataSourceProvider(new LocalSampleDataSourceProvider()).
				.build());

		ctx.getServletContext().setAttribute("revealSdkVersion", RevealEngineInitializer.getRevealSdkVersion());
	}
```

## 例: ホスト、データベース、およびテーブルの置き換え

各 `RVDataSourceItem` を `RVSqlServerDataSourceItem` としてキャストし、そのプロパティを次のように変更することで、ダッシュボード内のすべての MS SQL Server データ ソース項目の MS SQL Server ホスト、データベース、およびテーブル名を変更できます。

```java
public class LocalSampleDataSourceProvider implements IRVDataSourceProvider {

	public RVDashboardDataSource changeDataSource(IRVUserContext userContext, RVDashboardDataSource dataSource) {

		return null;
	}

	public RVDataSourceItem changeDataSourceItem(IRVUserContext userContext, String dashboardsID, RVDataSourceItem dataSourceItem) {

		if (dataSourceItem instanceof RVSqlServerDataSourceItem)
		{
			RVSqlServerDataSourceItem sqlServerDsi = (RVSqlServerDataSourceItem)dataSourceItem;
			// Change SQL Server host and database
			RVSqlServerDataSource sqlServerDS = (RVSqlServerDataSource)sqlServerDsi.getDataSource();
			sqlServerDS.setHost("10.0.0.20");
			sqlServerDS.setDatabase("Adventure Works");

			// Change SQL Server table/view
			sqlServerDsi.setTable("Employees");

			return (RVDataSourceItem)sqlServerDsi;
		}
		return null;
	}
}
```
