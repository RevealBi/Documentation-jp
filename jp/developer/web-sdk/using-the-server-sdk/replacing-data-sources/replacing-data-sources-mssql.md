# データ ソースの置き換え (MS SQL サーバー)

## 概要

ダッシュボードのデータを (Reveal Server SDK) ロードして処理する前に、ダッシュボードの各視覚化に使用される構成またはデータをオーバーライドできます。

インターフェイス __IRVDataSourceProvider__ を実装するクラスは、特定の可視化またはダッシュボード フィルターによって使用されるデータ ソースを置換または変更することができます。

## 使用事例

以下は、一般的なユース ケースです。

  - 使用するデータベースの名前は、現在のユーザーやアプリが取得する userId、division、company、customer などその他の属性に応じて変更できます。これにより、マルチテナント データベースからデータを取得する単一のダッシュボードを持つことができます。

  - 使用されているテーブルの名前、ロードするファイルのパスなどを変更することができます。ユース ケースは上記のものと似ています。

  - データ ソースをメモリ内のデータ ソースに置き換えることができます。Reveal App はインメモリ データ ソースをサポートしていないため、CSV ファイルを使用してダッシュボードを設計し、このコールバックを使用して CSV データ ソースをインメモリデータ ソースに置き換えることができます。このシナリオでは、データは実際にメモリからロードされます (またはカスタムデータローダを使用して)。インメモリ データ ソースの使用方法の詳細については、[**インメモリ データのサポート**](~/jp/developer/web-sdk/using-the-server-sdk/in-memory-data.md)をご覧ください。

## コード

次のコード スニペットは、データ ソース アイテムを置き換える方法の例を示しています。

``` csharp
public class SampleDataSourceProvider : IRVDataSourceProvider
{
        public Task<RVDataSourceItem> ChangeDataSourceItemAsync(
            IRVUserContext userContext, string dashboardId,
            RVDataSourceItem dataSourceItem)
        {
            var sqlServerDsi = dataSourceItem as RVSqlServerDataSourceItem;
            if (sqlServerDsi != null)
            {
                // Change SQL Server host and database
                var sqlServerDS = (RVSqlServerDataSource)sqlServerDsi.DataSource;
                sqlServerDS.Host = "10.0.0.20";
                sqlServerDS.Database = "Adventure Works";

                // Change SQL Server table/view
                sqlServerDsi.Table = "Employees";
                return Task.FromResult((RVDataSourceItem)sqlServerDsi);
            }

            return Task.FromResult(dataSourceItem);
        }
}
```

上記の例では、次の置換が実行されます:

  - MS SQL Server データベースを使用するすべてのデータ ソースは、ハードコードされたサーバー 10.0.0.20、Adventure Works データベース、および Employees テーブルを使用するように変更されます。

__IRVDataSourceProvider__ を実装することに加えて、ConfigureServices で IMvcBuilder に Reveal を追加するときに、実装を登録する必要があることに注意してください。
```csharp
services
    .AddMvc()
        .AddReveal(builder =>
        {
            builder
              ...
              .AddDataSourceProvider<MyDataSourceProvider>()
              ...
        });
```