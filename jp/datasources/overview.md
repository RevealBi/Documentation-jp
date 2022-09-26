---
title: Slingshot でデータ ソースに接続する方法
_description: さまざまなエンタープライズ データ ソースに接続して使用する方法を学びます。
_language: ja
---

# データ ソース

データ ソースはデータの送信元です。Reveal は、さまざまなエンタープライズ データ ソースに接続する機会を提供します。分析ツール、コンテンツ マネージャー、クラウド サービス、CRM、データベース、スプレッドシート、および公開用のデータ ソースから選択できます。

## データ ソースに接続

データ ソースから情報を取得し、それを表示形式に使用するには、まずデータ ソースに接続する必要があります。データ ソースに接続すると、**[データ ソース]** メニューに保存され、次に必要になったときにすばやく選択できます。

データ ソースに接続するには、以下の手順を実行します:

1. **[分析]** またはダッシュボードを作成するワークスペースに移動します。
2. **[+ ダッシュボード]** または **[ダッシュボードの作成]** **(分析)** の青いボタンをクリックまたはタップします。

   <img src="images/data-sources-my-analytics.png" alt="Dashboard button in my analytics" class="responsive-img" width="70%" height="80%"/>
3. **[データ ソース]** ダイアログに、最近使用したデータ ソースのリストが表示されます。新しい接続を作成するには、右側の **[+ データ ソース]** ボタンを選択します。

   <img src="images/data-sources-screen.png.png" alt="Sample data sources" class="responsive-img" width="60%"/>

データ ソース プロバイダーを選択すると、データ ソースを**設定**するように求められます。設定に関しては、選択したデータ ソースの設定に関する記事をご覧ください (以下のリストを参照)。

   - [Amazon Athena](~/jp/datasources/supported-data-sources/athena.md)

   - [Amazon Redshift](~/jp/datasources/supported-data-sources/redshift.html)

   - [Amazon S3](~/jp/datasources/supported-data-sources/amazon-s3.md)

   - [Box](~/jp/datasources/supported-data-sources/box.md)

   - [Dropbox](~/jp/datasources/supported-data-sources/dropbox.md)

   - [Google Ads](~/jp/datasources/supported-data-sources/google-ads.md)

   - [Google Analytics](~/jp/datasources/supported-data-sources/google-analytics.html)

   - [Google BigQuery](~/jp/datasources/supported-data-sources/google-bigquery.html)

   - [Google Drive](~/jp/datasources/supported-data-sources/google-drive.html)
  
   - [Hubspot](~/jp/datasources/supported-data-sources/hubspot.html)
  
   - [Marketo](~/jp/datasources/supported-data-sources/marketo.html)

   - [Microsoft Analysis Services](~/jp/datasources/supported-data-sources/microsoft-analysis-services.html)
  
   - [Microsoft Azure Analysis Services](~/jp/datasources/supported-data-sources/microsoft-azure-analysis-services.html)
  
   - [Microsoft Azure Synapse Analytics](~/jp/datasources/supported-data-sources/microsoft-azure-synapse-analytics.html)
  
   - [Microsoft Azure SQL Database](~/jp/datasources/supported-data-sources/azure-sql.md)*

   - [Microsoft Dynamics CRM](~/jp/datasources/supported-data-sources/microsoft-dynamics-crm.html)

   - [Microsoft Reporting Services (SSRS)](~/jp/datasources/supported-data-sources/microsoft-reporting-services.html)

   - [Microsoft SQL Server](~/jp/datasources/supported-data-sources/microsoft-sql-server.html)*

   - [MySQL](~/jp/datasources/supported-data-sources/mysql.html)*

   - [OData フィード](~/jp/datasources/supported-data-sources/odata-feed.html)

   - [OneDrive](~/jp/datasources/supported-data-sources/onedrive.html)

   - [Oracle](~/jp/datasources/supported-data-sources/oracle.html)*

   - [PostgreSQL](~/jp/datasources/supported-data-sources/postgresql.html)*
  
   - [Quickbooks](~/jp/datasources/supported-data-sources/quickbooks.html) 

   - [REST API](~/jp/datasources/supported-data-sources/rest-api.html)

   - [Salesforce](~/jp/datasources/supported-data-sources/salesforce.html)

   - [SharePoint](~/jp/datasources/supported-data-sources/sharepoint.html)
 
   - [Snowflake](~/jp/datasources/supported-data-sources/snowflake.d)

   - [Sybase](~/jp/datasources/supported-data-sources/sybase.html)*

   - [ウェブ リソース](~/jp/datasources/supported-data-sources/web-resource.html)

   - [JSON ファイル](~/jp/datasources/working-files/working-with-json-files.html)

   - [スプレッドシート](~/jp/datasources/working-files/working-with-spreadsheets.html)

## データ ソースのフィルタリング

データ ソースをフィルターするには、右上隅にあるフィルター ボタンをクリックします。

   <img src="images/data-sources-filter.png" alt="A dialog with filtering options" class="responsive-img" width="60%"/>

## 関連トピック 

- まだ接続していないデータ ソースからのデータを使用するダッシュボードを受け取りましたか? [ダッシュボードをデータ ソースに接続](connect-dashboard-to-data-source.html)トピックで開く方法を参照してください。
- 表示形式の作成途中でデータ ソースを変更することにしましたか? 表示形式エディターで別のデータ ソースに接続する方法については、[表示形式に使用するデータ ソースの変更](changing-data-source-visualization.html)を参照してください。
- 複数のデータ ソースからのデータを表示形式に使用しますか? [データ ソースを 1 つの表示形式に統合](data-blending.html)を参照してください。