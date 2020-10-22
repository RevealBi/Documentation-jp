## RevealView オブジェクトの設定

### 概要

__RevealView__ コンポーネントを使用して、エンドユーザーに対するさまざまな機能を有効または無効にすることができます。
  - **UI 要素の表示/非表示** - ShowFilters プロパティは初期化時に __RevealView__ によって読み込まれ、その値に基づいてグローバル フィルター UI をユーザーに表示または非表示にします。その他の同様のプロパティには、ShowExportButton、CanEdit、showChangeDataSource、MaximizedVisualization があります。

  - **ダッシュボードの指定** - どのダッシュボードをレンダリングするかを指定するには、dashboard プロパティを使用します。[**ダッシュボード ファイルの読み込み**](loading-dashboards.html)に示すように、the dashboard must be instantiated by using __RVDashboard__ constructor, which receives either a Stream or a path string pointing to a location of the rdash file on the local file system. 

  - **グローバル フィルター値の選択** - ダッシュボードのロード時に既存のグローバル フィルターに対して最初に選択される値を指定できます。

### コード

次のコードスニペットは、ダッシュボードを読み込む方法を示し、選択された「Territory」値を「Americas」に設定します。したがって、ダッシュボードには「Americas」でフィルタリングされたデータが表示されます。

``` csharp
var revealView = new RevealView();
var dashboard = new RVDashboard(path);
dashboard.filters.GetByTitle("Territory").selectedValues = new List<object>() { "Americas" };
revealView.Dashboard = dashboard;
```



