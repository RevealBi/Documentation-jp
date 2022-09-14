---
title: Slingshot で Microsoft Reporting Services に接続する方法
_description: 既存の Microsoft Reporting Services を使用して優れた表示形式を作成する方法を説明します。
_language: ja
---

# Microsoft Reporting Services

既存の Microsoft Reporting Services (SSRS) レポートをダッシュボードに PDF ファイルとして埋め込むか、レポートからデータを取得して表示形式を作成して、Reveal で使用できます。

## Microsoft Reporting Services への接続

Microsoft Reporting Services (SSRS) データ ソースを構成するには、以下の情報が必要です。

<img src="images/add-microsoft-reporting-services-as-data-source.png" alt="Set up menu for Microsoft Reporting Services data source" class="responsive-img" width="55%"/>

1.  **[URL]**: サーバーの URL。

2.  **[資格情報]**: 新しいダイアログが表示されます。Microsoft Reporting Services サーバーの新しい資格情報を入力、または既存の情報を入力します

## レポートの設定

Microsoft Reporting Services レポートへの接続を構成した後、以下のダイアログが開き、操作するデータを選択するよう求められます。

<img src="images/microsoft-reporting-services-data-source-details.png" alt="Select a Report dialog" class="responsive-img" width="55%"/>

レポートとフォルダーの順序は、Microsoft Reporting Services アカウントの順序とよく似ています。

データに応じて、以下に示すようにレポートの特定の **[パラメーター]** を構成する必要があります。

<img src="images/microsoft-reporting-services-parameters.png" alt="Set up parameters and choose an output format dialog" class="responsive-img" width="55%"/>

レポートのパラメーターを選択/入力した後、レポートを*表示形式エディター*に読み込む形式を選択できます。

  - **[PDF として読み込み]** - レポートを PDF 文書として表示形式エディターに埋め込みます。表示形式エディター内で PDF をスクロール、ズーム、ダウンロード、または印刷できます。

  <img src="images/microsoft-reporting-services-pdf.png" alt="Microsoft reporting services in pdf format in the Visualization editor" class="responsive-img" width="55%"/>

  - **[データの読み込み]** - レポートのデータは標準形式で読み込まれ、表示形式を作成するためのフィールドを提供します。

  <img src="images/microsoft-reporting-services-visualization-editor.png" alt="Microsoft reporting services data in the Visualization editor" class="responsive-img" width="55%"/>

>[!NOTE]
>表示形式エディターでデータ ソースを編集: 読み込み後は変更できないため、レポート形式 (pdf または data) を選択してください。データ ソースを*編集する*場合、レポートのパラメーターの構成のみ変更できます。

## Working in the Visualization editor

By default, the *Column* visualization will be selected. You can select it in order to choose another chart type. 

<img src="images/microsoft-reporting-services-chart-types.png" alt="List of chart types while using Microsoft Reporting Services as data source" class="responsive-img" width="50%"/>

Based on the vusialization that you have chosen, you will see different types of fields.

Once you are ready with your visualization, click/tap on the checkmark in the top right corner to save it as a dashboard. 

In this case we saved the dashboard in **My Analytics** > **My Dashboards** > **Accounting**.

<img src="images/microsoft-reporting-services-my-analytics-dashboard.png" alt="A dashboard in the My Analytics section created while using Microsoft Reporting Services" class="responsive-img" width="50%"/>
