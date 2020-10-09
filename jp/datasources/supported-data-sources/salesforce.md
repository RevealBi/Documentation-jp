## Salesforce

Salesforce データ ソースを選択すると、以下のログイン プロンプトが表示されます。

<img src="images/salesforce-login-prompt.png" alt="Salesforce login prompt" width="100%"/>

ログイン情報を*入力*してサインインをクリックします。

ID 認証が有効な場合は、送信された**確認コード**を入力するプロンプトが表示されます。ID 認証についての情報は、[Salesforce ヘルプ](https://help.salesforce.com/articleView?id=security_activation_about.htm&type=5)をご覧ください。

認証プロンプトが表示されます。*許可*をクリックしてください。

### データの設定

ログイン後、次のダイアログで Salesforce データを設定できます。

<img src="images/set-up-data-salesforce.png" alt="Set up your data dialog" width="100%"/>

ここで、必要な Salesforce オブジェクトを選択できます。

  - *人気のオブジェクト* - このカテゴリでは、ユーザーが最もよく使用する 7 つのオブジェクトをすばやく選択できます。

  - *すべてのオブジェクト* - このカテゴリには、Salesforce アカウントに含まれるオブジェクトの完全なリストが表示されます。提供されている検索を使用して、必要なオブジェクトをすばやく見つけることができます。

#### レポートの使用

表示形式エディターで使用するレポートを選択した後、次のダイアログでパラメーターの値を設定する必要があります:

<img src="images/filters-set-dialog.png" alt="A dialog showing filters from Salesforce to be configured" width="100%"/>

リストに表示されるパラメーター (_Show me_、_Probability_ など) は、レポートのフィルターです。レポート フィルターは、ユーザーがレポートに表示するデータを制御するために設定された条件です。Reveal では、フィルタリングされたデータは、表示形式エディターのチャートで使用されます。

上のダイアログでは、フィルターは Salesforce のデフォルト値で事前設定されています。これらの値を変更するには、各フィルターの横にあるドロップダウンを使用します。

その後、データソースを [編集] を選択することで、表示形式エディターでレポート フィルターの値を変更できます (以下を参照)。

<img src="images/edit-salesforce-data-source.png" alt="Edit your data source in the Visualization editor" width="100%"/>