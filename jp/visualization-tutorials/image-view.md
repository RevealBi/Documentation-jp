## イメージ ビューを作成する方法

このチュートリアルでは、サンプル スプレッドシートを使用しイメージ表示形式を作成する方法を説明します。

<img src="images/ImageVisualizationDashboard_All.png" alt="ImageVisualizationDashboard\_All.png" width="100%"/>

### 重要なコンセプト

[データ表示] セクションに述べたように、[イメージ ビュー](image-view.html)は URL へ要求を送信して、埋め込みのブラウザーで結果を表示します。したがって、データ ソースに以下の項目が必要です:

  - ウィジェットに表示されるウェブ リソースへのリンク。

  - **データセットの最初の行**に含みます。

### サンプル データ ソース

このチュートリアルでは、[Reveal チュートリアル スプレッドシート](http://download.infragistics.com/reportplus/help/samples/Reveal_Visualization_Tutorials.xlsx)の [イメージ ビュー] のシートを使用します。

>[!NOTE]
>このリリースでは、ローカル ファイルとしての Excel ファイルはサポートされていません。チュートリアルを実行するには、サポートされている[クラウド サービス](data-sources.html)のいずれかにファイルをアップロードするか、[Web リソース](~/jp/datasources/supported-data-sources/web-resource.html)として追加してください。

### イメージ ビューを作成する方法

|                                          |                                                                                                |                                                                                                                                                      |
| ---------------------------------------- | ---------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------- |
| 1\. **ダッシュボードの作成**               | <img src="images/Tutorials-Create-New-Dashboard.png" alt="Tutorials-Create-New-Dashboard" width="100%"/>                   | ダッシュボード ビューアーで、[ダッシュボード] 画面の右上隅にある [+] ボタンを選択します。次に、ドロップダウンから [ダッシュボード] を選択します。|
| 2\. **データ ソースの構成**       | <img src="images/Tutorials-Select-Data-Source.png" alt="Tutorials-Select-Data-Source" width="100%"/>                       | *新しい表示形式*ウィンドウで、右下隅の [+] ボタンを選択し、データソースを選択します。                                       |
| 3\. **チュートリアル スプレッドシートの選択** | <img src="images/Tutorials-Select-Image-View-Spreadsheet.png" alt="Tutorials-Select-Image-View-Spreadsheet" width="100%"/> | データソースを設定したら、**Reveal チュートリアル スプレッドシート**を選択します。次に、[画像 ビュー] シートを選択し、*[データのロード]* を選択します。                               |
| 4\. **表示形式メニューを開く**     | <img src="images/Tutorials-Select-Change-Visualization.png" alt="Tutorials-Select-Change-Visualization" width="100%"/>     | 表示形式エディターのトップ バーで**グリッド アイコン**を選択します。                                                                                |
| 5\. **表示形式の選択**        | <img src="images/Tutorial-Image-View-Select.png" alt="Tutorial-Image-View-Select" width="100%"/>                           | デフォルトで、表示形式のタイプは*グリッド*に設定されています。**画像** オプションを選択してください。                                                               |
| 6\. **データを構成します**               | <img src="images/Tutorials-ImageView-Organizing-Data.png" alt="Tutorials-ImageView-Organizing-Data" width="100%"/>         | 使用可能なフィールドのいずれかを **URL** にドラッグします。                                                                                                       |
