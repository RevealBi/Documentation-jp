# 可視化の最大化
ユーザーにダッシュボードを表示するときに、最大化された視覚化を 1 つだけ表示したい場合があります。さらに、最初の可視化をロックして、ユーザーがダッシュボード全体にアクセスできないようにすることもできます。Desktop SDK を使用して両方のシナリオを実現できます。

<img src="images/maximize-three_divisions_dashboard_maximized.png" alt="Displaying a dashboard with a maximized visualization" width="100%"/>

#### サンプル詳細

可視化した 3 つのダッシュボードがあり、それぞれの可視化に会社の異なる部門のデータが表示されているとします。

<img src="images/maximize-three_divisions_dashboard.png" alt="Displaying a dashboard with three visualizations" width="100%"/>

この例では、業務アプリケーションでこれらの可視化を使用します。各部門のホーム ページに表示される情報の一部としてそれらを含める必要があります。

### 可視化の最大化

最大化された可視化でダッシュボードを開くには、revealView.Dashboard プロパティを割り当てた後、__RevealView__ の __MaximizedVisualization__ プロパティを使用する必要があります。この属性に可視化を設定しないと、ダッシュボード全体が表示されます。

[**RevealView オブジェクトの構成**](configuring-revealview.md)に示すように、ページに特定のダッシュボードを表示できます。以下のコード スニペットに示すように、今回は、__MaximizedVisualization__ 属性も設定する必要があります:

``` csharp
var revealView = new RevealView();
using (var fileStream = File.OpenRead(path))
{
    var dashboard = new RVDashboard(fileStream);
    revealView.Dashboard = dashboard;
    revealView.MaximizedVisualization = dashboard.Visualizations.GetByTitle("Sales");
}
```

最初に最大化された可視化は「Sales」というタイトルの可視化になりますが、それでもエンドユーザーはダッシュボードに戻って残りの可視化を表示できます。

### 単一可視化モード

また、最初の可視化をロックして、常に可視化を 1 つのみ表示するようにすることもできます。これにより、ダッシュボードは単一の視覚化ダッシュボードのように機能します。これが「単一可視化モード」の概念です。

「SingleVisualizationMode」をオンにするには、以下に示すように、__SingleVisualizationMode__ プロパティを true に設定します。

``` csharp
revealView.SingleVisualizationMode = true;
```

この 1 行を追加すると、ダッシュボードは単一の視覚化ダッシュボードとして機能します。
各部門のホーム ページでも同じことができます。__dashboard.Visualizations.GetByTitle()__ で可視化のタイトルを正しいタイトルに置き換えるだけです。

#### ロックされた可視化を動的に変更

ページを再読み込みせずに、表示されている単一の可視化を動的に変更することもできます。ユーザーの観点から見ると、アプリは部門のセレクターと最大化された視覚化を備えた単一ページのアプリケーションになります。ユーザーがリストから 1 つの部門を選択すると、最大化された視覚化が更新されます。

このシナリオは、以下に示すように、__RevealView__ のメソッドを使用するか __MaximizedVisualization__ プロパティを設定することで実現できます。

``` csharp
private void MaximizeVisualization(string title)
        {
            revealView.MaximizeVisualization(revealView.Dashboard.Visualizations.GetTitle(title));
            //or set the property
            revealView.MaximizedVisualization = revealView.Dashboard.Visualizations.GetTitle(title);
        }
```

最後に、カスタム コントロールを上記の方法で接続します。それにより、アプリケーションの選択が変わったときに視覚化が最大化されます。

注意事項:

  - ダッシュボードで可視化のリストを繰り返すことで、ボタンのリストを動的に生成できます。詳細については、__RVDashboard.Visualizations__ を参照してください。
  - SDK とともに配布されている *UpMedia* WPF アプリケーションに、**Manufacturing.xaml.cs** の実用的な例があります。このサンプルビューでは、画面下部にすべての可視化がトグル ボタンのリストとして表示されます。
