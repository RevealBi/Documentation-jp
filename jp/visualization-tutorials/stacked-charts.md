## 積層型チャートを作成する方法

このチュートリアルはサンプル スプレッドシートを使用し積層型チャートを作成する方法を説明します。

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><img src="images/charts-stacked-area.png" alt="charts stacked area" /><br />
</p>
<p><a href="#create-stacked-chart">積層型エリア チャート</a><br />
</p></td>
<td><p><img src="images/charts-stacked-bar.png" alt="charts stacked bar" /><br />
</p>
<p><a href="#create-stacked-chart">積層型棒チャート</a><br />
</p></td>
<td><p><img src="images/charts-stacked-columns.png" alt="charts stacked columns" /><br />
</p>
<p><a href="#create-stacked-chart">積層型柱状チャート</a><br />
</p></td>
</tr>
<tr class="even">
<td><p><img src="images/stacked-columns-bounds.png" alt="stacked columns bounds" /><br />
</p>
<p><a href="#change-axis-configuration">しきい値の積層型柱状</a><br />
</p></td>
<td><p><img src="images/stacked-columns-logarithmic.png" alt="stacked columns logarithmic" /><br />
</p>
<p><a href="#set-logarithmic-axis">対数を含む積層型柱状チャートの構成</a><br />
</p></td>
<td><p><img src="images/stacked-chart-percentage-distribution.png" alt="stacked chart percentage distribution" /><br />
</p>
<p><a href="#enable-percentage-distribution">百分率分布を含む積層型柱状チャート</a><br />
</p></td>
</tr>
</tbody>
</table>

積層型チャート ビューのガイドは、以下のリンクから参照してください。

  - [積層型柱状チャートを作成する方法](#積層型チャートの作成)

  - [積層型チャートのタイプを変更する方法](#change-chart-type)

  - [軸の構成を変更する](#change-axis-configuration)

  - [軸の構成を対数に変更する](#set-logarithmic-axis)

  - [百分率分布を有効にする方法](#enable-percentage-distribution)

### 重要なコンセプト

積層型チャートは、3 つのレイアウトから選択できます - [エリア](#積層型チャートの作成)、[柱状](#積層型チャートの作成)および [棒](#積層型チャートの作成)。

以下の項目も設定できます。

  - **軸の構成**: 軸の構成でチャートの最大値と最小値を構成できます。デフォルトで最小値は 0 に設定され、最大値は使用されるデータによって設定されます。

      - **対数軸構成**: [対数] ボックスをチェックする場合、値のスケールは通常のリニア スケールを使用する代わりに大きさを使用するリニア スケール以外で計算されます。

### サンプル データ ソース

このチュートリアルでは [Reveal チュートリアル スプレッドシート](http://download.infragistics.com/reportplus/help/samples/Reveal_Visualization_Tutorials.xlsx) の [Stacked Charts] のシートを使用します。

>[!NOTE]
このリリースでは、ローカル ファイルとしての Excel ファイルはサポートされていません。チュートリアルを実行するには、サポートされているクラウド サービスのいずれかにファイルをアップロードするか、[Web リソース](datasources/supported-data-sources/web-resource.html)として追加してください。

</div>

<a name='create-stacked-chart'></a>
### 積層型チャートの作成

|                                          |                                                                                                        |                                                                                                                                                                                                                                                 |
| ---------------------------------------- | ------------------------------------------------------------------------------------------------------ | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 1\. **ダッシュボードの作成**               | ![Tutorials-Create-New-Dashboard](images/Tutorials-Create-New-Dashboard.png)                           | ダッシュボード ビューアーで、[ダッシュボード] 画面の右上隅にある [+] ボタンを選択します。                                                                                            |
| 2\. **データ ソースの構成**       | ![Tutorials-Select-Data-Source](images/Tutorials-Select-Data-Source.png)                               | [新しい表示形式] ウィンドウで、右下隅の [+] ボタンを選択し、データソースを選択します。                                                                                                                                  |
| 3\. **チュートリアル スプレッドシートの選択** | ![Tutorials-Select-Stacked-Charts-Spreadsheet](images/Tutorials-Select-Stacked-Charts-Spreadsheet.png) | データソースを設定したら、**Reveal チュートリアル スプレッドシート**を選択します。 次に、「Stacked Charts」シートを選択します。                                                                                                                       |
| 4\. **表示形式メニューを開く**     | ![Tutorials-Select-Change-Visualization](images/Tutorials-Select-Change-Visualization.png)             | 表示形式エディターのトップ バーで**グリッド アイコン**を選択します。                                                                                                                                                                          |
| 5\. **表示形式の選択**        | ![Tutorials-Stacked-Select-Visualization](images/Tutorials-Stacked-Select-Visualization.png)           | デフォルトで、表示形式のタイプは*グリッド*に設定されています。 **積層型**の表示形式のいずれかを選択します。                                                                                                                                           |
| 6\. **データの構成**               | ![Tutorials-Stacked-Charts-Organizing-Data](images/Tutorials-Stacked-Charts-Organizing-Data.png)       | 積層型チャートには 2 つ以上のフィールドをデータ エディターの [値] プレースホルダーへドラッグアンドドロップする必要があります。今の例で、1960、2003、2008 と 2010 を [値] へ、Country Name を [ラベル] へドラッグアンドドロップします。 |

<a name='change-chart-type'></a>
### 積層型チャートのタイプを変更する方法

必要に応じて、他の積層型チャートを選択できます。以下は作業手順です。

|                                      |                                                                                              |                                                                                                                                      |
| ------------------------------------ | -------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------ |
| 1\. **表示形式メニューを開く** | ![Tutorials-Select-Change-Visualization](images/Tutorials-Select-Change-Visualization.png)   | 表示形式エディターのトップ バーで**グリッド アイコン**を選択します。                                                                |
| 2\. **表示形式の選択**    | ![Tutorials-Stacked-Select-Visualization](images/Tutorials-Stacked-Select-Visualization.png) | 必要な積層型チャートのタイプを選択します。このセクションの上部に[各積層型チャートのタイプのプレビュー](#create-stacked-chart)があります。 |

<a name='change-axis-configuration'></a>
### 軸の構成の変更

[ゲージのバンド](~/jp/data-visualizations/gauge-charts#bands-configuration)と同様に、チャート軸構成でチャートの最小と最大値を設定できます。
この機能を使用して、特定のデータ含有や除外ができます。

|                                        |                                                                                      |                                                                                                                                       |
| -------------------------------------- | ------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------- |
| 1\. **設定の変更**                | ![Tutorials-Navigate-Settings](images/Tutorials-Navigate-Settings.png)               | 表示形式エディターの**設定**セクションへ移動します。                                                                           |
| 2\. **範囲の設定へアクセス** | ![Tutorials-Axis-Bounds](images/Tutorials-Axis-Bounds.png)                           | [軸範囲] へ移動します。                                                                                                              |
| 3\. **デフォルト選択の変更**   | ![Tutorials-Change-Default-Selection](images/Tutorials-Change-Default-Selection.png) | 最大値または最小値 (または両方) 値を設定するかどうかに基づいて、チャートの開始値または終了値を入力します。 |

<a name='set-logarithmic-axis'></a>
### 軸構成を対数的としての設定

|                                           |                                                                          |                                                             |
| ----------------------------------------- | ------------------------------------------------------------------------ | ----------------------------------------------------------- |
| 1\. **設定の変更**                   | ![Tutorials-Navigate-Settings](images/Tutorials-Navigate-Settings.png)   | 表示形式エディターの**設定**セクションへ移動します。 |
| 2\. **軸のオプションへアクセス**            | ![Tutorials-Axis-Bounds](images/Tutorials-Axis-Bounds.png)               | 下矢印を選択して、軸ドロップダウンを展開します。       |
| 3\. **軸構成タイプの選択** | ![Tutorials-Charts-Logarithmic](images/Tutorials-Charts-Logarithmic.png) | [対数] を選択します。                                       |

<a name='enable-percentage-distribution'></a>
### 百分率分布を有効します。

積層型チャートに百分率分布も構成できます。このタイプのチャートに値と百分率分布スケールを切り替えます。以下は作業手順です。

|                                        |                                                                                    |                                                                                           |
| -------------------------------------- | ---------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------- |
| 1\. **設定の変更**                | ![Tutorials-Navigate-Settings](images/Tutorials-Navigate-Settings.png)             | 表示形式エディターの**設定**セクションへ移動します。                               |
| 2\. **百分率分布を有効にする** | ![Tutorials-Percentage-Distribution](images/Tutorials-Percentage-Distribution.png) | [パーセンテージの配分] ボックスをチェックして、パーセンテージの配分設定を有効にします。|
