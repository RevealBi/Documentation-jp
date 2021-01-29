## OData フィード

### OData フィードへの接続

OData フィードのデータ ソースを設定するには、以下の情報が必要です。

<img src="images/enter-OData-service-details.png" alt="Enter OData Service Details dialog" width="80%"/>

1.  データ ソースの **デフォルト名**: データ ソース名は前のダイアログのアカウントのリストに表示されます。デフォルトでは、Reveal は **OData フィード** という名前を付けます。好みに合わせて変更できます。


2.  **[URL]**: サービスの URL (Northwind OData Test Service の <http://services.odata.org/Northwind/Northwind.svc> など)。

3.  **[資格情報]**: [資格情報] を選択した後、OData Service の資格情報を入力するか、既存の資格情報 (適用可能な場合) を選択できます。

      - **[名前]**: データ ソース アカウントの名前。以前のダイアログのアカウントのリストに表示されます。

      - (オプション) の **[ドメイン]**: ドメイン名 (適用可能な場合)。

      - **[ユーザー名]**: OData Service のユーザー アカウント (該当する場合)。

      - **[パスワード]**: OData Service にアクセスするためのパスワード (該当する場合)。

準備ができたら、**[作成して使用]** を選択します。

保護された OData フィード データ ソースの *OAuth 2 / OIDC アカウント*を設定するには、[このトピック](/jp/datasources/OAuth-2-OIDC-User-Authentication.html)を参照してください。

### オープン型の列

Reveal は、動的な[*オープン型の列*](https://docs.microsoft.com/ja-jp/aspnet/web-api/overview/odata-support-in-aspnet-web-api/odata-v4/use-open-types-in-odata-v4)を持つ OData フィードをサポートします。動的な OData フィードを変更した後、ダッシュボードを更新するだけで新しいデータが取得されます。

以下の例は、動的な Odata サンプルの [1 つ](https://services.odata.org/V3/OData/\(S\(bwrmr2ccg0nex5gmubqxjkkz\)\)/OData.svc/)に基づいて作成されます。
最初に 3 つのカテゴリを持つ 2 つのフィールド (**ID** および **Name**) の表示形式が作成されました。

<img src="images/ODataOpenTypesSampleV3_All.png" alt="ODataOpenTypesSampleV3\_All" width="80%"/>

いくつかのレコードが [Postman (英語)](https://www.odata.org/getting-started/learning-odata-on-postman/) によって Categories セクションに追加されました。変更後、ダッシュボードが更新され、新しいレコードが表示されました。

<img src="images/ODataRefreshedOpenTypeV3_All.png" alt="ODataRefreshedOpenTypeV3\_All" width="80%"/>

OData のオープン型の詳細については、[こちら](https://docs.microsoft.com/ja-jp/aspnet/web-api/overview/odata-support-in-aspnet-web-api/odata-v4/use-open-types-in-odata-v4)を参照してください。

### 関数の使用

OData フィードによって公開されるように設定した関数は、データ ソースの  **[新しい表示形式]** メニューの **[関数]** タブに表示されます。

<img src="images/OData-functions.png" alt="OData Functions tab in the Set up your entity dialog" width="80%"/>

関数によっては、データを取得するために 1 つ以上の値を入力する必要がある場合があります。V3 OData サンプルには、結果を得るために **rating** の値を入力する必要がある以下のサンプル関数が含まれています。

<img src="images/OData-function-sample.png" alt="Setting up rating value of a function and Function preview dialog" width="80%"/>

準備ができたら、表示形式エディターは関数条件に一致するデータ ソースのフィールドを読み込みます。

<img src="images/Odata-get-products-by-rating.png" alt="Odata function used in the Visualization editor" width="80%"/>

OData 関数の詳細については、[こちら](https://docs.microsoft.com/ja-jp/aspnet/web-api/overview/odata-support-in-aspnet-web-api/odata-v4/odata-actions-and-functions)を参照してください。

