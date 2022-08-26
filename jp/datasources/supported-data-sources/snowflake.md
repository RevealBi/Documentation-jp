# Snowflake

## Snowflake への接続

Snowflake データ ソースを構成するには、最初に次の情報を入力してサーバーに接続する必要があります:

<img src="images/add-snowflake-server.png" alt="Configure Snowflake Server details" class="responsive-img" width="55%"/>

1.  **Account**: Your snowflake account without the region or cloud provider information. For example, it should be similar to \<account_name\> instead of _\<account_name\>.us-east-1.snowflakecomputing.com_.

2.  **[ホスト]**:  必須ではありませんが、値が指定されていない場合は _\<28/>.snowflakecomputing.com_ が使用されます。米国西部地域にいない場合、またはグローバル URL を使用する場合は、_\<account_name\>.\<region_id\>.snowflakecomputing.com_ の形式でホストを指定する必要があります。

3.  **[資格情報]**: *資格情報*を選択した後、*Snowflake* サーバーの資格情報を入力するか、既存の資格情報 (利用可能な場合) を選択できます。

 <img src="images/add-snowflake-credentials.png" alt="A dialog where you can add your credentials" class="responsive-img" width="60%"/>

- **Username**: the user account for the *Snowflake* server or the name of the domain.

- **[パスワード]**:  *Snowflake*サーバーにアクセスするためのパスワード。

- **Alias**: the name for your data source account. It will be
        displayed in the list of accounts in the previous dialog.

## Snowflake データ ソースの構成

1.  データベースの横にある空の円をマークして、**データベースを選択します**。

  <img src="images/snowflake-database-dialog.png" alt="Select a database dialog" class="responsive-img" width="55%"/>

2.  **Select a table** from the database. Use the icon on the right, next to the empty circles, to preview the data.

  <img src="images/snowflake-data-source-details.png.png" alt="Select a table dialog" class="responsive-img" width="55%"/>

これで、Snowflake から取得したデータを使用して表示形式の構築を開始できる**表示形式エディター**が表示されます。
