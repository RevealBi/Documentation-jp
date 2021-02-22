## ダッシュボード ファイルの読み込み

### 概要とコード

If you want to display a dashboard, you can choose between loading a __rdash__ file or loading a __json__ file. In both cases the _Build Action_ property of the file has to be set to _Embedded resource_ in Visual Studio.

When you load the dashboard from a __rdash__ file, you have to pass it as stream or path to the _RVDashboard_ constructor.
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
When you load a __json__ file, you need to pass the file content as a _string_ parameter to the _RVDashboard.LoadFromJsonAsync_ static method.   
The code snippet below shows how to load a json file from a relative path (..\\..\\Sales.json):
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
        var path = @"..\..\Sales.json";
        var revealView = new RevealView();

        // reading the json file contents
        string jsonContent = File.ReadAllText(path);
        RVDashboard dashboard = await RVDashboard.LoadFromJsonAsync(jsonContent);
        revealView.Dashboard = dashboard;

        Grid grid = this.Content as Grid;
        grid.Children.Add(revealView);
    }
}
```
> [!NOTE]
> この例では、Loaded イベントでコンポーネントを初期化し、ウィンドウ コンテンツが Grid コンポーネントであると仮定しました。コードをアプリケーションに統合する場合、変更を加える必要がある場合があります。
