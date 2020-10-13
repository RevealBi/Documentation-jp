## KPI ゲージを作成

このチュートリアルでは、サンプル スプレッドシートを使用して KPI ゲージの表示形式を作成する方法を説明します。

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><img src="images/KPIGaugeSimple_All.png" alt="KPIGaugeSimple All" /><br />
</p>
<p><a href="#creating-kpi-gauge">KPI ゲージ</a><br />
</p></td>
<td><p><img src="images/TutorialMultipleKPIGauges_All.png" alt="TutorialMultipleKPIGauges All" /><br />
</p>
<p><a href="#adding-category-kpi">複数の KPI ゲージ</a><br />
</p></td>
</tr>
<tr class="even">
<td><p><img src="images/KPIGaugePreviousMonth_All.png" alt="KPIGaugePreviousMonth All" /><br />
</p>
<p><a href="#changing-date-comparison-type">月ごとの KPI ゲージ</a><br />
</p></td>
<td><p><img src="images/KPIGaugeValuePercentage_All.png" alt="KPIGaugeValuePercentage All" /><br />
</p>
<p><a href="#changing-difference-label-kpi">値とパーセンテージの違いがある KPI ゲージ</a><br />
</p></td>
</tr>
<tr class="odd">
<td><p><img src="images/KPIGaugeDifferenceColor_All.png" alt="KPIGaugeDifferenceColor All" /><br />
</p>
<p><a href="#changing-color-difference-marker">値が減少したときに緑色のマーカーが付いた KPI ゲージ</a><br />
</p></td>
<td></td>
</tr>
</tbody>
</table>

KPI ゲージ ビューのためのガイドは、以下のリンクから参照してください:

  - [KPI ゲージの作成方法](#creating-kpi-gauge)

  - [1 つの表示形式で複数の KPI ゲージを作成する方法](#adding-category-kpi)

  - [KPI の日付タイプを変更する方法](#changing-date-comparison-type)

  - [KPI の差分ラベルを変更する方法](#changing-difference-label-kpi)

  - [KPI の差分マーカーの色を変更する方法](#changing-color-difference-marker)

### 重要なコンセプト

KPI ゲージは、特定の期間内のパフォーマンスとその変動を表示するためのものです。作成するには、次のものが必要です:

  - データ エディターの **[日付]**プレースホルダーへ **1 フィールド**ドロップします。

  - **1 フィールド**を **[値]** へドロップします。

### サンプル データ ソース

このチュートリアルでは、[Reveal チュートリアル スプレッドシート](http://download.infragistics.com/reportplus/help/samples/Reveal_Visualization_Tutorials.xlsx)の [KPI ビュー] のシートを使用します。

>[!NOTE]
>このリリースでは、ローカル ファイルとしての Excel ファイルはサポートされていません。チュートリアルを実行するには、サポートされている[クラウド サービス](data-sources.html)のいずれかにファイルをアップロードするか、[Web リソース](web-resource.html)として追加してください。

<a name='creating-kpi-gauge'></a>
### KPI ゲージを作成

|                                          |                                                                                              |                                                                                                                                                      |
| ---------------------------------------- | -------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------- |
| 1\. **ダッシュボードの作成**               | <img src="images/Tutorials-Create-New-Dashboard.png" alt="Tutorials-Create-New-Dashboard" width="100%"/>                 | ダッシュボード ビューアーで、[ダッシュボード] 画面の右上隅にある [+] ボタンを選択します。 次に、ドロップダウンから [ダッシュボード] を選択します。 |
| 2\. **データ ソースの構成**       | <img src="images/Tutorials-Select-Data-Source.png" alt="Tutorials-Select-Data-Source" width="100%"/>                     | *新しい表示形式*ウィンドウで、右下隅の [+] ボタンを選択し、データソースを選択します。                                       |
| 3\. **チュートリアル スプレッドシートの選択** | <img src="images/Tutorials-Select-KPI-Gauge-Spreadsheet.png" alt="Tutorials-Select-KPI-Gauge-Spreadsheet" width="100%"/> | データソースを設定したら、**Reveal チュートリアル スプレッドシート**を選択します。 次に、[KPI ゲージ] シートを選択します。                                 |
| 4\. **表示形式メニューを開く**     | <img src="images/Tutorials-Select-Change-Visualization.png" alt="Tutorials-Select-Change-Visualization" width="100%"/>   | 表示形式エディターのトップ バーで**グリッド アイコン**を選択します。                                                                                |
| 5\. **表示形式の選択**        | <img src="images/Tutorials-Select-KPI-vs-Time-Gauge.png" alt="Tutorials-Select-KPI-Gauge" width="100%"/>                         | デフォルトで、表示形式のタイプは*グリッド*に設定されています。 **KPI vs Time** ゲージを選択します。                                                            |
| 6\. **Organize your Data**               | <img src="images/Tutorials-KPIGauge-Organizing-Data.png" alt="Tutorials-KPIGauge-Organizing-Data" width="100%"/>         | [ラベル] に Date フィールド、[値] に Sales フィールドをドラッグアンドドロップします。                                                                       |

<a name='adding-category-kpi'></a>
### 1 つの表示形式で複数の KPI ゲージを作成する方法

1 つの表示形式で複数の KPI を作成するには、データ エディターの**カテゴリ** プレースホルダーにフィールドを追加する必要があります。

|                                          |                                                                                                      |                                                                                                                                                      |
| ---------------------------------------- | ---------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------- |
| 1\. **ダッシュボードの作成**               | <img src="images/Tutorials-Create-New-Dashboard.png" alt="Tutorials-Create-New-Dashboard" width="100%"/>                         | ダッシュボード ビューアーで、[ダッシュボード] 画面の右上隅にある [+] ボタンを選択します。 次に、ドロップダウンから [ダッシュボード] を選択します。 |
| 2\. **データ ソースの構成**       | <img src="images/Tutorials-Select-Data-Source.png" alt="Tutorials-Select-Data-Source" width="100%"/>                             | *新しい表示形式*ウィンドウで、右下隅の [+] ボタンを選択し、データソースを選択します。                                       |
| 3\. **チュートリアル スプレッドシートの選択** | <img src="images/Tutorials-Select-KPI-Gauge-Spreadsheet.png" alt="Tutorials-Select-KPI-Gauge-Spreadsheet" width="100%"/>         | データソースを設定したら、**Reveal チュートリアル スプレッドシート**を選択します。 次に、[KPI ゲージ] シートを選択します。                                 |
| 4\. **表示形式メニューを開く**     | <img src="images/Tutorials-Select-Change-Visualization.png" alt="Tutorials-Select-Change-Visualization" width="100%"/>           | 表示形式エディターのトップ バーで**グリッド アイコン**を選択します。                                                                                |
| 5\. **表示形式の選択**        | <img src="images/Tutorials-Select-KPI-vs-Time-Gauge.png" alt="Tutorials-Select-KPI-Gauge" width="100%"/>                                 | デフォルトで、表示形式のタイプは*グリッド*に設定されています。 **KPI vs Time** ゲージを選択します。                                                            |
| 6\. **データの体系化**               | <img src="images/Tutorials-MultipleKPIGauge-Organizing-Data.png" alt="Tutorials-MultipleKPIGauge-Organizing-Data" width="100%"/> | Date フィールドを [日付] に、Sales フィールドを [値] に、State フィールドを [カテゴリ] にドラッグアンドドロップします。                                    |

<a name='changing-date-comparison-type'></a>
### 日付比較タイプの変更

デフォルトでは、KPI ゲージの日付タイプは前年比になります。[タイプ] フィールドを変更することでこれを変更できます。以下は変更手順です。

|                                  |                                                                        |                                                                                                                                                |
| -------------------------------- | ---------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------- |
| 1\. **設定メニューへアクセス** | <img src="images/Tutorials-Navigate-Settings.png" alt="Tutorials-Navigate-Settings" width="100%"/> | 表示形式エディターの**設定**セクションへ移動します。                                                                                    |
| 2\. **タイプを変更します。**          | <img src="images/Tutorial-Change-Date-Type.png" alt="Tutorial-Change-Date-Type" width="100%"/>     | デフォルトでは、日付タイプは前年比になります。 **[目票期間]]** の横のドロップダウンを選択し、選択を **[月度累計]** に変更します。|

<a name='changing-difference-label-kpi'></a>
### KPI ゲージの差分ラベルの変更

|                                  |                                                                                            |                                                                                                                                                                         |
| -------------------------------- | ------------------------------------------------------------------------------------------ | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 1\. **設定メニューへアクセス** | <img src="images/Tutorials-Navigate-Settings.png" alt="Tutorials-Navigate-Settings" width="100%"/>                     | 表示形式エディターの**設定**セクションへ移動します。                                                                                                             |
| 2\. **タイプを変更します。**          | <img src="images/Tutorial-Change-Date-Difference-Label.png" alt="Tutorial-Change-Date-Difference-Label" width="100%"/> | デフォルトで、差分ラベルは*パーセンテージ*に設定されています。 **[差異の表示]** の横のドロップダウンを選択し、選択を **[値とパーセンテージ]** に変更します。|

<a name='changing-color-difference-marker'></a>
### 差分マーカーの色の変更

デフォルトでは、 KPI ゲージのマーカーの色は、正の値の場合は緑、負の値の場合は赤に設定されます。ただし、減少をプラスとして表現したい場合もあります。以下は設定方法です。

|                                  |                                                                                                          |                                                                                                                                                             |
| -------------------------------- | -------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 1\. **設定メニューへアクセス** | <img src="images/Tutorials-Navigate-Settings.png" alt="Tutorials-Navigate-Settings" width="100%"/>                                   | 表示形式エディターの**設定**セクションへ移動します。                                                                                                 |
| 2\. **タイプを変更します。**          | <img src="images/Tutorial-Change-Date-Difference-Marker-Color.png" alt="Tutorial-Change-Date-Difference-Marker-Color" width="100%"/> | デフォルトでは、マーカーの色は緑に設定されます。**[値の増加を表す色]** の横のドロップダウンを選択し、選択を **[赤色]** に変更します。|
