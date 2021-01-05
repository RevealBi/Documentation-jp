## ダッシュボードの編集と保存

### 概要

ダッシュボードを読み込むには、ダッシュボード ファイルを含むストリームを __RevealView__ コンポーネントに提供する必要があります。その後、ユーザーがダッシュボードを変更した後に、変更されたダッシュボード ファイルを処理したい場合があります。

### ダッシュボードの編集

__RevealView__ の **Dashboard** プロパティ (タイプ RVDashboard) は、エンドユーザーがダッシュボードの編集を開始すると更新されます。たとえば、可視化またはフィルターを追加または削除すると、RVDashboard のコレクションが自動的に更新されます。

__RVDashboard__の **PropertyChanged** イベントに添付して、**HasPendingChanges** などのプロパティへの変更の通知を受け取ります:

**コード サンプル**:

``` csharp
dashboard.PropertyChanged += Dashboard_PropertyChanged;
```

次に、イベント ハンドラーを実装します:

``` csharp
private void Dashboard_PropertyChanged(object sender, System.ComponentModel.PropertyChangedEventArgs e)
{
    if (e.PropertyName == "HasPendingChanges")
    {
        Console.Out.WriteLine("HasPendingChanges: " + ((RVDashboard)sender).HasPendingChanges);
    }
}
```

ユーザーが可視化の編集を終了した後、可視化エディターを閉じると、Revealview の __VisualizationEditorClosed__ イベントが発生します。
次のコードを使用して、イベントに添付することができます:

``` csharp
revealView.VisualizationEditorClosed += RevealView_VisualizationEditorClosed;
```

次にイベント ハンドラーを実装します:

``` csharp
private void RevealView_VisualizationEditorClosed(object sender, VisualizationEditorClosedEventArgs e)
{
    if (e.IsCancelled)
    {
        Console.Out.WriteLine("Visualization editor cancelled " + (e.IsNewVisualization ? "creating a new visualization" : "editing " + e.Visualization.Title));
        return;
    }
    if (e.IsNewVisualization)
    {
        Console.Out.WriteLine("New visualization created: " + e.Visualization.Title);
    } else
    {
        Console.Out.WriteLine("Visualization modified: " + e.Visualization.Title);
    }
}
```

新しい可視化を追加する方法を制御する必要がある場合は、[**新しい可視化とダッシュボードの作成**](~/jp/developer/desktop-sdk/using-the-desktop-sdk/creating-visualizations-dashboards.md)を参照してください。

### ダッシュボードの保存

次のコードを使用して __SaveDashboard__ イベントにアタッチできます。

``` csharp
_revealView.SaveDashboard += RevealView_SaveDashboard;
```

次にイベント ハンドラーを実装します。

``` csharp
private async void RevealView_SaveDashboard(object sender, DashboardSaveEventArgs args)
{
    var data = await args.Serialize();
    using (var output = File.OpenWrite($"{args.Name}.rdash"))
    {
        output.Write(data, 0, data.Length);
    }
    args.SaveFinished();
}
```

上記の例は、Save イベントを処理するための単純化された実装を示しています。実際のシナリオでは、カスタム UI をユーザーに表示し、ユーザーがダッシュボードの場所と姓を選択できます。

ユーザーがダッシュボードの名前を変更した場合は、メソッド __SerializeWithNewName__ を使用して、ダッシュボードの Title 属性に正しく反映された名前を取得できます。

保存操作を処理したくない場合は、次の設定でダッシュボードを編集するオプションをオフにすることができます。

``` csharp
revealView.CanEdit = false;
```

この方法は、たとえば、ユーザーが変更を加えることを想定していない場合に便利です。
