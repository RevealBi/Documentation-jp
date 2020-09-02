## シンプルシリーズのチャートの作成

このチュートリアルは、サンプル スプレッドシートを使用しシンプルシリーズのチャートを作成する方法を説明します。

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><img src="images/areachart_all.png" alt="areachart all" /><br />
</p>
<p><a href="#create-basic-chart">エリア チャート</a><br />
</p></td>
<td><p><img src="images/barchart_all.png" alt="barchart all" /><br />
</p>
<p><a href="#create-basic-chart">棒チャート</a><br />
</p></td>
<td><p><img src="images/circularradialchart_all.png" alt="circularradialchart all" /><br />
</p>
<p><a href="#create-basic-chart">円/ラジアル チャート</a><br />
</p></td>
</tr>
<tr class="even">
<td><p><img src="images/columnchart_all.png" alt="columnchart all" /><br />
</p>
<p><a href="#create-basic-chart">柱状チャート</a><br />
</p></td>
<td><p><img src="images/doughnutchart_all.png" alt="doughnutchart all" /><br />
</p>
<p><a href="#create-basic-chart">ドーナツ型チャート</a><br />
</p></td>
<td><p><img src="images/funnelchart_all.png" alt="funnelchart all" /><br />
</p>
<p><a href="#create-basic-chart">ファンネル チャート</a><br />
</p></td>
</tr>
<tr class="odd">
<td><p><img src="images/linechart_all.png" alt="linechart all" /><br />
</p>
<p><a href="#create-basic-chart">折れ線チャート</a><br />
</p></td>
<td><p><img src="images/piechart_all.png" alt="piechart all" /><br />
</p>
<p><a href="#create-basic-chart">円チャート</a><br />
</p></td>
<td><p><img src="images/splineareachart_all.png" alt="splineareachart all" /><br />
</p>
<p><a href="#create-basic-chart">スプライン エリア チャート</a><br />
</p></td>
</tr>
<tr class="even">
<td><p><img src="images/splinechart_all.png" alt="splinechart all" /><br />
</p>
<p><a href="#create-basic-chart">スプライン チャート</a><br />
</p></td>
<td><p><img src="images/stepareachart_all.png" alt="stepareachart all" /><br />
</p>
<p><a href="#create-basic-chart">ステップ エリア チャート</a><br />
</p></td>
<td><p><img src="images/steplinechart_all.png" alt="steplinechart all" /><br />
</p>
<p><a href="#create-basic-chart">ステップ折れ線チャート</a><br />
</p></td>
</tr>
<tr class="odd">
<td><p><img src="images/chartquarticfit_all.png" alt="chartquarticfit all" /><br />
</p>
<p><a href="#add-trendline-chart">四次フィットトレンドラインのチャート</a><br />
</p></td>
<td><p><img src="images/chartbounds_all.png" alt="chartbounds all" /><br />
</p>
<p><a href="#change-axis-configuration">しきい値のチャート</a><br />
</p></td>
<td><p><img src="images/chartlogarithmicaxis_all.png" alt="chartlogarithmicaxis all" /><br />
</p>
<p><a href="#set-logarithmic-axis">対数軸構成のチャート</a><br />
</p></td>
</tr>
<tr class="even">
<td><p><img src="images/chartstartposition270_all.png" alt="chartstartposition270 all" /><br />
</p>
<p><a href="#change-start-position">開始位置が270°のドーナツ型チャート</a><br />
</p></td>
<td><p><img src="images/chartslicelabels_all.png" alt="chartslicelabels all" /><br />
</p>
<p><a href="#change-slice-labels">値と割合のスライス ラベルが付いたドーナツ型チャート</em> slice labels</a><br />
</p></td>
<td></td>
</tr>
</tbody>
</table>

シンプル チャート ビューのガイドは、以下のリンクから参照してください。

  - [エリア チャートを作成する方法](#create-basic-chart)

  - [チャートのタイプを変更する方法](#changing-chart-type)

  - [チャートにトレンドラインを追加する](#add-trendline-chart)

  - [軸の構成を変更する](#change-axis-configuration)

  - [軸の構成を対数に変更する](#set-logarithmic-axis)

  - [ドーナツ型と円チャートの開始位置の変更方法](#change-start-position)

  - [ファンネル、円とドーナツ型 チャートのスライスのラベルを変更する方法](#change-slice-labels)

### 重要なコンセプト

チャートを使用する時、可視化される情報とともに追加の情報も追加できます。これは以下の機能で追加できます。

  - チャートに折れ線で表示する**チャート トレンドライン**。変数間の関係や情報全体の方向性を表す場合に役立ちます。チャートに回帰と呼ばれるいくつかのアルゴリズムを適用できます。回帰は *[チャート トレンドライン]* から選択できます。

  - **軸の構成**: 軸の構成でチャートの最大値と最小値を構成できます。デフォルトで最小値は 0 に設定され、最大値は使用されるデータによって設定されます。

      - *対数軸構成*: [対数] ボックスをチェックする場合、値のスケールは通常のリニア スケールを使用する代わりに大きさを使用するリニア スケール以外で計算されます。

  - **開始位置**: 円チャートおよびドーナツ型チャートでチャートのスライスを回転する開始位置を構成し、データの表示順序を変更できます。

  - **スライス ラベル**: ドーナツ型、ファンネル、および円チャートでは、値やパーセンテージ、またはその両方を同時に表示するスライス ラベルを構成できます。

### サンプル データ ソース

このチュートリアルでは [Reveal チュートリアル スプレッドシート](http://download.infragistics.com/Reveal/help/samples/Reveal-Tutorials-Spreadsheet.xlsx) の [シンプル シリーズのチャート] のシートを使用します。

>[!NOTE]
>このリリースでは、ローカル ファイルとしての Excel ファイルはサポートされていません。チュートリアルを実行するには、サポートされている[クラウド サービス](data-sources.md)のいずれかにファイルをアップロードするか、[Web リソース](web-resource.md)として追加してください。

<a name='create-basic-chart'></a>
### チャートの作成

|                                          |                                                                                                                   |                                                                                                                                                                                                |
| ---------------------------------------- | ----------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 1\. **ダッシュボードの作成**               | ![Tutorials-Create-New-Dashboard](images/Tutorials-Create-New-Dashboard.png)                                      | ダッシュボード ビューアーで、[ダッシュボード] 画面の右上隅にある [+] ボタンを選択します。次に、ドロップダウンから [ダッシュボード] を選択します。                                           |
| 2\. **データ ソースの構成**       | ![Tutorials-Select-Data-Source](images/Tutorials-Select-Data-Source.png)                                          | *新しい表示形式*ウィンドウで、右下隅の [+] ボタンを選択し、データソースを選択します。                                                                                |
| 3\. **チュートリアル スプレッドシートの選択** | ![Tutorials-Select-Simple-Series-Charts-Spreadshee](images/Tutorials-Select-Simple-Series-Charts-Spreadsheet.png) | データソースを設定したら、**Reveal チュートリアル スプレッドシート**を選択します。次に、「シンプル シリーズ チャート」 シートを選択します。                                                                |
| 4\. **表示形式メニューを開く**     | ![Tutorials-Select-Change-Visualization](images/Tutorials-Select-Change-Visualization.png)                        | 表示形式エディターのトップ バーで**グリッド アイコン**を選択します。                                                                                                                         |
| 5\. **表示形式の選択**        | ![Tutorials-Charts-Select-Visualization](images/Tutorials-Charts-Select-Visualization.png)                        | デフォルトで、表示形式のタイプは*グリッド*に設定されています。**チャート**の表示形式のいずれかを選択します。                                                                                          |
| 6\. **データの体系化**               | ![Tutorials-Charts-Organizing-Data](images/Tutorials-Charts-Organizing-Data.png)                                  | たとえば、上の表のチャートには、選択した国のリストの人口が表示されます。[ラベル] に [Country Name] フィールド、[Population] フィールドを [値] へドラッグアンドドロップします。|

### チャートのタイプの変更

上記のチュートリアルでは、チャートの作成方法を概説しています。必要に応じて別のタイプを選択する場合は、次の手順を実行してください。

|                                      |                                                                                            |                                                                                                                                 |
| ------------------------------------ | ------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------- |
| 1\. **表示形式メニューを開く** | ![Tutorials-Select-Change-Visualization](images/Tutorials-Select-Change-Visualization.png) | 表示形式エディターのトップ バーで**グリッド アイコン**を選択します。                                                          |
| 2\. **表示形式の選択**    | ![Tutorials-Charts-Select-Visualization](images/Tutorials-Charts-Select-Visualization.png) | このセクションの上部に各チャートのタイプのプレビューがあります。|

<a name='add-trendline-chart'></a>
### チャートに近似曲線を追加する

情報全体の方向性またチャートの変数の関係を表すためにチャートの近似曲線を追加できます。以下は作業手順です。

|                                     |                                                                        |                                                                  |
| ----------------------------------- | ---------------------------------------------------------------------- | ---------------------------------------------------------------- |
| 1\. **設定を変更します**             | ![Tutorials-Navigate-Settings](images/Tutorials-Navigate-Settings.png) | 表示形式エディターの**設定**セクションへ移動します。      |
| 2\. **チャートの近似曲線アクセスします** | ![Tutorials-Expand-Trendlines](images/Tutorials-Expand-Trendlines.png) | 下矢印を選択して、[チャートの近似曲線] ドロップダウンを展開します。|
| 3\. **チャートの近似曲線を選択します**    | ![Select-Predefined-Trendline](images/Select-Predefined-Trendline.png) | Reveal の定義済みの近似曲線の 1 つを選択します。                    |

<a name='change-axis-configuration'></a>
### 軸の構成の変更

[ゲージのバンド](~/jp/data-visualizations/gauge-views.html#bands-configuration)と同様に、チャート軸構成でチャートの最小と最大値を設定できます。この機能を使用して、特定のデータ含有や除外ができます。

|                                        |                                                                                      |                                                                                                                                       |
| -------------------------------------- | ------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------- |
| 1\. **設定を変更します**                | ![Tutorials-Navigate-Settings](images/Tutorials-Navigate-Settings.png)               | 表示形式エディターの**設定**セクションへ移動します。                                                                           |
| 2\. **範囲の設定へアクセスします** | ![Tutorials-Axis-Bounds](images/Tutorials-Axis-Bounds.png)                           | 軸範囲に移動します。                                                                                                              |
| 3\. **デフォルト選択を変更します**   | ![Tutorials-Change-Default-Selection](images/Tutorials-Change-Default-Selection.png) | 最大値または最小値 (または両方) 値を設定するかどうかに基づいて、チャートの開始値または終了値を入力します。|

<a name='set-logarithmic-axis'></a>
### 軸を対数軸として設定

|                                           |                                                                          |                                                             |
| ----------------------------------------- | ------------------------------------------------------------------------ | ----------------------------------------------------------- |
| 1\. **設定を変更します**                   | ![Tutorials-Navigate-Settings](images/Tutorials-Navigate-Settings.png)   | 表示形式エディターの**設定**セクションへ移動します。|
| 2\. **軸オプションにアクセスする**            | ![Tutorials-Axis-Bounds](images/Tutorials-Axis-Bounds.png)               | 下矢印を選択して、軸ドロップダウンを展開します。       |
| 3\. **軸構成タイプを選択します** | ![Tutorials-Charts-Logarithmic](images/Tutorials-Charts-Logarithmic.png) |「対数」を選択します。                                       |

<a name='change-start-position'></a>
### ドーナツ型と円チャートの開始位置の変更

|                                                   |                                                                                |                                                                                           |
| ------------------------------------------------- | ------------------------------------------------------------------------------ | ----------------------------------------------------------------------------------------- |
| 1\. **設定を変更します**                           | ![Tutorials-Navigate-Settings](images/Tutorials-Navigate-Settings.png)         | 表示形式エディターの**設定**セクションへ移動します。                               |
| 2\. **開始位置セクションにアクセスする**         | ![Tutorials-Start-Position](images/Tutorials-Start-Position.png)               | 下矢印を選択して、開始位置ドロップダウンを展開します。                           |
| 3\. **開始位置オプションの 1 つを選択します**。 | ![Tutorials-Select-Start-Position](images/Tutorials-Select-Start-Position.png) | チャートに対して、Reveal の事前定義された開始位置 (0°、90°、180°、または 270°) のいずれかを選択します。 |

<a name='change-slice-labels'></a>
### ドーナツ型、ファンネルと円チャートのスライスのラベルの変更

|                                                |                                                                          |                                                                                                        |
| ---------------------------------------------- | ------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------ |
| 1\. **設定を変更します**                        | ![Tutorials-Navigate-Settings](images/Tutorials-Navigate-Settings.png)   | 表示形式エディターの**設定**セクションへ移動します。                                            |
| 2\. **スライス ラベルのセクションにアクセスする**         | ![Tutorials-Slice-Label](images/Tutorials-Slice-Label.png)               | 下矢印を選択して、スライス ラベル ドロップダウンを展開します。                                          |
| 3\. **スライス ラベル オプションの 1 つを選択します**。 | ![Tutorials-Select-Slice-Label](images/Tutorials-Select-Slice-Label.png) | Reveal の事前定義されたラベル付けオプション (パーセント、値、または値とパーセント) のいずれかを選択します。 |
