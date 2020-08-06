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
| 1\. **ダッシュボードの作成**               | ![Tutorials-Create-New-Dashboard](images/Tutorials-Create-New-Dashboard.png)                   | ダッシュボード ビューアーで、[ダッシュボード] 画面の右上隅にある [+] ボタンを選択します。次に、ドロップダウンから [ダッシュボード] を選択します。|
| 2\. **データ ソースの構成**       | ![Tutorials-Select-Data-Source](images/Tutorials-Select-Data-Source.png)                       | *新しい表示形式*ウィンドウで、右下隅の [+] ボタンを選択し、データソースを選択します。                                       |
| 3\. **チュートリアル スプレッドシートの選択** | ![Tutorials-Select-Image-View-Spreadsheet](images/Tutorials-Select-Image-View-Spreadsheet.png) | データソースを設定したら、**Reveal チュートリアル スプレッドシート**を選択します。次に、[画像 ビュー] シートを選択し、*[データのロード]* を選択します。                               |
| 4\. **表示形式メニューを開く**     | ![Tutorials-Select-Change-Visualization](images/Tutorials-Select-Change-Visualization.png)     | 表示形式エディターのトップ バーで**グリッド アイコン**を選択します。                                                                                |
| 5\. **表示形式の選択**        | ![Tutorial-Image-View-Select](images/Image-View-Select.png)                           | デフォルトで、表示形式のタイプは*グリッド*に設定されています。**画像** オプションを選択してください。                                                               |
| 6\. **データを構成します**               | ![Tutorials-ImageView-Organizing-Data](images/Tutorials-ImageView-Organizing-Data.png)         | 使用可能なフィールドのいずれかを **URL** にドラッグします。                                                                                                       |
