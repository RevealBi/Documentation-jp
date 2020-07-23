## Microsoft SQL サーバー

Microsoft SQL サーバーデータソースを構成するには、以下の情報が必要です。

![Enter SQL Server Details](images/Enter-SQL-Server-Details.png)

1.  データ ソースの**デフォルト名**: データ ソース名は前のダイアログのアカウントのリストに表示されます。デフォルトでは、Reveal は *Microsoft SQL Server* という名前を付けます。好みに合わせて変更できます。

2.  [**サーバー**](#how-to-find-server): コンピューター名またはサーバーを実行しているコンピューターに割り当てられた IP アドレス。

3.  **ポート**: 該当する場合、サーバー ポートの詳細。情報が入力されない場合、Reveal はデフォルトでヒント テキスト (1433) のポートに接続します。

4.  **資格情報**: *資格情報*を選択した後、Microsoft SQL Server の資格情報を入力するか、既存の資格情報 (適用可能な場合) を選択できます

      - **名前**: データソース アカウントの名前。以前のダイアログのアカウントのリストに表示されます。

      - *(オプション)* **ドメイン**: ドメイン名 (適用可能な場合)。

      - **ユーザー名**: SQL サーバーのユーザー アカウント

      - **パスワード**: SQL サーバーのパスワード

    準備ができたら、**アカウントの作成**を選択します。**[接続テスト]**を選択すると、アカウントがデータソースに到達しているかどうかを確認できます。

<a name='how-to-find-server'></a>
### サーバー情報を見つける方法

以下の手順でサーバーの確認ができます。コマンドはサーバーで実行する必要があることに注意してください。

| WINDOWS                                                                                                         | LINUX                                                                                                         | MAC                                                                  |
| --------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------- |
| 1\. ファイル エクスプローラーを開きます。                                                                                     | 1\. ターミナルを開きます。                                                                                          | 1\. システム環境設定を開きます。                                         |
| 2\. マイコンピューターを右クリックしてプロパティを表示します。                                                                   | 2\. **$hostname** と入力します。                                                                                   | 2\. 共有セクションへ移動します。                                 |
| ホスト名は、「コンピューター名、ドメイン、ワークグループ設定」の下にコンピューター名として表示されます。 | ホスト名と DNS ドメイン名が表示されます。Reval では**ホスト名**のみを含めることに注意してください。 | ホスト名は、上部の「コンピューター名」の下に表示されます。 |

以下の手順で *IP アドレス*も確認できます。コマンドはサーバーで実行する必要があることに注意してください。

| WINDOWS                              | LINUX                             | MAC                                                           |
| ------------------------------------ | --------------------------------- | ------------------------------------------------------------- |
| 1\. コマンド プロンプトを開きます。           | 1\. ターミナルを開きます。              | 1\. ネットワーク アプリケーションを起動します。                                  |
| 2\. **ipconfig** と入力します。             | 2\. **$ /bin/ifconfig** と入力します。   | 2\. 接続を選択します。                                   |
| **IPv4 アドレス** はあなたの IP アドレスです。 | **Inet addr** はあなたの IP アドレスです。 | **IP アドレス** フィールドに必要な情報が提供されます。 |

<a name='working-with-views'></a>
### ビューの作業

Reveal を使用すると、テーブル全体から SQL Server データを取得できますが、代わりにテーブルまたはテーブルのセットからデータのサブセットを返す、特定の[ビュー](https://docs.microsoft.com/ja-jp/sql/relational-databases/views/views?view=sql-server-2017)を選択することもできます。

![SQLServerViews\_All](images/SQLServerViews_All.png)

上記のサンプルでは、**Alphabetical list of products** ビューに SQL サーバーの **Products** テーブルのデータの一部が含まれています。

![AlphabeticalListProductsSQLServer\_All](images/AlphabeticalListProductsSQLServer_All.png)

ビューおよび MS SQL サーバーの詳細については、[この Web サイト](https://docs.microsoft.com/ja-jp/sql/relational-databases/views/views?view=sql-server-2017)を参照してください。

### ストアド プロシージャの作業

MS SQL では、ストアド プロシージャを利用することで、特定のパラメーターを使用して、リレーショナル データベースで一連のクエリ ステートメントを実行できます。以下は、[Northwind](https://docs.microsoft.com/ja-jp/dotnet/framework/data/adonet/sql/linq/downloading-sample-databases) データを使用してテスト サーバーで実行されるサンプル ストアド プロシージャのセットです。

![SQLStoredProcedures\_All](images/SQLStoredProcedures_All.png)

たとえば、このストアド プロシージャは、**Products** テーブルの製品を、**Unit Price** で並べ替えて返します。  **ProductName** の名前は、**TenMostExpensiveProducts** に変更されました。

![StoredProcedureSampleResults\_All](images/StoredProcedureSampleResults_All.png)

この場合、ストアド プロシージャは、**Sales by Year** 情報を表示するための開始日と終了日を設定する必要があります。

![StoredProcedureSampleDates\_All](images/Stored-Procedure-Sample-Dates.png)

ストアドプロシージャおよび MS SQL サーバーの詳細については、[この Web サイト](https://docs.microsoft.com/ja-jp/sql/relational-databases/stored-procedures/stored-procedures-database-engine?view=sql-server-2017)を参照してください。

#### Reveal ストアド プロシージャの制限


  - 複数の結果セットを返すスト アドプロシージャの場合、最初の結果のみが表示されます。

  - ストアド プロシージャの[出力パラメーター](https://docs.microsoft.com/ja-jp/sql/connect/jdbc/using-a-stored-procedure-with-output-parameters?view=sql-server-2017)は無視されます。

  - 結果セットを返さないストアド プロシージャはデータソース リストに表示されますが、失敗します。