---
title: Slingshot で Microsoft Dynamics CRM を構成する方法
_description: Microsoft Dynamics CRM を構成して使用する方法を説明します。
_language: ja
---

# Microsoft Dynamics CRM

Microsoft Dynamics CRM データ ソースを構成するには、以下の情報が必要です。

<img src="images/add-dynamics-crm-connection-dialog.png" alt="A dialog for adding the credentials for Microsoft Dynamics CRM" class="responsive-img" width="50%"/>

1.  データ ソースの**デフォルト名**: データ ソース名は前のダイアログのアカウントのリストに表示されます。デフォルトでは、Reveal は *Microsoft Dynamics CRM* という名前を付けます。好みに合わせて変更できます。

2.  **[URL]**: Dynamics CRM サイトの URL (<http://crm.YourCompany.local> など)。

3.  **[資格情報]**: [資格情報] を選択した後、Microsoft Dynamics CRM サイトの資格情報を入力するか、既存の資格情報 (適用可能な場合) を選択できます。

     - **ユーザー名**: Dynamics CRM web サイトのユーザー アカウントまたはドメイン名。

      - **パスワード**: Dynamics CRM web サイトのパスワード。

      - **Alias**: データ ソース アカウントの名前。以前のダイアログのアカウントのリストに表示されます。

準備ができたら、**[追加]** を選択します。

## データの設定

ログイン後、次のダイアログで Microsoft Dynamics CRM データを設定できます:

<img src="images/microsoft-dynamics-crm-details.png" alt="A dialog containing lists of entities" class="responsive-img" width="57%"/>

ここで、必要な Microsoft Dynamics CRM エンティティを選択できます:

- 人気のエンティティ - このカテゴリでは、ユーザーが最もよく使用するエンティティをばやく選択できます。
- すべてのエンティティ - このカテゴリには、Microsoft Dynamics CRM アカウントに含まれるエンティティの完全なリストが表示されます。提供されている検索を使用して、必要なエンティティをすばやく見つけることができます。

## 表示形式エディターでの作業

エンティティを選択すると、**表示形式エディター**に移動します。ここでダッシュボードを作成できます。

デフォルトでは、*柱状*表示形式が選択されます。それを選択して、別のチャート タイプを選択できます。

<img src="images/microsoft-dynamics-visualization-editor.png" alt="Using the data from Microsoft Dynamics CRM in the visualization editor" class="responsive-img" width="85%"/>
