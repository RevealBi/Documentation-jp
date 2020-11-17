## ダッシュボード ファイルの読み込み

### 概要とコード

ダッシュボードを表示するには、その .rdash ファイルをストリームとして、またはローカル ファイル システム上のパスとして RVDashboard クラスのコンストラクターに提供する必要があります。

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

        // ファイル システム内のパスを使用する
        RVDashboard dashboard = new RVDashboard(path);

        // ストリームを使用して RVDashboard オブジェクトを作成する
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

> [!NOTE]
> この例では、Loaded イベントでコンポーネントを初期化し、ウィンドウ コンテンツが Grid コンポーネントであると仮定しました。コードをアプリケーションに統合する場合、変更を加える必要がある場合があります。
