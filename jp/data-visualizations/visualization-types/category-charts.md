---
title: 表示形式にカテゴリ チャートを使用する方法
_description: カテゴリ チャートを使用して表示形式を向上させる方法を説明します。
_language: ja
---

# カテゴリ チャート

これらのチャートを使用して、カテゴリを定量的情報に関連付けます。

<img src="images/category-charts-list.png" alt="Category charts variations" class="responsive-img" width="85%"/>

データに適している限り、表示形式オプション メニューに表示されたチャート アイコンをどれでも選択できます。Reveal はデータセットの最初の数字の列を選択し、選択したチャート タイプのデータ系列の要件と一致させようと試みます。

<img src="../images/various-charts-example.png" alt="Various charts visualizations in a dashboard" class="responsive-img" width="88%"/>

たとえば、柱状チャートでは、すべての数値列がチャートに追加されます。Reveal の列の自動選択は、チャートの設定の構成で変更できます。

## チャートの近似曲線

チャートの設定でトレンドラインの表示を有効にできます。このラインはアルゴリズムに基づいてチャートにラインを表示します。近似曲線でデータセットの傾向を把握し、意思決定のためのしきい値を定義できます。
サポートされるトレンドラインは、二次フィット、キュービック フィット、四次フィット、対数フィット、指数フィト、べき乗フィット、単純平均、指数平均、修正平均、累加平均、加重平均です。

<img src="images/chart-trendline-option.png" alt="Chart trendline options" class="responsive-img" width="88%"/>

## パーセンテージの配分

積層型シリーズ チャートにもこの機能を構成できます。0-100 のデフォルト スケールを上書きして、チャートで値のパーセンテージ配分を表示形式できます。

<img src="images/percentage-distribution-option-stacked-series-charts.png" alt="Pivot editor view stacked percentage distribution setting" class="responsive-img" width="88%"/>

## 開始位置とスライス ラベル

円チャートおよびドーナツ チャートでチャートのスライスを回転する開始位置を構成し、データの表示順序を変更できます。

<img src="images/start-position-setting-doughnut-chart-example.png" alt="Start position setting while using a doughnut chart" class="responsive-img" width="88%"/>

ファンネル、円チャート、およびドーナツ型チャート、値やパーセンテージ、またはその両方を同時に表示するスライス ラベルを構成できます。

<img src="images/slice-label-setting-doughnut-chart-example.png" alt="Pivot editor slice labels setting" class="responsive-img" width="88%"/>

## 値 0 の要素を表示するために円チャートおよびドーナツ チャートの凡例を有効化

円およびドーナツ チャートの表示形式の凡例には、[ラベル] に選択されたフィールドのすべてのデータ (値 0 の要素を含む) を表示するオプションがあります。

この設定を有効にするには、以下の画像のように、表示形式エディターの [設定] に移動し、[0 (ゼロ) 値を凡例に表示] を選択します。

<img src="images/pie-chart-example-legends-value-zero-setting.png" alt="Enabling the legend setting in the visualization editor" class="responsive-img" width="88%"/>

