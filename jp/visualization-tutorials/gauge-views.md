## ゲージで表示形式を作成する方法

このチュートリアルは、サンプル スプレッドシートを使用したゲージでデータの可視化を行います。

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><img src="images/lineargauge-visualization.png" alt="lineargauge visualization" /><br />
</p>
<p><a href="#create-linear-gauge">リニア ゲージ</a><br />
</p></td>
<td><p><img src="images/circulargauge-visualization.png" alt="circulargauge visualization" /><br />
</p>
<p><a href="#create-circular-gauge">円形ゲージ</a><br />
</p></td>
<td><p><img src="images/textgauge-visualization.png" alt="textgauge visualization" /><br />
</p>
<p><a href="#create-text-gauge">テキスト ゲージ</a><br />
</p></td>
</tr>
<tr class="even">
<td><p><img src="images/bulletgraphgauge-visualization.png" alt="bulletgraphgauge visualization" /><br />
</p>
<p><a href="#create-bullet-graph-gauge">ブレット グラフ</a><br />
</p></td>
<td><p><img src="images/lineargauge-boundsconfiguration.png" alt="lineargauge boundsconfiguration" /><br />
</p>
<p><a href="#adding-bounds-gauge">範囲構成のリニア ゲージ</a><br />
</p></td>
<td><p><img src="images/lineargauge-visualization-bandconfiguration.png" alt="lineargauge visualization bandconfiguration" /><br />
</p>
<p><a href="#modify-bands">バンドの色が異なるリニア ゲージ</a><br />
</p></td>
</tr>
</tbody>
</table>

ゲージ ビューのためのガイドは、以下のリンクから参照してください。

  - [リニア ゲージの作成方法](#create-linear-gauge)

  - [ラジアル ゲージの作成方法](#create-circular-gauge)

  - [ラベル ゲージの作成方法](#create-text-gauge)

  - [ブレット グラフ の作成方法](#create-bullet-graph-gauge)

  - [ゲージ可視化に範囲を追加する方法](#adding-bounds-gauge)

  - [バンドの色を変更する方法](#modify-bands)

<a name='key-concepts'></a>
### 重要なコンセプト

積層型チャートは、 3 つのレイアウトから選択できます:

  - **しきい値の構成**。ゲージのしきい値の構成ではゲージの最大値と最小値を設定できます。デフォルトで最小値に設定されますが、特定のデータを除外するために変更できます。

  - **バンド構成**。バンドの構成は 3 つの範囲を設定できます ([より大きい]、[中間]、[より小さい]) です。データ ソースに基づく範囲でデフォルトの値を上書きします。

### サンプル データ ソース

このチュートリアルでは、[Reveal チュートリアル スプレッドシート](http://download.infragistics.com/reportplus/help/samples/Reveal_Visualization_Tutorials.xlsx).

>[!NOTE]
>このリリースでは、ローカル ファイルとしての Excel ファイルはサポートされていません。チュートリアルを実行するには、サポートされている[クラウド サービス](data-sources.md)のいずれかにファイルをアップロードするか、[Web リソース](web-resource.md)として追加してください。

<a name='create-linear-gauge'></a>
### リニア ゲージを作成する方法

|                                          |                                                                                            |                                                                                                                                                                       |
| ---------------------------------------- | ------------------------------------------------------------------------------------------ | --------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 1\. **Create a Dashboard**               | ![Tutorials-Create-New-Dashboard](images/Tutorials-Create-New-Dashboard.png)               | In the dashboard viewer, select the + button in the top right-hand corner of the "My Dashboards" screen. Then, select "Dashboard" from the dropdown.                  |
| 2\. **Configure your Data Source**       | ![Tutorials-Select-Data-Source](images/Tutorials-Select-Data-Source.png)                   | In the *New Visualization* window, select the + button in the bottom right corner and select your data source.                                                        |
| 3\. **Select the Tutorials Spreadsheet** | ![Tutorials-Select-Gauge-Views](images/Tutorials-Select-Gauge-Views.png)                   | Once the data source is configured, select the **Reveal Tutorials Spreadsheet**. Then, choose the "Gauge Views" sheet and select *Load Data*.                         |
| 4\. **Open the Visualizations Menu**     | ![Tutorials-Select-Change-Visualization](images/Tutorials-Select-Change-Visualization.png) | Select the **grid icon** in the top bar of the Visualizations Editor.                                                                                                 |
| 5\. **Select your Visualization**        | ![Tutorials-Select-Linear-Gauge](images/Tutorials-Select-Linear-Gauge.png)                 | By default, the visualization type will be set to "Grid". Select the "Linear" gauge.                                                                                  |
| 6\. **Organize your Data**               | ![Tutorials-LinearGauge-Data](images/Tutorials-LinearGauge-Data.png)                       | This linear gauge, for example, will display life expectancy per Country. Drag and drop the "Country Name" field to "Label" and one of the year fields into "Values". |

<a name='create-circular-gauge'></a>
### 円形ゲージを作成する方法

|                                          |                                                                                            |                                                                                                                                                                       |
| ---------------------------------------- | ------------------------------------------------------------------------------------------ | --------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 1\. **ダッシュボードの作成**               | ![Tutorials-Create-New-Dashboard](images/Tutorials-Create-New-Dashboard.png)               | In the dashboard viewer, select the + button in the top right-hand corner of the "My Dashboards" screen. Then, select "Dashboard" from the dropdown.                  |
| 2\. **データ ソースの構成**       | ![Tutorials-Select-Data-Source](images/Tutorials-Select-Data-Source.png)                   | In the *New Visualization* window, select the + button in the bottom right corner and select your data source.                                                        |
| 3\. **Select the Tutorials Spreadsheet** | ![Tutorials-Select-Gauge-Views](images/Tutorials-Select-Gauge-Views.png)                   | Once the data source is configured, select the **Reveal Tutorials Spreadsheet**. Then, choose the "Gauge Views" sheet and select *Load Data*.                         |
| 4\. **Open the Visualizations Menu**     | ![Tutorials-Select-Change-Visualization](images/Tutorials-Select-Change-Visualization.png) | Select the **grid icon** in the top bar of the Visualizations Editor.                                                                                                 |
| 5\. **Select your Visualization**        | ![Tutorials-Select-Linear-Gauge](images/Tutorials-Select-Linear-Gauge.png)                 | By default, the visualization type will be set to "Grid". Select the "Circular" gauge.                                                                                |
| 6\. **Organize your Data**               | ![Tutorials-CircularGauge-Data](images/Tutorials-CircularGauge-Data.png)                   | This radial gauge, for example, will display life expectancy per Country. Drag and drop the "Country Name" field to "Label" and one of the year fields into "Values". |


円形ゲージは、特に平均値と値の合計の表示に適しています。[値] に表示されるフィールドの集計を変更する手順:

<a name='aggregation-instructions'></a>

|                                              |                                                                            |                                                                                           |
| -------------------------------------------- | -------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------- |
| 1\. **Access Field Settings for your Value** | ![Add-Data-Filter-CircularGauge](images/Add-Data-Filter-CircularGauge.png) | Select the field in **Values** to access                                                  |
| 2\. **Choose a different Aggregation**       | ![CircularGauge-Aggregation](images/CircularGauge-Aggregation.png)         | Expand the **Aggregation** dropdown and select a different option (for example, Average). |


<a name='create-text-gauge'></a>
### テキスト ゲージを作成する方法

|                                          |                                                                                                                   |                                                                                                                                                                                                                                                       |
| ---------------------------------------- | ----------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 1\. **Create a Dashboard**               | ![Tutorials-Create-New-Dashboard](images/Tutorials-Create-New-Dashboard.png)                                      | In the dashboard viewer, select the + button in the top right-hand corner of the "My Dashboards" screen. Then, select "Dashboard" from the dropdown.                                                                                                  |
| 2\. **Configure your Data Source**       | ![Tutorials-Select-Data-Source](images/Tutorials-Select-Data-Source.png)                                          | In the *New Visualization* window, select the + button in the bottom right corner and select your data source.                                                                                                                                        |
| 3\. **Select the Tutorials Spreadsheet** | ![Tutorials-Select-Simple-Series-Charts-Spreadshee](images/Tutorials-Select-Simple-Series-Charts-Spreadsheet.png) | Once the data source is configured, select the **Reveal Tutorials Spreadsheet**. Then, choose the "Gauge Views" sheet.                                                                                                                                |
| 4\. **Open the Visualizations Menu**     | ![Tutorials-Select-Change-Visualization](images/Tutorials-Select-Change-Visualization.png)                        | Select the **grid icon** in the top bar of the Visualizations Editor.                                                                                                                                                                                 |
| 5\. **Select your Visualization**        | ![Tutorials-Select-Linear-Gauge](images/Tutorials-Select-Linear-Gauge.png)                                        | By default, the visualization type will be set to "Grid". Select the "Text" gauge.                                                                                                                                                                    |
| 6\. **Organize your Data**               | ![Tutorials-TextGauge-Organizing-Data](images/Tutorials-TextGauge-Organizing-Data.png)                            | This text gauge, for example, will display life expectancy per Country. Drag and drop one of the year fields into "Values", and then the "Country Name" field into "Data Filters". Then, select the specific country you want by selecting the field. |

The text gauge sample above utilizes the average aggregation. In order to learn how to change your field's aggregation, [review these instructions](#aggregation-instructions).

<a name='create-bullet-graph-gauge'></a>
### ブレット グラフを作成する方法

|                                          |                                                                                                                   |                                                                                                                                                                                              |
| ---------------------------------------- | ----------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 1\. **Create a Dashboard**               | ![Tutorials-Create-New-Dashboard](images/Tutorials-Create-New-Dashboard.png)                                      | In the dashboard viewer, select the + button in the top right-hand corner of the "My Dashboards" screen. Then, select "Dashboard" from the dropdown.                                         |
| 2\. **Configure your Data Source**       | ![Tutorials-Select-Data-Source](images/Tutorials-Select-Data-Source.png)                                          | In the *New Visualization* window, select the + button in the bottom right corner and select your data source.                                                                               |
| 3\. **Select the Tutorials Spreadsheet** | ![Tutorials-Select-Simple-Series-Charts-Spreadshee](images/Tutorials-Select-Simple-Series-Charts-Spreadsheet.png) | Once the data source is configured, select the **Reveal Tutorials Spreadsheet**. Then, choose the "Gauge Views" sheet.                                                                       |
| 4\. **Open the Visualizations Menu**     | ![Tutorials-Select-Change-Visualization](images/Tutorials-Select-Change-Visualization.png)                        | Select the **grid icon** in the top bar of the Visualizations Editor.                                                                                                                        |
| 5\. **Select your Visualization**        | ![Tutorials-Charts-Select-Visualization](images/Tutorials-Charts-Select-Visualization.png)                        | By default, the visualization type will be set to "Grid". Select the "Bullet Graph" visualization.                                                                                           |
| 6\. **Organize your Data**               | ![Tutorials-Charts-Organizing-Data](images/Tutorials-Charts-Organizing-Data.png)                                  | This bullet graph, for example, will display life expectancy per Country. Drag and drop the "Country Name" field to "Label", one of the years into "Values", and another year into "Target". |

<a name='adding-bounds-gauge'></a>
### ゲージの化でしきい値を追加する方法

しきい値を使用すると、ゲージの最小値と最大値を設定できます。 [重要なコンセプト](#key-concepts)で述べたように、特定のデータを除外するように変更できます。以下は作業手順です。

|                                                |                                                                        |                                                                                                                                       |
| ---------------------------------------------- | ---------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------- |
| 1\. **Change Settings**                        | ![Tutorials-Navigate-Settings](images/Tutorials-Navigate-Settings.png) | Go to the **Settings** section of the Visualization Editor.                                                                           |
| 2\. **Change the Default selection in Limits** | ![Tutorials-Limits-Bounds](images/Tutorials-Limits-Bounds.png)         | Depending on whether you want to set the minimum or maximum value (or both), enter the value you want the chart to start or end with. |

<a name='modify-bands'></a>
### バンドの色の変更

以下は、バンド ([より大きい]、[中間] および [より小さい]) の色を変更するための手順です。以下は変更手順です。

|                                    |                                                                        |                                                                          |
| ---------------------------------- | ---------------------------------------------------------------------- | ------------------------------------------------------------------------ |
| 1\. **Change Settings**            | ![Tutorials-Navigate-Settings](images/Tutorials-Navigate-Settings.png) | Go to the **Settings** section of the Visualization Editor.              |
| 2\. **Access the Colors dropdown** | ![Tutorials-Colors-Dropdown](images/Tutorials-Colors-Dropdown.png)     | Expand the dropdown of the range for which you want to change the color. |
| 3\. **Select your Color**          | ![Tutorials-Changing-Color](images/Tutorials-Changing-Color.png)       | Select one of Reveal's three predefined colors for your band color.      |
