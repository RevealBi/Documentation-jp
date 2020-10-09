## RevealView オブジェクトの設定

### 概要

**RevealSettings** オブジェクトをパラメーターとして渡している間に **RevealView** コンポーネントをインスタンス化できます。

**RevealSettings** オブジェクトを使用して、エンドユーザーに対するさまざまな機能を有効または無効にすることができます。

  - **UI 要素の表示/非表示** -  *ShowFilters* プロパティは初期化時に **RevealView** によって読み込まれ、その値に基づいてグローバル フィルター UI をユーザーに表示または非表示にします。他の同様のプロパティは、*showExportImage*、*canEdit*、*showChangeDataSource*、*maximizedVisualization*です。
  - **ダッシュボードの指定** - どのダッシュボードをレンダリングするかを指定するには、dashboard プロパティを使用します。[**Web Client SDK のインスタンス化**](~/jp/developer/general/setup-configuration-web.html#instantiate-web-client-sdk)で説明の通り、ダッシュボードは、dashboardId と、ダッシュボードがロードされたときに呼び出される成功コールバックを受け取る *RevealUtility.loadDashboard* メソッドを使用して取得する必要があります。
  - **ダッシュボード フィルター値の選択** - ダッシュボードのロード時に既存のダッシュボード フィルターに対して最初に選択される値を指定できます。Reveal アプリでは、ダッシュボードフィルターを使用して、ダッシュボードのすべての接続された表示形式に動的フィルタリングを適用できます。選択が変更されると、すべての表示形式が一度に更新します。詳細については、_Reveal のユーザー ガイド_ にある [**Reveal フィルター**](https://www.revealbi.io/help/filters)  を参照してください。

### コード

次のコードスニペットは、ダッシュボード「AppsStats」を読み込む方法を示しています。「application_name」 グローバル フィルターの選択値を 「App2」 に設定して、ダッシュボードには 「App2」 でフィルタリングされたデータが表示されます。

``` js
var dashboardId = "AppsStats";
var revealSettings = new RevealSettings(dashboardId);

RevealUtility.loadDashboard(dashboardId, function (dashboard) {
    revealSettings.dashboard = dashboard;

    var applicationNameFilter = dashboard.getFilterByTitle("application_name");
    revealSettings.setFilterSelectedValues(applicationNameFilter, ["App2"]);

    window.revealView = new RevealView("#revealView", revealSettings);
}, function (error) {
});
```

### 初期化

**RevealView** は、ダッシュボードが画面に表示される前の特定の時間である**初期化時**に **RevealSettings** を適用します。これによるいくつかの影響があります。

  - ダッシュボードのレンダリング後に設定オブジェクトを変更しても、すでにロードされているダッシュボードには影響しません。
  - ただし、ビューの作成後にダッシュボード フィルターの選択値を変更することはできます。これを行うには、RevealView オブジェクトの **setFilterSelectedValues** メソッドを使用する必要があります。
  - **RevealSettings** オブジェクトのプロパティを変更した場合 (canEdit、canSaveAsなど)、**RevealView** の新しいインスタンスを作成する必要があります。
