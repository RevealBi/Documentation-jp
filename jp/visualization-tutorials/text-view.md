## テキスト ビューを作成する方法

このチュートリアルはサンプル スプレッドシートを使用しテキスト ビューを作成する方法を説明します。

![TextViewSample\_All](images/TextViewSample_All.png)

テキスト ビューのガイドは、以下のリンクから参照してください。

  - [基本的なテキスト ビューを作成する方法](#creating-text-view)

  - [選択された行を変更する方法](#changing-selected-row)

### 重要なコンセプト

テキストビューではキーと値のパターンで情報が表示されますが、**列のラベルとペアになっているデータの最初の行のみが表示されます**。ただし、フィルターを追加して、必要な行が Reveal 表示されるようにすることができます。

### サンプル データ ソース

このチュートリアルでは [Reveal チュートリアル スプレッドシート](http://download.infragistics.com/reportplus/help/samples/Reveal_Visualization_Tutorials.xlsx) の [Simple Series Charts] のシートを使用します。

>[!NOTE]
>このリリースでは、ローカル ファイルとしての Excel ファイルはサポートされていません。チュートリアルを実行するには、サポートされているクラウド サービスのいずれかにファイルをアップロードするか、Web リソースとして追加してください。

<a name='creating-text-view'></a>
### テキスト ビューを作成する方法

|                                          |                                                                                                                   |                                                                                                                                                                                                                         |
| ---------------------------------------- | ----------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 1\. **ダッシュボードの作成**               | ![Tutorials-Create-New-Dashboard](images/Tutorials-Create-New-Dashboard.png)                                      | ダッシュボード ビューアーで、[ダッシュボード] 画面の右上隅にある [+] ボタンを選択します。次に、ドロップダウンから [ダッシュボード] を選択します。                                                                    |
| 2\. **データ ソースの構成**       | ![Tutorials-Select-Data-Source](images/Tutorials-Select-Data-Source.png)                                          | [新しい表示形式] ウィンドウで、右下隅の [+] ボタンを選択し、データソースを選択します。                                                                                                         |
| 3\. **チュートリアル スプレッドシートの選択** | ![Tutorials-Select-Simple-Series-Charts-Spreadshee](images/Tutorials-Select-Simple-Series-Charts-Spreadsheet.png) | データソースを設定したら、**Reveal チュートリアル スプレッドシート**を選択します。 次に、「Simple Series Charts」シートを選択します。                                                                                        |
| 4\. **表示形式メニューを開く**     | ![Tutorials-Select-Change-Visualization](images/Tutorials-Select-Change-Visualization.png)                        | 表示形式エディターのトップ バーで**グリッド アイコン**を選択します。                                                                                                                                                   |
| 5\. **表示形式の選択**        | ![Tutorials-Charts-Select-Text-View](images/Tutorials-Charts-Select-Text-View.png)                                | デフォルトで、表示形式のタイプは*グリッド*に設定されています。 Select the **Text View**.                                                                                                                                     |
| 6\. **データの構成**               | ![Tutorials-TextView-Organizing-Data](images/Tutorials-TextView-Organizing-Data.png)                              | たとえば、上記のテキスト ビューには、特定の国の人口、平均余命、および出生率が表示されます。[国名]、[人口]、[平均余命]、[出生率] を列にドラッグアンドドロップします。 |

<a name='changing-selected-row'></a>
### 選択された行を変更する方法

デフォルトで、テキスト ビューはシートの最初の行を表示されます。これを変更するためにフィルターを適用できます。たとえば、テキスト ビューに行 9 (ボスニアおよびヘルツェゴビナ) を表示させます。

|                           |                                                                       |                                                                                                                                            |
| ------------------------- | --------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------ |
| 1\. **データフィルターの追加** | ![SelectFieldTextView\_All](images/SelectFieldTextView_All.png)       | [国名] フィールドをデータ フィルターにドラッグアンドドロップします。                                                                                  |
| 2\. **フィルターの設定**   | ![SelectedValuesTextView\_All](images/SelectedValuesTextView_All.png) | [フィルター タイプ] を選択してドロップダウン メニューを有効にしてから [値の選択] を選択します。                                                       |
| 3\. **値の選択** | ![SelectValueTextView2\_All](images/SelectValueTextView2_All.png)     | デフォルトでは、すべての値が選択済です。[すべて] のボックスをオフにして、「ボスニアとヘルツェゴビナ」のみを選択します。 |

