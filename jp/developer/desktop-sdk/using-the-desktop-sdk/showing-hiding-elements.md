# ユーザー インターフェイス要素の表示/非表示

__RevealView__ コンポーネントを使用して、エンドユーザーに対するさまざまな機能または UI 要素を有効または無効にすることができます。使用可能なプロパティの多くはブール型で簡単に使用できますが、その他のプロパティはそれほど多くありません。

以下に作成する *revealView* インスタンスは、このトピックのすべてのコード スニペットで使用されます。

``` csharp
var revealView = new RevealView();
```

すべてのプロパティは、初期化時に __RevealView__ によって読み取られ、その値に基づいて、ユーザーにさまざまな機能または UI 要素を表示または非表示にします。

## CanEdit
このプロパティは、ダッシュボードを編集するユーザー機能を無効にするために使用できます。

<img src="../../general/images/showing_hiding_elements_edit.png" alt="Editing a dashboard through the UI" class="responsive-img"/>

``` csharp
revealView.CanEdit = false;
```

## ShowEditDataSource
このプロパティを使用して、ダッシュボード データ ソースの編集を無効にすることができます。

<img src="../../general/images/showing-hiding-elements-edit-datasource.png" alt="Editing a dashboard datasource through the UI" class="responsive-img"/>

``` csharp
revealView.ShowEditDataSource = false;
```

## ShowExportImage
このプロパティを使用して、ダッシュボードの画像へのエクスポートを無効にすることができます。

<img src="../../general/images/showing-hiding-elements-show-export-image.png" alt="Exporting a dashboard to Image" class="responsive-img"/>

``` csharp
revealView.ShowExportImage = false;
```

## ShowExportToPowerpoint
このプロパティを使用して、ダッシュボードの PowerPoint へのエクスポートを無効にすることができます。

<img src="../../general/images/showing-hiding-elements-show-export-powerpoint.png" alt="Exporting a dashboard to PowerPoint" class="responsive-img"/>

``` csharp
revealView.ShowExportToPowerpoint = false;
```

## ShowExportToPDF
このプロパティを使用して、ダッシュボードの PDF へのエクスポートを無効にすることができます。

<img src="../../general/images/showing-hiding-elements-show-export-pdf.png" alt="Exporting a dashboard to PDF" class="responsive-img"/>

``` csharp
revealView.ShowExportToPDF = false;
```

## ShowExportToExcel
このプロパティを使用して、ダッシュボードの Excel へのエクスポートを無効にすることができます。

<img src="../../general/images/showing-hiding-elements-show-export-excel.png" alt="Exporting a dashboard to Excel" class="responsive-img"/>

``` csharp
revealView.ShowExportToExcel = false;
```

## CanCopyVisualization
このプロパティは、表示形式をコピーし、後で現在のダッシュボードまたは別のダッシュボードに貼り付ける機能を無効にするために使用できます。

<img src="../../general/images/showing_hiding_elements_copy.png" alt="Copying an existing visualization through the UI" class="responsive-img"/>

``` csharp
revealView.CanCopyVisualization = false;
```

## CanDuplicateVisualization
このプロパティは、現在のダッシュボードで表示形式を複製する機能を無効にするために使用できます。

<img src="../../general/images/showing_hiding_elements_duplicate.png" alt="Duplicating an existing visualization through the UI" class="responsive-img"/>

``` csharp
revealView.CanDuplicateVisualization = false;
```

## CanAddPostCalculatedFields
このプロパティを使用して、現在のダッシュボードに新しい事後計算フィールドを追加する機能を無効にできます。

<img src="../../general/images/showing_hiding_elements_post_calculated.png" alt="Accessing post-calculated fields through the UI" class="responsive-img"/>

事後計算フィールドはデータセットの新しいフィールドで、すでに集計された値に数式を適用して作成されます。
詳細については、[Reveal ヘルプ](https://help.revealbi.io/jp/data-visualizations/fields/calculated-fields/overview.html)をご覧ください。

``` csharp
revealView.CanAddPostCalculatedFields = false;
```

## CanAddCalculatedFields
このプロパティを使用して、現在のダッシュボードに新しい事前計算フィールドを追加する機能を無効にできます。

<img src="../../general/images/showing_hiding_elements_pre_calculated.png" alt="Accessing pre-calculated fields through the UI" class="responsive-img"/>

事前計算フィールドはデータセットの新しいフィールドで、データ エディター集計を実行する前に評価されます。
詳細については、[Reveal ヘルプ](https://help.revealbi.io/jp/data-visualizations/fields/calculated-fields/overview.html)をご覧ください。

``` csharp
revealView.CanAddCalculatedFields = false;
```

## ShowFilters
このプロパティは、ユーザーにダッシュボード フィルター UI を表示または非表示にするために使用できます。

<img src="../../general/images/showing_hiding_elements_filters.png" alt="Showing Dashboard Filters in the UI" class="responsive-img"/>

ダッシュボード フィルターを使用すると、ダッシュボードの全ての表示形式のコンテンツを一度にフィルター適用できます。

``` csharp
revealView.ShowFilters = false;
```

## CanAddDashboardFilter
このプロパティを使用して、[ダッシュボード フィルターの追加] メニュー項目を表示または非表示にすることができます。

<img src="../../general/images/showing-hiding-elements-can-add-dashboard-filter.png" alt="Showing Add Dashboard Filter in the UI" class="responsive-img"/>

``` csharp
revealView.CanAddDashboardFilter = false;
```

## CanAddDateFilter
このプロパティを使用して、[日付フィルターの追加] メニュー項目を表示または非表示にすることができます。

<img src="../../general/images/showing-hiding-elements-can-add-date-filter.png" alt="Showing Add Date Filter in the UI" class="responsive-img"/>

``` csharp
revealView.CanAddDateFilter = false;
```

## 選択済みフィルター
ダッシュボードを読み込みする時に既存のダッシュボード フィルターから最初に選択される値を指定できます。

<img src="../../general/images/showing_hiding_elements_filters_preselected.png" alt="Showing a Dashboard Filter preselected in the UI" class="responsive-img"/>

次のコードスニペットは、ダッシュボードを読み込む方法を示し、選択された「Territory」値を「Americas」に設定します。したがって、ダッシュボードには「Americas」でフィルタリングされたデータが表示されます。

``` csharp
var dashboard = new RVDashboard(path);
dashboard.filters.GetByTitle("Territory").selectedValues = new List<object>() { "Americas" };
revealView.Dashboard = dashboard;
```

## AvailableChartTypes
このプロパティは、ユーザーが使用できる表示形式タイプをフィルターするために使用できます。

<img src="../../general/images/showing_hiding_elements_charts.png" alt="Switching visualizations through the UI" class="responsive-img"/>

たとえば、以下のように表示形式を追加または削除できます。

``` csharp
revealView.AvailableChartTypes.Add(RVChartType.BulletGraph);
revealView.AvailableChartTypes.Remove(RVChartType.Choropleth);
```

さらに、使用可能な表示形式のみを含む新しいリストを作成できます。

``` csharp
revealView.AvailableChartTypes = new List<RVChartType>() { RVChartType.BulletGraph, RVChartType.Choropleth };
```

## CanChangeVisualizationBackgroundColor
エンドユーザーが表示形式エディター ([設定] タブの下) で特定の表示形式の背景色を変更できるかどうかを示すフラグ。有効にすると、RevealTheme で BackgroundColors として指定された色のリストが推奨パレットとして表示されます。ユーザーは、詳細モードを使用して任意の色を選択することもできます。

このプロパティのデフォルト値は false です。したがって、エンドユーザーが視覚化の背景を指定できるようにするには、それを true に設定する必要があります。

``` csharp
revealView.CanChangeVisualizationBackgroundColor = true;
```

視覚化の背景色は、RevealView.SetVisualizationBackgroundColor(RVVisualization, Color) を呼び出すことによってプログラムで制御することもできます。