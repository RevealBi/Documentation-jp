## OData Feed

OData サービスのデータソースを設定するには、以下の情報が必要です。

![Enter OData Service Details dialog](images/enter-OData-service-details.png)

1.  **Default name** of the data source: Your data source name will be displayed in the list of accounts in the previous dialog. By default, Reveal names it *OData Feed*. You can change it to your preference.


2.  **URL**: サービスの URL (Northwind OData Test Service の <http://services.odata.org/Northwind/Northwind.svc> など)。

3.  **資格情報**: 資格情報を選択した後、OData Service の資格情報を入力するか、既存の資格情報 (適用可能な場合) を選択できます。

      - **名前**: データソース アカウントの名前。以前のダイアログのアカウントのリストに表示されます。

      - *(オプション)* **ドメイン**: ドメイン名 (適用可能な場合)。

      - **ユーザー名**: OData Service のユーザー アカウント (該当する場合)。

      - **パスワード**: OData Service にアクセスするためのパスワード (該当する場合)。

準備ができたら、**[アカウントの作成]**を選択します。**[接続テスト]** を選択すると、アカウントがデータソースに到達しているかどうかを確認できます。

保護された OData サービス データソースの *OAuth 2 / OIDC アカウント*を設定するには、[このトピック](OAuth-2-OIDC-User-Authentication.md)を参照してください。

### オープン型の列

Reveal は、動的な[*オープン型の列*](https://docs.microsoft.com/ja-jp/aspnet/web-api/overview/odata-support-in-aspnet-web-api/odata-v4/use-open-types-in-odata-v4)を持つ OData フィードをサポートします。動的な OData フィードを変更した後、ダッシュボードを更新するだけで新しいデータが取得されます。

以下の例は、動的な Odata サンプルの [1 つ](https://services.odata.org/V3/OData/\(S\(bwrmr2ccg0nex5gmubqxjkkz\)\)/OData.svc/)に基づいて作成されます。
最初に 3 つのカテゴリを持つ 2 つのフィールド (**ID** および **Name**) の表示形式が作成されました。

![ODataOpenTypesSampleV3\_All](images/ODataOpenTypesSampleV3_All.png)

いくつかのレコードが [Postman](https://www.odata.org/getting-started/learning-odata-on-postman/) によって Categories セクションに追加されました。変更後、ダッシュボードが更新され、新しいレコードが表示されました。

![ODataRefreshedOpenTypeV3\_All](images/ODataRefreshedOpenTypeV3_All.png)

OData のオープン型の詳細については、[こちら](https://docs.microsoft.com/ja-jp/aspnet/web-api/overview/odata-support-in-aspnet-web-api/odata-v4/use-open-types-in-odata-v4)を参照してください。

### 関数の使用

OData サービスによって公開されるように設定した関数は、データソースの  **[可視化データ]** メニューの **[関数]** タブに表示されます。

![OData Functions tab in the Set up your entity dialog](images/OData-functions.png)

関数によっては、データを取得するために 1 つ以上の値を入力する必要がある場合があります。V3 OData サンプルには、結果を得るために**評価**値を入力する必要がある以下のサンプル関数が含まれています。

![Setting up rating value of a function and Function preview dialog](images/OData-function-sample.png)

準備ができたら、表示形式エディターは関数条件に一致するデータソースのフィールドを読み込みます。

![Odata function used in the Visualization editor](images/Odata-get-products-by-rating.png)

OData 関数の詳細については、[こちら](https://docs.microsoft.com/ja-jp/aspnet/web-api/overview/odata-support-in-aspnet-web-api/odata-v4/odata-actions-and-functions)を参照してください。

