# Excel ファイル データ ソースの置き換え

ダッシュボードは、クラウドに保存されている Excel ファイルを表示形式のデータ ソースとして使用して作成される場合があります。

アプリケーションに Reveal SDK を埋め込む場合、これらのクラウドベースのファイルを、実行時にサーバー上にあるローカル ディレクトリに保存されているファイルに置き換えることができます。

**手順 1** - Java Web API サーバー アプリケーションで、`IRVDataSourceProvider` を実装するクラスを作成します。このクラスは、Excel ファイルの実際の置換を実行します。

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

このクラスの `changeDataSourceItem` メソッドは、表示形式がデータを取得するために使用する `RVDataSourceItem` を返します。`changeDataSourceItem` メソッドで引数として提供される `RVDataSourceItem` 項目を変更することにより、どの Excel ファイルからデータを取得するかを変更できます。

**手順 2** - `WebAppListener.java` ファイルの `contextInitialized` 関数を更新して、`setDataSourceProvider(new LocalSampleDataSourceProvider()).` メソッドを使用して、先ほど作成した `IRVDataSourceProvider` を `RevealEngineInitializer` に追加します。また、「local:/SalesLocalExcelFile.xlsx」などの相対 URI に使用するルートディレクトリを指定するため、RevealEngineInitializer 内で `setLocalFilesStoragePath("your_root_directory")` を使用してローカル ストレージ データ パスを指定する必要があります。

```java
	public void contextInitialized(ServletContextEvent ctx) {
		RevealEngineInitializer.initialize(new InitializeParameterBuilder().
				setDataSourceProvider(new LocalSampleDataSourceProvider()).
				.build());

		ctx.getServletContext().setAttribute("revealSdkVersion", RevealEngineInitializer.getRevealSdkVersion());
	}
```

## 例: Excel ファイル データ ソースの置き換え

この例では、「Sales CloudExcelFile」という名前のクラウドベースの Excel ファイルを使用しているデータ ソース項目を「SalesLocalExcelFile.xlsx」という名前のローカル Excel ファイルに置き換えています。

まず、受信 `RVDataSourceItem` をチェックして、それが `RVExcelDataSourceItem` であるかどうかを確認します。そうである場合は、既存の `RVDataSourceItem.ResourceItem` を取得し、その `Title` プロパティを確認します。タイトルが「SalesCloudExcel File」の場合、新しい `RVLocalFileDataSourceItem` を作成し、`Uri` を新しいローカル Excel ファイルの場所に設定します。ローカル Excel ファイル データ ソース項目のタイトルを設定した後、`RVExcelDataSourceItem.ResourceItem` を新しく作成した `RVLocalFileDataSourceItem` に置き換えます。

```java
public class LocalSampleDataSourceProvider implements IRVDataSourceProvider {

	public RVDashboardDataSource changeDataSource(IRVUserContext userContext, RVDashboardDataSource dataSource) {

		return null;
	}

	public RVDataSourceItem changeDataSourceItem(IRVUserContext userContext, String dashboardsID, RVDataSourceItem dataSourceItem) {

		if (dataSourceItem instanceof RVExcelDataSourceItem)
		{
			RVExcelDataSourceItem excelDataSourceItem = (RVExcelDataSourceItem)dataSourceItem;
			RVDataSourceItem resourceItem = (RVDataSourceItem)excelDataSourceItem.getResourceItem();

			if (resourceItem.getTitle() == "Sales Cloud Excel File")
			{
				RVLocalFileDataSourceItem localItem = new RVLocalFileDataSourceItem();
				localItem.setUri("local:/SalesLocalExcelFile.xlsx");
				localItem.setTitle(resourceItem.getTitle());
				excelDataSourceItem.setResourceItem(localItem);
				
				return (RVDataSourceItem)excelDataSourceItem;
			}
		}
		return null;
	}
}
```
