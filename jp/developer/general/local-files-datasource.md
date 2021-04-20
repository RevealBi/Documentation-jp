## エクスポートされたダッシュボードにローカルの Excel ファイルと csv ファイルのデータを入力

### 概要

**Reveal アプリ**でダッシュボードを作成するとき、クラウドに保存されている Excel または CSV ファイルを使用してデータを入力することがよくあります。   
ダッシュボードをエクスポートしてカスタム アプリケーションに組み込んだ後、これらのファイルをローカル ディレクトリに移動し、Reveal SDK を使用してアクセスし、ローカル データ ソースとして設定できます。

### 手順
ローカルの Excel ファイルと CSV ファイルを使用してエクスポートされた ダッシュボードにデータを入力するには、次の手順に従う必要があります。
1. [**SDK 用のダッシュボードの取得**](~/jp/developer/general/get-dashboards.md)の説明に従って、**ダッシュボード ファイルをエクスポートします**。 
2. [**ダッシュボードファイルの読み込み**](~/jp/developer/desktop-sdk/using-the-desktop-sdk/loading-dashboards.md) (WPF の場合) または [**Web SDK をはじめて使用する**](~/jp/developer/web-sdk/create-first-app.md) (Web の場合) の説明に従って、アプリケーションに**ダッシュボードを読み込みます**。
3. ダッシュボードの作成に使用した**ファイルをクラウド ストレージからダウンロードし**、ローカル フォルダーにコピーします。   
UpMedia サンプル アプリケーションと同じフォルダーを使用することをお勧めします。  
 - WPF アプリケーションでは、*DataSources* フォルダーを使用します。  
 - Web アプリケーションでは、*wwwroot/App_data/RvLocalFiles* フォルダーを使用します。  
4. プロジェクトに**新しい *CloudToLocalDatasourceProvider* クラスを追加します**。  
5. 以下の**コード** セクションの関連するスニペットから**実装コードをコピーします**。
6. *RevealSdkContext* クラスの ***DataSourceProvider* プロパティを *CloudToLocalDatasourceProvider* に設定します**:   

``` csharp
  public override IRVDataSourceProvider DataSourceProvider => new CloudToLocalDatasourceProvider();        
```

### コード
WPF の CloudToLocalDatasourceProvider:
``` csharp
    public class CloudToLocalDatasourceProvider : IRVDataSourceProvider
    {
        public Task<RVDataSourceItem> ChangeDashboardFilterDataSourceItemAsync(RVDashboardFilter filter, RVDataSourceItem dataSourceItem)
        {
            return ProcessDataSourceItem(dataSourceItem);
        }
        public Task<RVDataSourceItem> ChangeVisualizationDataSourceItemAsync(RVVisualization visualization, RVDataSourceItem dataSourceItem)
        {
            return ProcessDataSourceItem(dataSourceItem);
        }
        protected Task<RVDataSourceItem> ProcessDataSourceItem(RVDataSourceItem dataSourceItem)
        {
            // Check if the data source item is excel or csv file. Return the original data source item unchanged if it is not.
            if (dataSourceItem is RVExcelDataSourceItem == false &&
                dataSourceItem is RVCsvDataSourceItem == false)
            {
                return Task.FromResult(dataSourceItem);
            }

            var resourceBased = dataSourceItem as RVResourceBasedDataSourceItem;
            var resourceItem = resourceBased?.ResourceItem as RVDataSourceItem;
            var title = resourceItem?.Title;

            if (string.IsNullOrEmpty(title))
            {
                return Task.FromResult(dataSourceItem);
            }

            var localItem = new RVLocalFileDataSourceItem();
            // add comment what the local folder can be
            localItem.Uri = @"local:/" + title;
            // add comment about the title
            localItem.Title = title;
            resourceBased.ResourceItem = localItem;

            return Task.FromResult(dataSourceItem);
        }

    }
```

WEB の CloudToLocalDatasourceProvider (.Net サーバー側):
``` csharp
    public class CloudToLocalDatasourceProvider : IRVDataSourceProvider
    {
        public Task<RVDataSourceItem> ChangeDashboardFilterDataSourceItemAsync(string userId, string dashboardId, RVDashboardFilter filter, RVDataSourceItem dataSourceItem)
        {
            return ProcessDataSourceItem(dataSourceItem);
        }

        public Task<RVDataSourceItem> ChangeVisualizationDataSourceItemAsync(string userId, string dashboardId, RVVisualization visualization, RVDataSourceItem dataSourceItem)
        {
            return ProcessDataSourceItem(dataSourceItem);
        }

        protected Task<RVDataSourceItem> ProcessDataSourceItem(RVDataSourceItem dataSourceItem)
        {
            // Check if the data source item is excel or csv file. Return the original data source item if not.
            if (dataSourceItem is RVExcelDataSourceItem == false &&
                dataSourceItem is RVCsvDataSourceItem == false)
            {
                return Task.FromResult(dataSourceItem);
            }

            var resourceBased = dataSourceItem as RVResourceBasedDataSourceItem;
            var resourceItem = resourceBased?.ResourceItem as RVDataSourceItem;
            var title = resourceItem?.Title;

            if (string.IsNullOrEmpty(title))
            {
                return Task.FromResult(dataSourceItem);
            }

            var localItem = new RVLocalFileDataSourceItem();
            localItem.Uri = @"local:/" + title;
            localItem.Title = title;
            resourceBased.ResourceItem = localItem;

            return Task.FromResult(dataSourceItem);
        }
    }
```  

  > [!NOTE] *CloudToLocalDatasourceProvider* は、Excel ファイルと CSV ファイルのみを自動的に置き換えます。ファイルは、ダッシュボードの作成に使用したものと同じである必要があります。他のファイル タイプまたはデータ ソースへの呼び出しは変更されません。オプションで、Excel および csv データ ソース ファイルのコンテンツを変更できますが、ファイル **スキーマ**は**同じまま**である必要があります。一部の視覚化に MSSQL データ ベースを使用する場合は、資格情報を構成する必要があります。