# Replacing an Excel File DataSource

Sometimes dashboards are created using Excel files stored in the cloud as a data source for its visualizations.

When embedding the Reveal SDK in your application, you can replace these cloud-based files with files stored in a local directory located on the server at runtime.

**Step 1** - In the ASP.NET Web API server application, create a class that implements `IRVDataSourceProvider`. This class will perform the actual replacement of the Excel files.

```cs
public class MyDataSourceProvider : IRVDataSourceProvider
{
    public Task<RVDataSourceItem> ChangeDataSourceItemAsync(IRVUserContext userContext, string dashboardId, RVDataSourceItem dataSourceItem)
    {
        throw new NotImplementedException();
    }
}
```

The `ChangeDataSourceItemAsync` method of this class returns the `RVDataSourceItem` that the visualization will use to get its data. By modifying the `RVDataSourceItem` item that is provided as an argument in the `ChangeDataSourceItemAsync` method, you can change which Excel file get your data from.

**Step 2** - Update the `AddReveal` method in the `Program.cs` file to add the `IRVDataSourceProvider` you just created to the `RevealSetupBuilder` using the `RevealSetupBuilder.AddDataSourceProvider` method.

```cs
builder.Services.AddControllers().AddReveal( builder =>
{
    builder.AddDataSourceProvider<MyDataSourceProvider>();
});
```

## Example: Replacing an Excel File Data Source

In this example, we are replacing a data source item that is using a cloud-based Excel file named "Sales Cloud Excel File" with a local Excel file named "SalesLocalExcelFile.xlsx".

First, we check the incoming `RVDataSourceItem` to see if it is a `RVExcelDataSourceItem`. If it is, then we get the existing `RVDataSourceItem.ResourceItem` and check its `Title` property. If the title is "Sales Cloud Excel File" then we will create a new `RVLocalFileDataSourceItem` and set the `Uri` to the location of the new local Excel file. After we set the title of the local Excel file data source item, we replace the `RVExcelDataSourceItem.ResourceItem` with our newly created `RVLocalFileDataSourceItem`.

```cs
public class MyDataSourceProvider : IRVDataSourceProvider
{
    public Task<RVDataSourceItem> ChangeDataSourceItemAsync(IRVUserContext userContext, string dashboardId, RVDataSourceItem dataSourceItem)
    {
        if (dataSourceItem is RVExcelDataSourceItem excelDataSourceItem)
        {
            var resourceItem = excelDataSourceItem.ResourceItem as RVDataSourceItem;
            if (resourceItem.Title == "Sales Cloud Excel File")
            {
                var localItem = new RVLocalFileDataSourceItem();
                localItem.Uri = "local:/SalesLocalExcelFile.xlsx";
                localItem.Title = resourceItem.Title;

                excelDataSourceItem.ResourceItem = localItem;
            }
        }

        return Task.FromResult(dataSourceItem);
    }
}
```
