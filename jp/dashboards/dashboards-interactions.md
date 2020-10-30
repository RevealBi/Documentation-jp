## ダッシュボードを操作する

初期画面でダッシュボードのサムネイル画像をクリックし、既存のダッシュボードを開くことができます。

<img src="images/dashboard-opened-edit-mode.png" alt="dashboard opened in edit mode" width="80%"/>


さまざまな方法でダッシュボードの表示形式の **UI 操作が**できます。たとえば、表示形式がグリッド ビューの場合、水平方向および垂直方向にスクロールできます。チャート ビューではパン、ズームがサポートされています。また、基になるデータ モデルがサポートしている場合は、ドリルダウンとドリルアップの実行が可能になります。

<a name='maximized-view'></a>
### 最大化されたビュー

ダッシュボードが開くと、表示形式のいずれかにカーソルをホバーし、右上隅の矢印をクリック/タップすることで**最大化**できます。

<img src="images/visualization-maximizing-arrow.png" alt="maximizing arrow in the top right corner" width="80%"/>

最大化されたビューは、より多くの情報の表示を可能にします。

<img src="images/maximized-visualization.png" alt="maximized visualization view" width="80%"/>

さらに、このモードでは、右上隅の**小さなチャート アイコン**をタップし、最大化されたビューを他の表示形式に切り替えることができます。エディターで使用されたデータに基づいて、さまざまな表示形式が表示されます。データで適切に機能するチャート タイプのみが提供されます。 

変更された表示形式を保存する場合は、編集権限を持ち、[ダッシュボード編集モード](#view-edit-mode)で右上隅のチェック アイコンを選択して変更を明示的に保存する必要があります。自分で作成したか、[管理者または変更の権限](~/jp/dashboards/sharing-dashboards/share-a-dashboard.html#access-permissions)で共有しているダッシュボードの編集権限があります。 

<img src="images/chart-change-visualization-view-mode.png" alt="chart change in visualization view mode" width="80%"/>

さらに、表示形式メニューの右上隅にある**チャート アイコン**をクリックすると、ビューを切り替え、チャートの背後のデータを表示できます。

<img src="images/flip-grid.png" alt="flip to grid" width="80%"/>

表示形式のデータ ビハインド表示で並べ替え (昇順または降順) を適用できます。グリッドの並べ替え詳細については、[グリッド ビュー](~/jp/data-visualizations/grid-chart.html)トピックをご覧ください。

元の表示形式へ戻すために、**[元の形式を表示]** リンクを選択します。

<img src="images/change-visualization-show-original.png" alt="show original link" width="80%"/>

### 通常のツールチップ

特定の表示形式 (タッチ環境で長押すと) をクリックすると、ツールチップ ポップアップが表示されます。ツールチップは、次のようにチャートの特定のポイントで値を表示するのに役立ちます:

<img src="images/tooltips-popups.png" alt="tooltips popups on visualizations" width="80%"/>

通常のツールチップを閉じるには、離れてクリックするかタップしてください。

### ツールチップのホバーと十字線

**インタラクション**メニューでは、次の 2 つのオプションを有効にできます: *ツールチップのホバー*と*十字線*。どちらもダッシュボード ビュー モードの場合のみ使用できます。ダッシュボード編集モードでは使用できません。

<img src="images/dashboard-interactions-menu.png" alt="Accessing Reveal's Dashboard Interactions menu" width="80%"/>

  - *ホバー ツールチップ*を有効にすると、データにホバーした際に (タッチ環境で長押しした際に) **ツールチップ** ポップアップが表示されます。

    <img src="images/tooltips-hover.png" alt="Reveal displays tooltips when hovering over data" width="80%"/>

    データをクリックすると (タッチ環境でドラッグ ツールチップをリリースすると)、ツールチップのインタラクションが適用可能な場合、ドリルダウン、ドリルアップ、およびリンク済みのダッシュボードなどのインタラクションで **[ツール]** セクションにアクセスできます。

  - *十字線*を有効にすると、Reveal はツールチップとともに十字線要素を表示します。ツールチップにより多くのコンテキストを与えます。

    <img src="images/crosshairs-enabled.png" alt="Reveal displays crosshairs along with tooltips" width="80%"/>

十字線は、現在次のデータ可視化でサポートされています: 散布、バブル、エリア、ローソク足、折れ線、OHLC、スプライン、スプライン エリア、ステップ エリア、ステップ折れ線。

ローソク足と OHLC の表示形式は、水平の十字線のみを表します。垂直十字線を含めると、データ ポイントの線が見えにくくなります。

### ツールチップの合計

ツールチップを表示するときに、カテゴリごとに合計値を表示するように構成できます。

<img src="images/tooltips-totals.png" alt="Reveal Portrait Orientation" width="80%"/>

この機能を有効にするには、次のように、[設定] \> [ツールチップで合計を表示] に移動します:

<img src="images/tooltips-configuration.png" alt="Reveal Portrait Orientation" width="80%"/>

合計を有効にする場合、表示形式で複数の値を表示するためにカテゴリを追加したことを確認してください。

<a name='view-edit-mode'></a>
### ビュー & 編集モード

ダッシュボードを初めて開いた場合、**ビュー モード**でブラウズすることになります。このモードでは、表示された情報のナビゲーションやフィルタリングが可能ですが、ダッシュボード定義を変更することはできません。

ダッシュボードへの変更を適用するためには、**ダッシュボードの編集モード**に切り替える必要があります。ダッシュボードの右上隅のオーバーフロー メニューから [編集] を選択します。これにより、*自動レイアウト*、ダッシュボード *テーマ*の適用、ダッシュボードのエクスポートなどの編集オプションが有効になります。

以下は、*ダッシュボード編集*モードのダッシュボードです:

<img src="images/dashboard-opened-edit-mode.png" alt="dashboard opened in edit mode" width="80%"/>

**編集モードを終了するには**、右上隅の*チェック アイコン*を選択するだけです。これにより、*表示モード*に戻ります。

### ダッシュボード フィルター

ダッシュボードまたは表示形式レベルで情報をフィルターできます。

  - [**ダッシュボード フィルター**](~/jp/filters/dashboard-filters.html) は、ダッシュボード編集モードを開くと使用できます (このモードにアクセスするには、ダッシュボードのオーバーフロー メニューから **[編集]** を選択します)。画面の左上隅に、現在のダッシュボード フィルターと、新しいフィルターを追加するオプションが表示されます。

  - [**表示形式フィルター**](~/jp/filters/Visualization-Filters.html) (つまり、クイック フィルター) は最大化モードで表示されます。これらは、表示形式の名前の下にある表示形式の上部セクションにあります。

ダッシュボードと表示形式フィルターの詳細については、[このセクション](~/jp/filters/overview.html)をご覧ください。

### 表示形式の自動レイアウト

Reveal の自動レイアウトは、デバイスのサイズ制約と表示形式の量に基づいて、ダッシュボードのすべての表示形式を動的にサイズ変更します。

<img src="images/auto-layout-dashboard.png" alt="auto layout view and resizing of dashboards" width="80%"/>

自動レイアウトが有効なときに表示形式のサイズを変更するには、隅を下または横にドラッグするだけです。これにより、*自動レイアウト* が自動的にオフになります。
