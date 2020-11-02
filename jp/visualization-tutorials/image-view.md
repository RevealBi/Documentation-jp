## 画像ビューを作成する方法

このチュートリアルでは、サンプル スプレッドシートを使用して画像の表示形式を作成する方法を説明します。

<img src="images/ImageVisualizationDashboard_All.png" alt="ImageVisualizationDashboard\_All.png" width="80%"/>

### 重要なコンセプト

[データ表示] セクションに述べたように、画像ビュー は URL へ要求を送信して、埋め込みのブラウザーで結果を表示します。したがって、データソースに以下の項目が必要です:

  - ウィジェットに表示される Web リソースへのリンク。

  - リンクを**データセットの最初の行**に含みます。

### サンプル データソース

このチュートリアルでは、[Reveal チュートリアル スプレッドシート](http://download.infragistics.com/reportplus/help/samples/Reveal_Visualization_Tutorials.xlsx)の「Image View」シートを使用します。

>[!NOTE]
>このリリースでは、ローカル ファイルとしての Excel ファイルはサポートされていません。チュートリアルを実行するには、サポートされているクラウド サービスのいずれかにファイルをアップロードするか、[Web リソース](~/jp/datasources/supported-data-sources/web-resource.html)として追加してください。

### イメージ ビューを作成する方法

|                                          |                                                                                                |                                                                                                                                                      |
| ---------------------------------------- | ---------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------- |
| 1\. **ダッシュボードを作成する**               | <img src="images/Tutorials-Create-New-Dashboard.png" alt="Tutorials-Create-New-Dashboard" width="80%"/>                   | ダッシュボード ビューアーで、[ダッシュボード] 画面の右上隅にある [+ ダッシュボード] ボタンを選択します。|
| 2\. **データソースを構成する**       | <img src="images/Tutorials-Select-Data-Source.png" alt="Tutorials-Select-Data-Source" width="80%"/>                       | [新しい表示形式] ウィンドウで、右下隅の [+ データソース] ボタンを選択し、データソースを選択します。                                       |
| 3\. **チュートリアル スプレッドシートを選択する** | <img src="images/Tutorials-Select-Image-View-Spreadsheet.png" alt="Tutorials-Select-Image-View-Spreadsheet" width="80%"/> | データソースを設定したら、**Reveal チュートリアル スプレッドシート**を選択します。次に、Image View シートを選択し、[データを選択] を選択します。                               |
| 4\. **表示形式メニューを開く**     | <img src="images/Tutorials-Select-Change-Visualization.png" alt="Tutorials-Select-Change-Visualization" width="80%"/>     | 表示形式エディターのトップ バーで**グリッド アイコン**を選択します。                                                                                |
| 5\. **表示形式を選択する**        | <img src="images/Tutorial-Image-View-Select.png" alt="Tutorial-Image-View-Select" width="80%"/>                           | デフォルトで、表示形式のタイプは**グリッド**に設定されています。**[画像]** オプションを選択してください。                                                               |
| 6\. **データを構成する**               | <img src="images/Tutorials-ImageView-Organizing-Data.png" alt="Tutorials-ImageView-Organizing-Data" width="80%"/>         | 使用可能なフィールドのいずれかを **URL** にドラッグします。                                                                                                       |
