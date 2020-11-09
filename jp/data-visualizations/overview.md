## データ表示形式

Reveal は、さまざまな表示形式を提供することにより、ビジネス データから可能な限り多くの気付きを得るのに役立ちます。

### 表示形式の概要

ビジネス データを理解するために Reveal は情報の可視化をカスタマイズする複数のオプションを提供します。これらは表示形式といいます。すべてのダッシュボードは 1 つ以上の表示形式で構成されます。

以下に示すダッシュボードには、製造のさまざまな側面を分析する多様な表示形式が含まれています。

<img src="images/data-visualizations-example.png" alt="Reveal's log in screen" width="80%"/>

### 適切なチャート タイプの選択

最適なチャート タイプを選択するには、データを確認し、表示形式で伝えようとしているストーリーを見つけるのに役立つ質問に答える必要があります。

データを比較することか、データの分布を示すことあるいはデータを全体の一部分として提示しようとしていますか? 財務、マーケティング、または販売データのトレンド分析を行っていますか? 日付/時刻軸が必要ですか? データ間の関係を調べていますか? または、読みやすく、簡単なストーリーを伝える KPI とゲージを表示したいだけですか? データを地図上にプロットすることは重要ですか?

データを通じて何を表示したいかについて回答し、以下の表を使用して最適なチャートを選択してください。

<style type="text/css">
td { 
  border: 1px solid black;
}
</style>
<table>
<colgroup>
<col style="width: 10%" />
<col style="width: 10%" />
<col style="width: 10%" />
<col style="width: 10%" />
<col style="width: 10%" />
<col style="width: 10%" />
<col style="width: 10%" />
<col style="width: 10%" />
<col style="width: 10%" />
<col style="width: 10%" />
</colgroup>
<body>
  <tr>
    <td><b>データの比較</b></td>
    <td>
      <img src="images/Bar-Chart.png" alt="Bar Chart" /><br/>
      <a href="visualization-types/category-charts.md">棒</a>
    </td>
    <td>
      <img src="images/Column-chart.png" alt="Column Chart" /><br/>
      <a href="visualization-types/category-charts.md">柱状</а>
    </td>
    <td>
      <img src="images/Area-chart.png" alt="Area Chart" /><br/>
      <a href="visualization-types/category-charts.md">エリア</а>
    </td>
    <td>
      <img src="images/Spline-chart.png" alt="Spline Chart" /><br/>
      <a href="visualization-types/category-charts.md">スプライン</а>
    </td>
    <td>
      <img src="images/Combo-chart.png" alt="Combo Chart" /><br/>
      <a href="visualization-types/combo-charts.md">複合</a>
    </td>
    <td>
      <img src="images/Circular-chart.png" alt="Circular Gauge" /><br/>
      <a href="visualization-types/gauge-charts.html#circular-gauge">円型</a>
    </td>
    <td>
      <img src="images/Spline-Area-chart.png" alt="Spline with Area Chart" /><br/>
      <a href="visualization-types/category-charts.md">スプライン エリア</a>
    </td>
    <td>
      <img src="images/OHLC-chart.png" alt="OHLC Chart" /><br/>
      <a href="visualization-types/financial-charts.md">OHLC</a>
    </td>
    <td>
      <img src="images/Candlestick-chart.png" alt="Candlestick Chart" /><br/>
      <a href="visualization-types/financial-charts.md">ロウソク足</a>
    </td>
  </tr>
  <tr>
    <td><b>部分から全体</b></td>
    <td>
      <img src="images/Stacked-Column-Chart.png" alt="Stacked Column Chart" /><br/>
      <a href="visualization-types/category-charts.md">積層型柱状</a>
    </td>
    <td>
      <img src="images/Stacked-Bar-Chart.png" alt="Stacked Bar Chart" /><br/>
      <a href="visualization-types/category-charts.md">積層型棒</a>
    </td>
    <td>
      <img src="images/Stacked-Area-Chart.png" alt="Stacked Area Chart" /><br/>
      <a href="visualization-types/category-charts.md">積層型エリア</a>
    </td>
    <td>
      <img src="images/Pie-Chart.png" alt="Pie Chart" /><br/>
      <a href="visualization-types/category-charts.md">円</a>
    </td>
    <td>
      <img src="images/Doughnut-Chart.png" alt="Dougnut Chart" /><br/>
      <a href="visualization-types/category-charts.md">ドーナツ型</a>
    </td>
    <td>
      <img src ="images/funnel-chart.png" alt="Funnel Chart" /><br/>
      <a href="visualization-types/category-charts.md">ファンネル</a>
    </td>
    <td>
      <img src ="images/treemap-chart.png" alt="Treemap Chart" /><br/>
      <a href="visualization-types/treemap-charts.md">ツリーマップ</a>
    </td>
    <td></td>
    <td></td>
  </tr>
  <tr>
    <td><b>データ分布</b></td>
    <td>
      <img src="images/step-area-Chart.png" alt="Step Area Chart" /><br/>
      <a href="visualization-types/category-charts.md">ステップ エリア</a>
    </td>
    <td>
      <img src="images/Stacked-Column-Chart.png" alt="Stacked Column Chart" /><br/>
      <a href="visualization-types/category-charts.md">積層型柱状</a>
    </td>
    <td>
      <img src="images/scatter-chart.png" alt="Scatter Chart" /><br/>
      <a href="visualization-types/scatter-bubble-charts.md">散布</а>
    </td>
    <td>
      <img src="images/bubble-Chart.png" alt="Bubble Chart" /><br/>
      <a href="visualization-types/scatter-bubble-charts.md">バブル</а>
    </td>
    <td></td>
    <td />
    <td />
    <td />
    <td />
  <tr>
    <td><b>データ トレンド分析<b/></td>
    <td>
      <img src="images/line-chart.png" alt="Line Chart" /><br/>
      <a href="visualization-types/category-charts.md">折れ線</a>
    </td>
    <td>
      <img src="images/spline-Chart.png" alt="Spline Chart" /><br/>
      <a href="visualization-types/category-charts.md">スプライン</a>
    </td>
    <td>
      <img src="images/Combo-Chart.png" alt="Combo Chart" /><br/>
      <a href="visualization-types/combo-charts.md">複合</a>
    </td>
    <td>
      <img src="images/ohlc-Chart.png" alt="OHLC Chart" /><br/>
      <a href="visualization-types/financial-charts.md">OHLC</a>
    </td>
    <td>
      <img src="images/candlestick-Chart.png" alt="Candlestick Chart" /><br/>
      <a href="visualization-types/financial-charts.md">ロウソク足</a>
    </td>
    <td>
      <img src="images/radial-Chart.png" alt="Radial Chart" /><br/>
      <a href="visualization-types/radial-charts.md">ラジアル</a>
    </td>
    <td />
    <td />
    <td />
    <td />
  </tr>
  <tr>
  <td><b>データの関係</b></td>
  <td>
    <img src="images/scatter-chart.png" alt="Scatter Chart" /><br/>
    <a href="visualization-types/scatter-bubble-charts.md">散布</а>
  </td>
  <td>
    <img src="images/Bubble-chart.png" alt="Bubble Chart" /><br/>
    <a href="visualization-types/scatter-bubble-charts.md">バブル</а>
  </td>
  <td>
    <img src="images/line-chart.png" alt="Line Chart" /><br/>
    <a href="visualization-types/category-charts.md">折れ線</a>
  </td>
  <td />
  <td />
  <td />
  <td />
  <td />
  <td />
  </tr>
  <tr>
  <td><b>KPI とゲージ</b></td>
  <td>
    <img src="images/bullet-graph-gauge.png" alt="Bullet Graph Gauge" /><br/>
    <a href="visualization-types/gauge-charts.html#bullet-graph">ブレット グラフ</a>
  </td>
  <td>
    <img src="images/linear-gauge.png" alt="Linear Gauge" /><br/>
    <a href="visualization-types/gauge-charts.html#linear-gauge">リニア</а>
  </td>
  <td>
    <img src="images/text-gauge.png" alt="Text Chart" /><br/>
    <a href="visualization-types/gauge-charts.html#text-gauge">テキスト</a>
  </td>
  <td>
    <img src="images/kpi.png" alt="KPI Gauge" /><br/>
    <a href="visualization-types/kpi-gauge.md">KPI</a>
  </td>
  <td>
    <img src="images/circular-gauge.png" alt="Circular Gauge" /><br/>
    <a href="visualization-types/gauge-charts.html#circular-gauge">円型</a>
  </td>
    <td />
    <td />
    <td />
    <td />
  </tr>
  <tr>
  <td><b>地理的データ</b></td>
  <td>
    <img src="images/choropleth-map.png" alt="Choropleth Map" /><br/>
    <a href="visualization-types/choropleth-map/choropleth-map.md">階級区分図</a>
  </td>
  <td>
    <img src="images/scatter-map.png" alt="Scatter Map" /><br/>
    <a href="visualization-types/scatter-map/scatter-map.md">散布図</a>
  </td>
  <td />
  <td />
  <td />
  <td />
  <td />
  <td />
  <td />
</body>
</table>

これらの各表示形式の使用方法に関する詳細が必要な場合は、表のハイパーリンクを使用してください。

### トピックの概要 

[表示形式タイプ] ドロップダウン (左側の目次を参照) には、Reveal が提供するすべての種類のチャートの A-Z リストがあります。

[表示形式エディターの操作](visualizations-editor.md)では、表示形式エディターの主要部分を紹介し、最初の表示形式の作成を開始する方法も学習します。

[フィールド](fields/overview.md) トピックでは、表示形式の構築に使用しているデータ フィールドの最も価値のある側面を、集計、フィルタリング、および強調表示する方法の詳細を確認できます。

[表示形式の再利用](reusing-visualizations.md)には、ダッシュボードの作成プロセスを高速化する方法に関する役立つアイデアがあります。

[統計関数](statistical-functions.md)には、Reveal で高度な予測分析がどのように機能するかが記載されています。**時系列予測**、**線形回帰**、および**外れ値の検出**の機能を使用して、データからより多くのインサイトを得る方法をご覧ください。


### 表示形式チュートリアル 

このセクションでは、Reveal の表示形式の作成手順を説明します。すべてのセクションのデータ可視化に使用しているデータソースは、[こちら](http://download.infragistics.com/reportplus/help/samples/Reveal_Visualization_Tutorials.xlsx)からダウンロードしてください。表示形式がサポートされる各ウィジェットの情報については、ヘルプの [データ表示] セクションを参照してください。

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><img src="images/Area-Chart.png" alt="Area Chart" /><br />
</p>
<p><a href="~/jp/visualization-tutorials/simple-charts.md">エリア</a><br />
</p></td>
<td><p><img src="images/Bar-Chart.png" alt="Bar Chart" /><br />
</p>
<p><a href="~/jp/visualization-tutorials/simple-charts.md">棒</a><br />
</p></td>
<td><p><img src="images/Bullet-Graph-Gauge.png" alt="Bullet Graph Gauge" /><br />
</p>
<p><a href="~/jp/visualization-tutorials/gauge-views.md">ブレット グラフ</a><br />
</p></td>
<td><p><img src="images/Candlestick-Chart.png" alt="Candlestick Chart" /><br />
</p>
<p><a href="~/jp/visualization-tutorials/candlestick-chart.md">ローソク足</a><br />
</p></td>
<td><p><img src="images/Circular-Gauge.png" alt="Circular Gauge" /><br />
</p>
<p><a href="~/jp/visualization-tutorials/gauge-views.md">円型</a><br />
</p></td>
</tr>
<tr class="even">
<td><p><img src="images/Column-Chart.png" alt="Column Chart" /><br />
</p>
<p><a href="~/jp/visualization-tutorials/simple-charts.md">柱状</a><br />
</p></td>
<td><p><img src="images/Doughnut-Chart.png" alt="Doughnut Chart" /><br />
</p>
<p><a href="~/jp/visualization-tutorials/simple-charts.md">ドーナツ型</a><br />
</p></td>
<td><p><img src="images/Funnel-Chart.png" alt="Funnel Chart" /><br />
</p>
<p><a href="~/jp/visualization-tutorials/simple-charts.md">ファンネル</a><br />
</p></td>
<td><p><img src="images/Web-View.png" alt="Image View" /><br />
</p>
<p><a href="~/jp/visualization-tutorials/image-view.md">画像</a><br />
</p></td>
<td><p><img src="images/kpi.png" alt="kpi" /><br />
</p>
<p><a href="~/jp/visualization-tutorials/kpi-gauge.md">KPI</a><br />
</p></td>
</tr>
<tr class="odd">
<td><p><img src="images/Line-Chart.png" alt="Line Chart" /><br />
</p>
<p><a href="~/jp/visualization-tutorials/simple-charts.md">折れ線</a><br />
</p></td>
<td><p><img src="images/Linear-Gauge.png" alt="Linear Gauge" /><br />
</p>
<p><a href="~/jp/visualization-tutorials/gauge-views.md">リニア</a><br />
</p></td>
<td><p><img src="images/OHLC-Chart.png" alt="OHLC Chart" /><br />
</p>
<p><a href="~/jp/visualization-tutorials/ohlc-chart.md">OHLC チャート</a><br />
</p></td>
<td><p><img src="images/Pie-Chart.png" alt="Pie Chart" /><br />
</p>
<p><a href="~/jp/visualization-tutorials/simple-charts.md">円</a><br />
</p></td>
<td><p><img src="images/radial-chart.png" alt="Radial Chart" /><br />
</p>
<p><a href="~/jp/visualization-tutorials/simple-charts.md">ラジアル</a><br />
</p></td>
</tr>
<tr class="even">
<td><p><img src="images/Sparkline-Chart.png" alt="Sparkline Chart" /><br />
</p>
<p><a href="~/jp/visualization-tutorials/sparkline-charts.md">スパークライン</a><br />
</p></td>
<td><p><img src="images/Spline-Chart.png" alt="Spline Chart" /><br />
</p>
<p><a href="~/jp/visualization-tutorials/simple-charts.md">スプライン</a><br />
</p></td>
<td><p><img src="images/Spline-Area.png" alt="Spline Area" /><br />
</p>
<p><a href="~/jp/visualization-tutorials/simple-charts.md">スプライン エリア</a><br />
</p></td>
<td><p><img src="images/Stacked-Area-Chart.png" alt="Stacked Area Chart" /><br />
</p>
<p><a href="~/jp/visualization-tutorials/stacked-charts.md">積層型エリア</a><br />
</p></td>
<td><p><img src="images/Stacked-Bar-Chart.png" alt="Stacked Bar Chart" /><br />
</p>
<p><a href="~/jp/visualization-tutorials/stacked-charts.md">積層型棒</a><br />
</p></td>
</tr>
<tr class="odd">
<td><p><img src="images/Stacked-Column-Chart.png" alt="Stacked Column Chart" /><br />
</p>
<p><a href="~/jp/visualization-tutorials/stacked-charts.md">積層型柱状</a><br />
</p></td>
<td><p><img src="images/Step-Area-Chart.png" alt="Step Area Chart" /><br />
</p>
<p><a href="~/jp/visualization-tutorials/simple-charts.md">ステップ エリア</a><br />
</p></td>
<td><p><img src="images/Step-Line-Chart.png" alt="Step Line Chart" /><br />
</p>
<p><a href="~/jp/visualization-tutorials/simple-charts.md">ステップ折れ線</a><br />
</p></td>
<td><p><img src="images/Text-Gauge.png" alt="Text Gauge" /><br />
</p>
<p><a href="~/jp/visualization-tutorials/gauge-views.md">テキスト</a><br />
</p></td>
<td><p><img src="images/Text-View.png" alt="Text View" /><br />
</p>
<p><a href="~/jp/visualization-tutorials/text-view.md">テキスト ビュー</a><br />
</p></td>
</tr>
</tbody>
</table>

