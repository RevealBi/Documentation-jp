## ダッシュボード ファイルの読み込み

### 概要とコード

ダッシュボードを表示する場合は、__rdash__ ファイルを読み込むか __json__ ファイルを読み込むかを選択できます。どちらの場合も、ファイルの _BuildAction_ プロパティを Visual Studio で埋め込みリソースに設定する必要があります。

__rdash__ ファイルからダッシュボードを読み込むときは、ストリームまたはパスとして _RVDashboard_ コンストラクターに渡す必要があります。
以下のコード スニペットは、相対パス (..\\..\\Sales.rdash) から rdash ファイルを読み込む方法を示しています:

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
__json__ ファイルを読み込むときは、ファイルの内容を文字列パラメーターとして _RVDashboard.LoadFromJsonAsync_ 静的メソッドに渡す必要があります。   
以下のコード スニペットは、相対パス (..\\..\\Sales.json) から json ファイルを読み込む方法を示しています:
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
