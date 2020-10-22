## RevealView オブジェクトの設定

### 概要

__$.ig.RevealView__ コンポーネントは、Reveal ビューを描画する必要がある DOM 要素を指すセレクターを渡してインスタンス化できます。このコンポネントを使用して、エンドユーザーに対して次のさまざまな機能を有効または無効にすることができます:

  - **UI 要素の表示/非表示** -  *ShowFilters* プロパティは初期化時に **RevealView** によって読み込まれ、その値に基づいてグローバル フィルター UI をユーザーに表示または非表示にします。他の同様のプロパティは、*showExportImage*、*canEdit*、*showChangeDataSource*、*maximizedVisualization*です。
  - **ダッシュボードの指定** - どのダッシュボードをレンダリングするかを指定するには、dashboard プロパティを使用します。[**Web Client SDK のインスタンス化**](~/jp/developer/setup-configuration/setup-configuration-web.html#instantiate-web-client-sdk)で説明の通り、ダッシュボードは、dashboardId と、ダッシュボードがロードされたときに呼び出される成功コールバックを受け取る *$.ig.RVDashboard.loadDashboard* メソッドを使用して取得する必要があります。
  - **ダッシュボード フィルター値の選択** - ダッシュボードのロード時に既存のダッシュボード フィルターに対して最初に選択される値を指定できます。Reveal アプリでは、ダッシュボードフィルターを使用して、ダッシュボードのすべての接続された表示形式に動的フィルタリングを適用できます。選択が変更されると、すべての表示形式が一度に更新します。詳細については、_Reveal のユーザー ガイド_ にある [**Reveal フィルター**](https://www.revealbi.io/help/filters)  を参照してください。

### コード

次のコードスニペットは、ダッシュボード「AppsStats」を読み込む方法を示しています。「application_name」グローバル フィルターの選択値を「App2」に設定して、ダッシュボードには「App2」でフィルタリングされたデータが表示されます。

``` js
var dashboardId = "AppsStats";

$.ig.RVDashboard.loadDashboard(dashboardId, function (dashboard) {
    dashboard.filters.getByTitle("application_name").selectedValues = ["App2"];

    var revealView = new $.ig.RevealView("#revealView");
    revealView.dashboard = dashboard;
}, function (error) {
});
```

