---
title: How to configure an Azure SQL data source in Slingshot
_description: : A roadmap to configuring an Azure SQL data source to use it for your great visualizations.
_language: ja
---

# Azure SQL

> [!NOTE] 
>**Web の制限**。*Reveal Web* アプリでは、公的にアクセス可能な Azure SQL アドレスにのみ接続できます。Azure SQL アドレスが一般公開 (プライベートまたは会社のイントラネットでホストされているなど) に制限されている場合は、*Reveal Desktop*、*iOS*、または *Android* を使用して接続できます。Reveal を実行しているデバイスは、SQL Server アドレスにアクセスできる必要があります。この制限は、*Reveal Embedded* には適用されません。

## Azure SQL への接続

Azure SQL データ ソースを構成するには、以下の情報が必要です。

<img src="images/enter-Azure-SQL-details.png" alt="Opening Reveal's AzureSQL data source configuration screen" class="responsive-img"/>

1.  **データ ソース名**: このフィールドはデータ ソース リストに表示されます。

2.  **[サーバー]**: コンピューター名またはサーバーを実行しているコンピューターに割り当てられた IP アドレス。

3.  **[ポート]**: 該当する場合、サーバー ポートの詳細。情報が入力されない場合、Reveal はデフォルトでヒント テキスト (1433) のポートに接続します。

4.  **[資格情報]**: [資格情報] を選択した後、Azure SQL の資格情報を入力するか、既存の資格情報 (適用可能な場合) を選択できます。

  - データ ソースの**デフォルト名**: データ ソース名は前のダイアログのアカウントのリストに表示されます。デフォルトでは、Reveal は *Microsoft Azure SQL Database* という名前を付けます。好みに合わせて変更できます。

  - (オプション) の **[ドメイン]**:  ドメイン名 (該当する場合)。

  - **[ユーザー名]**: Azure SQL のユーザー アカウント。

  - **[パスワード]**: Azure SQL にアクセスするためのパスワード。

5.  (条件付き) **[データベース]**: アカウントに接続すると、データベースを選択できるようになります (複数のデータベースがある場合)。

準備ができたら、**[作成して使用]** を選択します。

## 詳細情報

以下の詳細については、Reveal の両データ ソースは同様に機能するため、[**SQL Server**](microsoft-sql-server.html#how-to-find-server) を参照してください。

  - サーバー情報を見つける方法

  - ビューの作業

  - 保管されたプロシージャの作業

