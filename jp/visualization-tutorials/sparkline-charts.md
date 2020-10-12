## スパークライン チャートの作成

このチュートリアルは、サンプル スプレッドシートを使用してスパークライン チャートを作成する方法を説明します。

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><img src="images/SparklineChartSimple_All.png" alt="SparklineChartSimple All" /><br />
</p>
<p><a href="#create-sparkline">シンプルなスパークライン</a><br />
</p></td>
<td><p><img src="images/SparklineChartArea_All.png" alt="SparklineChartArea All" /><br />
</p>
<p><a href="#change-chart-type-sparkline">エリア チャートのスパークライン</a><br />
</p></td>
</tr>
<tr class="even">
<td><p><img src="images/SparklineDateAggregation_All.png" alt="SparklineDateAggregation All" /><br />
</p>
<p><a href="#change-date-aggregation">日の集計のスパークライン</a><br />
</p></td>
<td><p><img src="images/SparklineLessColumns_All.png" alt="SparklineLessColumns All" /><br />
</p>
<p><a href="#modify-columns">データ量の少ない柱状およびエリア チャートのスパークライン</a><br />
</p></td>
</tr>
</tbody>
</table>

スパークライン チャート ビューのガイドは、以下のリンクから参照してください。

  - [スパークライン チャートの作成](#スパークライン-チャートの作成)

  - [スパークラインのチャート タイプを変更する方法](#change-chart-type-sparkline)

  - [日付集計を変更する方法](#change-date-aggregation)

  - [スパークラインの列数を変更する方法](#modify-columns)

### 重要なコンセプト

スパークライン チャートは、指定した日付範囲のトレンドとその進行を表示します。OHLC チャートやローソク足チャートなど、ファイナンシャル シナリオと株の変動の分析のために役立ちます。
スパークラインは、グリッドセル内に折れ線チャートを表示します。

  - データ エディターの **「Date」** プレースホルダーにドロップする**フィールド**。

  - **「Value」**にドロップする**フィールド**。

  - **「Category」**にドロップする**フィールド**。

スパークライン チャートを使用する時、表示するデータに対して情報を追加、変更または削除できます。これは以下の機能で追加できます。

  - スパークラインの**チャート タイプ**は、**折れ線**または**エリア** チャートのいずれかを選択できます。

  - チャートの日付**集計**。

  - 同じチャート内に表示される**値の数**。

  - データに**過去 2 か月を含めるかどうか、またそれらの差異など**、スパークラインのグリッドに含める明示的な情報。

### サンプル データ ソース

このチュートリアルでは [Reveal チュートリアル スプレッドシート](http://download.infragistics.com/reportplus/help/samples/Reveal_Visualization_Tutorials.xlsx) の [Sparkline Charts] のシートを使用します。

>[!NOTE]
>このリリースでは、ローカル ファイルとしての Excel ファイルはサポートされていません。チュートリアルを実行するには、サポートされているクラウド サービスのいずれかにファイルをアップロードするか、[Web リソースとして](datasources/supported-data-sources/web-resource.html)追加してください。

<a name='create-sparkline'></a>
### スパークライン チャートの作成

|                                          |                                                                                                                |                                                                                                                                                      |
| ---------------------------------------- | -------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------- |
| 1\. **ダッシュボードの作成**               | <img src="images/Tutorials-Create-New-Dashboard.png" alt="Tutorials-Create-New-Dashboard" width="50%"/>                                   | ダッシュボード ビューアーで、[ダッシュボード] 画面の右上隅にある [+] ボタンを選択します。次に、ドロップダウンから [ダッシュボード] を選択します。 |
| 2\. **データ ソースの構成**       | <img src="images/Tutorials-Select-Data-Source.png" alt="Tutorials-Select-Data-Source" width="50%"/>                                       | [新しい表示形式] ウィンドウで、右下隅の [+] ボタンを選択し、データソースを選択します。                                      |
| 3\. **チュートリアル スプレッドシートの選択** | <img src="images/Tutorials-Select-Sparkline-Charts-Spreadsheet.png" alt="Tutorials-Select-Sparkline-Charts-Spreadsheet.png" width="50%"/> | データソースを設定したら、**Reveal チュートリアル スプレッドシート**を選択します。次に、「スパークライン チャート」 シートを選択します。                        |
| 4\. **表示形式メニューを開く**     | <img src="images/Tutorials-Select-Change-Visualization.png" alt="Tutorials-Select-Change-Visualization" width="50%"/>                     | 表示形式エディターのトップ バーの**グリッド アイコン**を選択します。                                                                                |
| 5\. **表示形式の選択**        | <img src="images/Tutorials-Charts-Select-Sparkline-Chart.png" alt="Tutorials-Charts-Select-Sparkline-Chart" width="50%"/>                 | デフォルトで、表示形式のタイプは*グリッド*に設定されています。スパークライン チャートを選択します。                                                           |
| 6\. **データの構成**               | <img src="images/Tutorials-SparklineChart-Organizing-Data.png" alt="Tutorials-SparklineChart-Organizing-Data" width="50%"/>               | Date フィールドを [日付] に、Offer を [値] に、Stocks を [カテゴリ] にドラッグアンドドロップします。                                                       |

<a name='change-chart-type-sparkline'></a>
### スパークラインのチャート タイプを変更する方法

スパークライン チャートに使用するチャートのタイプを変更できます。以下は作業手順です。

|                                  |                                                                                        |                                                                     |
| -------------------------------- | -------------------------------------------------------------------------------------- | ------------------------------------------------------------------- |
| 1\. **設定メニューへアクセス** | <img src="images/Tutorials-Navigate-Settings.png" alt="Tutorials-Navigate-Settings" width="50%"/>                 | 表示形式エディターの **[設定]** セクションへ移動します。         |
| 2\. **チャート タイプの変更**    | <img src="images/Tutorial-Change-Chart-Configuration.png" alt="Tutorial-Change-Chart-Configuration" width="50%"/> | デフォルトで、チャート タイプは折れ線に設定されています。エリアに設定します。 |

<a name='change-date-aggregation'></a>
### 日付集計の変更

デフォルトでは、情報の集計は **12 ヶ月**です。[表示: 過去] 設定で変更できます。以下は変更手順です。

|                                  |                                                                                                      |                                                                                                                                                      |
| -------------------------------- | ---------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------- |
| 1\. **設定メニューへアクセス** | <img src="images/Tutorials-Navigate-Settings.png" alt="Tutorials-Navigate-Settings" width="50%"/>                               | 表示形式エディターの **[設定]** セクションへ移動します。                                                                                          |
| 2\. **集計の変更**   | <img src="images/Tutorial-Change-Date-Aggregation-Sparkline.png" alt="Tutorial-Change-Date-Aggregation-Sparkline" width="50%"/> | デフォルトで、[表示: 過去] 設定は **[月]** に設定されます。[月] の横のドロップダウンを選択し、 [年] または [日] に変更します。|

日付の集計の隣にある数値を変更して、表示するデータを増減できます。

<a name='modify-columns'></a>
### スパークラインの列数を変更する方法

Reveal で、表示形式の列数は、過去 2 か月とそれらの差を表示するかどうかによって定義されます。デフォルトで有効になります。以下は削除方法です。

|                                      |                                                                                    |                                                                                                                                                          |
| ------------------------------------ | ---------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 1\. **設定メニューへアクセス**     | <img src="images/Tutorials-Navigate-Settings.png" alt="Tutorials-Navigate-Settings" width="50%"/>             | 表示形式エディターの **[設定]** セクションへ移動します。                                                                                              |
| 2\. **表示列の変更** | <img src="images/Tutorial-Remove-Columns-Sparkline.png" alt="Tutorial-Remove-Columns-Sparkline" width="50%"/> | どちらもスパークラインに表示しない場合は、**[最後の 2 つの値の列を表示] または [差異のある列を表示] ボックスをオフにします**。|
