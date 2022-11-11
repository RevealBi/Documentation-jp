---
title: Slingshot で画像チャートを作成する方法
_description: サンプルス プレッドシートを使用して画像チャートの表示形式を作成する方法を説明します。
_language: ja
---

# 画像チャートを作成する方法

このチュートリアルでは、サンプル スプレッドシートを使用して画像の表示形式を作成する方法を説明します。

<img src="../images/image-chart-sample.png" alt="A sample showing different image chart visualizations in one dashboard" class="responsive-img"/>

## 重要なコンセプト

[データ表示] セクションに述べたように、[画像チャート](image-chart.md)は URL へ要求を送信して、埋め込みのブラウザーで結果を表示します。したがって、データ ソースに以下の項目が必要です:

  - ウィジェットに表示されるウェブ リソースへのリンク。

  - リンクを**データセットの最初の行**に含みます。

## サンプル データ ソース

このチュートリアルでは、[Slingshot Visulization Tutorials](https://download.infragistics.com/reportplus/help/samples/Reveal_Visualization_Tutorials.xlsx) の「Image Chart」シートを使用します。

 1. In **My Analytics**, select the **+ Dashboard button** in the top right-hand corner.

    <img src="./images/button-dashboard.png" alt="Tutorials-Create-New-Dashboard" class="responsive-img" width="85%"/> 

 2. A dialog will open, contening a list of already added data source. The Visualization Tutorial file will be there as a data source if you have already used it. In case you haven't added the file, you can click/tap on **+Data Source** > **Data Files** > **+New** >**Upload** >select the file and click/tap on **Select and Continue** to include it in the list.

    <img src="images/select-your-data-source.png" alt="Tutorials-Select-Data-Source" class="responsive-img" width="85%"/>

 3. Once the data source is configured, select the *Image View* sheet.                                

    <img src="images/select-image-view.png" alt="Tutorials-Select-Image-View-Spreadsheet" class="responsive-img" width="57%"/>

 4. By default, the visualization type will be set to *Column*. Select the *Image* option.      

    <img src="../images/list-of-chart-types.png" alt="Tutorial-Image-View-Select" class="responsive-img" width="57%"/>   
                                                      
5. Drag any of the available fields into **URL**.        

   <img src="../images/image-chart-data-organization.png" alt="Tutorials-ImageView-Organizing-Data" class="responsive-img" width="57%"/>
