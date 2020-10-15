## ダッシュボード ファイルの読み込み

### 概要とコード

In order to display a dashboard, you must supply its .rdash file as a stream or as a path on the local file system to the constructor of the RVDashboard class

以下のコードスニペットは、相対パス (..\\..\\Sales.rdash): から rdash ファイルを読み込む方法を示しています。

``` csharp
public partial class MainWindow : Window
{
    public MainWindow()
    {
        InitializeComponent();
        this.Loaded += MainWindow_Loaded;
    }

    private async void MainWindow_Loaded(object sender, RoutedEventArgs e)
    {
        var path = @"..\..\Sales.rdash";

        var revealView = new RevealView();

        // using a path within the file system
        RVDashboard dashboard = new RVDashboard(path);

        // using a stream to create an RVDashboard object
        using (var fileStream = File.OpenRead(path))
        {
            dashboard = new RVDashboard(fileStream);
        }

        revealView.Dashboard = dashboard;
        Grid grid = this.Content as Grid;
        grid.Children.Add(revealView);
    }
}
```

上記のように、ダッシュボードのコンテンツは非同期メソッド __RevealUtility.LoadDashboard__ を使用してロードされます。
同期メソッドを使用したい場合は、代わりに __RevealUtility.LoadDashboardSync__ を使用することもできます。

> [!NOTE]
> この例では、Loaded イベントでコンポーネントを初期化し、ウィンドウ コンテンツが Grid コンポーネントであると仮定しました。コードをアプリケーションに統合する場合、変更を加える必要がある場合があります。
