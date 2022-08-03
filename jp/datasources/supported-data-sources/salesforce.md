---
title: How to set up and use Salesforce Data Source
_description: Setting up and using Salesforce as a data source in Slingshot.
_language: ja
---

# Salesforce

Salesforce データ ソースを選択すると、以下のログイン プロンプトが表示されます。

<img src="../images/salesforce-login.png" alt="Salesforce login prompt" class="responsive-img"/>

ログイン情報を入力して [ログイン] をクリックします。

>[!NOTE] ID 認証が有効な場合は、送信された**確認コード**を入力するプロンプトが表示されます。ID 認証についての情報は、[Salesforce ヘルプ](https://help.salesforce.com/articleView?id=security_activation_about.htm&type=5)をご覧ください。

## データの設定

ログイン後、次のダイアログで Salesforce データを設定できます。

<img src="../images/salesforce-data-source-details-popular-objects.png" alt="Set up your data dialog" class="responsive-img"/>

Here you can choose from:

  - **Reports** - this category displays all the reports that come from your Salesforce account. 

  - **[人気のあるオブジェクト]** - このカテゴリでは、ユーザーが最もよく使用する 7 つのオブジェクトをすばやく選択できます。

  - **[すべてのオブジェクト]** - このカテゴリには、Salesforce アカウントに含まれるオブジェクトの完全なリストが表示されます。提供されている検索を使用して、必要なオブジェクトをすばやく見つけることができます。

## レポートの使用

表示形式エディターで使用するレポートを選択した後、パラメーターの値を設定する必要があります:

<img src="../images/salesforce-values-for-parameters-filters.png" alt="A dialog showing filters from Salesforce to be configured" class="responsive-img"/>

リストに表示されるパラメーター (**Show me**、**Probability** など) は、レポートのフィルターです。レポート フィルターは、ユーザーがレポートに表示するデータを制御するために設定された条件です。Reveal では、フィルタリングされたデータは、表示形式エディターのチャートで使用されます。

上のダイアログでは、フィルターは Salesforce のデフォルト値で事前設定されています。これらの値を変更するには、各フィルターの横にあるドロップダウン メニューを使用します。

その後、データ ソースを **[編集]** を選択することで、表示形式エディターでレポート フィルターの値を変更できます (以下を参照)。

<img src="../images/edit-data-source-salesforce.png" alt="Edit your data source in the Visualization editor" class="responsive-img"/>