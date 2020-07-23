## イメージ ビューを作成する方法

このチュートリアルでは、サンプル スプレッドシートを使用しイメージ表示形式を作成する方法を説明します。

![ImageVisualizationDashboard\_All.png](images/ImageVisualizationDashboard_All.png)

### 重要なコンセプト

[データ表示] セクションに述べたように、[イメージ ビュー](image-view.md)は URL へ要求を送信して、埋め込みのブラウザーで結果を表示します。したがって、データ ソースに以下の項目が必要です:

  - ウィジェットに表示されるウェブ リソースへのリンク。

  - **データセットの最初の行**に含みます。

### サンプル データ ソース

このチュートリアルでは、[Reveal チュートリアル スプレッドシート](http://download.infragistics.com/reportplus/help/samples/Reveal_Visualization_Tutorials.xlsx)の [イメージ ビュー] のシートを使用します。

>[!NOTE]
>このリリースでは、ローカル ファイルとしての Excel ファイルはサポートされていません。チュートリアルを実行するには、サポートされている[クラウド サービス](data-sources.md)のいずれかにファイルをアップロードするか、[Web リソース](web-resource.md)として追加してください。

### イメージ ビューを作成する方法

|                                          |                                                                                                |                                                                                                                                                      |
| ---------------------------------------- | ---------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------- |
| 1\. **Create a Dashboard**               | ![Tutorials-Create-New-Dashboard](images/Tutorials-Create-New-Dashboard.png)                   | In the dashboard viewer, select the + button in the top right-hand corner of the "My Dashboards" screen. Then, select "Dashboard" from the dropdown. |
| 2\. **Configure your Data Source**       | ![Tutorials-Select-Data-Source](images/Tutorials-Select-Data-Source.png)                       | In the *New Visualization* window, select the + button in the bottom right corner and select your data source.                                       |
| 3\. **Select the Tutorials Spreadsheet** | ![Tutorials-Select-Image-View-Spreadsheet](images/Tutorials-Select-Image-View-Spreadsheet.png) | Once the data source is configured, select the **Reveal Tutorials Spreadsheet**. Then, choose the "Image View" sheet.                                |
| 4\. **Open the Visualizations Menu**     | ![Tutorials-Select-Change-Visualization](images/Tutorials-Select-Change-Visualization.png)     | Select the **grid icon** in the top bar of the Visualizations Editor.                                                                                |
| 5\. **Select your Visualization**        | ![Tutorial-Image-View-Select](images/Image-View-Select.png)                           | By default, the visualization type will be set to "Grid". Select the **Image** option.                                                               |
| 6\. **Organize your Data**               | ![Tutorials-ImageView-Organizing-Data](images/Tutorials-ImageView-Organizing-Data.png)         | Drag any of the available fields into **URL**.                                                                                                       |
