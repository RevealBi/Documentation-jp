---
title: Salesforce データ ソースの設定方法と使用方法
_description: Slingshot で Salesforce をデータ ソースとして設定および使用する方法。
_language: ja
---

# Salesforce

Salesforce データ ソースを選択すると、以下のログイン プロンプトが表示されます。

<img src="../images/salesforce-login.png" alt="Salesforce login prompt" class="responsive-img" width="50%"/>

ログイン情報を入力して [ログイン] をクリックします。

>[!NOTE] ID 認証が有効な場合は、送信された**確認コード**を入力するプロンプトが表示されます。ID 認証についての情報は、[Salesforce ヘルプ](https://help.salesforce.com/articleView?id=security_activation_about.htm&type=5)をご覧ください。

## データの設定

ログイン後、次のダイアログで Salesforce データを設定できます。

<img src="../images/salesforce-data-source-details-popular-objects.png" alt="Set up your data dialog" class="responsive-img" width="50%"/>

Slingshot で Salesforce をデータ ソースとして設定および使用する方法。

  - **[レポート]** - このカテゴリには、Salesforce アカウントからのすべてのレポートが表示されます。

  - **[人気のあるオブジェクト]** - このカテゴリでは、ユーザーが最もよく使用する 7 つのオブジェクトをすばやく選択できます。

  - **[すべてのオブジェクト]** - このカテゴリには、Salesforce アカウントに含まれるオブジェクトの完全なリストが表示されます。提供されている検索を使用して、必要なオブジェクトをすばやく見つけることができます。

## レポートの使用

表示形式エディターで使用するレポートを選択した後、パラメーターの値を設定する必要があります:

<img src="../images/salesforce-values-for-parameters-filters.png" alt="A dialog showing filters from Salesforce to be configured" class="responsive-img" width="50%"/>

リストに表示されるパラメーター (**Show me**、**Probability** など) は、レポートのフィルターです。レポート フィルターは、ユーザーがレポートに表示するデータを制御するために設定された条件です。Reveal では、フィルタリングされたデータは、**表示形式エディター**のチャートで使用されます。

上のダイアログでは、フィルターは Salesforce のデフォルト値で事前設定されています。これらの値を変更するには、各フィルターの横にあるドロップダウン メニューを使用します。

その後、データ ソースを **[編集]** を選択することで、表示形式エディターでレポート フィルターの値を変更できます (以下を参照)。

<img src="../images/edit-data-source-salesforce.png" alt="Edit your data source in the Visualization editor" class="responsive-img" width="75%"/>

## Working in the Visualization editor 

Once your data source has been added, you will be taken to the *Visualizations Editor*. Here you can build your dashboard.Note that based on the vusialization that you have chosen, you will see different types of fields.

<img src="./images/salesforce-visualization-editor.png" alt="Working in the visualization editor while using the information from a salesforce account" class="responsive-img" width="75%"/>

When you are ready with your visualization, you can click/tap on the checkmark in the top right corner to save it as a dashboard. In this case we saved the dashboard in **My Analytics** > **My Dashboards** > **Accounting**.

<img src="./images/salesforce-my-analytics.png" alt="A salesforce dashboard in the My Analytics section" class="responsive-img" width="75%"/>
