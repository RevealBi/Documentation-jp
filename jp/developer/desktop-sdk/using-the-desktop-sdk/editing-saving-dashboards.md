## ダッシュボードの編集と保存

### 概要

To load a dashboard, you need to provide the __RevealView__ component with the stream containing the dashboard file. Later, you might want to handle the modified dashboard file, once the user made changes to the dashboard.

### Editing dashboards

The **Dashboard** property (type RVDashboard) of __RevealView__ is updated when the end user starts editing the dashboard. For example, when adding or removing visualizations or filters, RVDashboard's collections get automatically updated.

Attach to the **PropertyChanged** event in __RVDashboard__, to get notified of changes to properties like **HasPendingChanges**:

*Code Sample*:

``` csharp
dashboard.PropertyChanged += Dashboard_PropertyChanged;
```

Then, implement the event handler:

``` csharp
private void Dashboard_PropertyChanged(object sender, System.ComponentModel.PropertyChangedEventArgs e)
{
    if (e.PropertyName == "HasPendingChanges")
    {
        Console.Out.WriteLine("HasPendingChanges: " + ((RVDashboard)sender).HasPendingChanges);
    }
}
```

After a user finishes editing a visualization, upon closing the Visualization Editor, the Revealview's __VisualizationEditorClosed__ event is fired.
You can attach to the event with this code:

``` csharp
revealView.VisualizationEditorClosed += RevealView_VisualizationEditorClosed;
```

And then you need to implement the event handler:

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

In the case that you need to control how to add new visualizations please refer to [**Creating New Visualizations and Dashboards**](~/en/developer/desktop-sdk/using-the-desktop-sdk/creating-visualizations-dashboards.md).

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
