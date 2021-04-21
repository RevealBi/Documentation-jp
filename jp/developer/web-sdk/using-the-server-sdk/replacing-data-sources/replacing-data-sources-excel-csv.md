## Excel および CSV ファイルのデータ ソースの置き換え

### 概要

Reveal アプリでダッシュボードを作成するとき、クラウドに保存されている Excel または CSV ファイルを使用してデータを入力することがよくあります。  
ダッシュボードをエクスポートしてカスタム アプリケーションに組み込んだ後、これらのファイルをローカル ディレクトリに移動し、**Reveal SDK** を使用してアクセスし、ローカル データ ソースとして設定できます。

### 手順
ローカルの Excel ファイルと CSV ファイルを使用してエクスポートされた ダッシュボードにデータを入力するには、次の手順に従う必要があります。
1. [**SDK 用のダッシュボードの取得**](~/jp/developer/general/get-dashboards.md)の説明に従って、**ダッシュボード ファイルをエクスポートします**。
2. [**初めてのアプリ作成**](~/jp/developer/web-sdk/create-first-app.md)の説明に従って、アプリケーションに**ダッシュボードを読み込みます**。
3. ダッシュボードの作成に使用した**ファイルをクラウド ストレージからダウンロードし**、ローカル フォルダーにコピーします。 
4. **ローカル フォルダー名を *LocalStoragePath* プロパティの値として設定します**。これについての詳細には、[**セットアップと構成 (サーバー) - サーバー SDK を初期化**](~/jp/developer/web-sdk/setup-configuration.md#3-initializing-the-server-sdk)をご覧ください。  
5.  プロジェクトに**新しい *CloudToLocalDatasourceProvider* クラスを追加します**。  
6. 以下の**コード** セクションの関連するスニペットから**実装コードをコピーします**。
7. *RevealSdkContext* クラスの ***DataSourceProvider* プロパティを *CloudToLocalDatasourceProvider* に設定します**:   

``` csharp
  public override IRVDataSourceProvider DataSourceProvider => new CloudToLocalDatasourceProvider();        
```

### コード

``` csharp
    public class CloudToLocalDatasourceProvider : IRVDataSourceProvider
    {
        public Task<RVDataSourceItem> ChangeDashboardFilterDataSourceItemAsync(string userId, string dashboardId, 
                        RVDashboardFilter filter, RVDataSourceItem dataSourceItem)
        {
            return ProcessDataSourceItem(dataSourceItem);
        }

        public Task<RVDataSourceItem> ChangeVisualizationDataSourceItemAsync(string userId, string dashboardId, 
                        RVVisualization visualization, RVDataSourceItem dataSourceItem)
        {
            return ProcessDataSourceItem(dataSourceItem);
        }

        protected Task<RVDataSourceItem> ProcessDataSourceItem(RVDataSourceItem dataSourceItem)
        {
            // Return data source unless it is an excel or csv file.
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

            // The SDK uses the local folder set as LocalStoragePath.
            localItem.Uri = @"local:/" + title;

            // The title assigned here is the original data source name.
            localItem.Title = title;
            resourceBased.ResourceItem = localItem;

            return Task.FromResult(dataSourceItem);
        }
    }
```  
  > [!NOTE] 
  > *CloudToLocalDatasourceProvider* は、Excel ファイルと CSV ファイルのみを自動的に置き換えます。他のファイル タイプまたはデータ ソースは変更されません。置換ファイルは、ダッシュボードの作成に使用したものと同じであるか、**同じスキーマ**を共有しているがデータが異なる新しいファイルである必要があります。
