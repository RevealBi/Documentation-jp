# リリース ノート

## 1.2.0 (8 月 2022 年)
### 新機能

- **カスタム メニュー項目のサポートを追加しました。**
以下のスニペットは、カスタムの「マイ メニュー項目」の作成を示しています。

```csharp
revealView.MenuOpening += RevealView_MenuOpening;
private void RevealView_MenuOpening(RVVisualization visualization, MenuOpeningEventArgs args)
{
	if (args.IsInEditMode && visualization == null) //dashboard edit mode
	{
		args.MenuItems.Add(new RVMenuItem()
		{
			Icon = new RVImage(new BitmapImage(new Uri("pack://application:,,,/Images/save-24.png"))),
			Title = "My Menu Item",
			Action = () =>
			{
				MyCustomAction();
			}
		});
	}
}
```

- **ダッシュボードのカスタムの空の状態の画像のサポートを追加しました。**
新規ダッシュボードの作成時に、表示されるプレースホルダー画像を変更する機能を追加しました。	

```csharp
revealView.Assets.DashboardEmptyState = new RVImageAsset()
{
  Image = new RVImage(new BitmapImage(new Uri("pack://application:,,,/Images/dashboard_empty.png"))),
  Title = "Add your First Visualization",
  Subtitle = "Visualize all your data in perfect harmony"
};	
```

- **デフォルトの表示形式を変更する方法を追加しました。**
以下のスニペットでは、既定の表示形式をピボット グリッドに変更します。
```csharp
revealView.DefaultChartType = RVChartType.PivotGrid;
```

- **RVInMemoryDataSourceItem にパラメーターのサポートを追加しました。**
パラメーターをインメモリ データ ソースの項目に設定して、追加情報を渡すことができるようになりました。
```csharp
public Task<RVDataSourceItem> ChangeDataSourceItemAsync(RVDataSourceItem dataSourceItem)
{
    if (dataSourceItem is RVInMemoryDataSourceItem item)
    {
        item.Parameters = new Dictionary<string, object>()
        {
            { "CurrentUser", GetCurrentUserName() }
        };
        return Task.FromResult<RVDataSourceItem>(item);
    }
    return Task.FromResult<RVDataSourceItem>(null);
}
```

- **スキーマ属性を SQL Server データ ソースに追加しました。**
データ ソースのスキーマ プロパティにより、SDK ユーザーは表示されるリスト テーブル/ビュー/プロシージャを提供されたスキーマに制限できます。
```csharp
var msSqlAdventureDS = new RVSqlServerDataSource()
{
	Id = "msSqlAdventureId",
	Title = "SQLServer Adventure DS",
	Host = "server.domain",
	Database = "AdventureWorks",
	Schema = "HumanResources",
	Port = 1433
};
datasources.Add(msSqlAdventureDS);
```

- **チャート の表示形式の凡例で使用されるカテゴリ グループ区切り記号を変更する方法を追加しました。**
以下のスニペットでは、セパレーターをデフォルト値 (スラッシュ) からハイフンに変更しています。
```csharp
revealView.CategoryGroupingSeparator = "-";
```

- **SQL Server データ ソースの TrustServerCertificate 設定のサポートを追加しました。**
この機能を RVSqlServerDataSource に実装するために、2 つの新しいブール プロパティを追加しました。
	- Encrypt
	- TrustServerCertificate
	
どちらも、接続文字列でまったく同じ名前のフラグを設定するために使用されます。		
```csharp
var msSqlAdventureDS = new RVSqlServerDataSource()
{
	Id = "msSqlAdventureId",
	Title = "SQLServer Adventure DS",
	Host = "server.domain",
	Database = "AdventureWorks",
	Schema = "HumanResources",
	Port = 1433,
	Encrypt = true,
	TrustServerCertificate = true
};
datasources.Add(msSqlAdventureDS);
```


### バグ修正
- Postgres/Redshift でデータ ソースを結合するときの ApplyTimeZone エラーを修正しました。
- ダッシュボードが更新されたときにダッシュボード フィルターが更新されない問題を修正しました。
- ツールチップのリンク名の数値形式を修正しました。
- Postgres/Redshift で会計年度が機能しない問題を修正しました。
- currentTimeZone のキャッシュの問題を修正しました。
- Google ドライブのポップアップにGoogle スプレッドシートが表示されない問題を修正しました。
すべての適格なデータ ソース (スプレッドシート、Excel、CSV、および JSON) がコネクタ内で正しく表示されるよう修正しました。			
- 時系列チャートにおいて、負の値に対し最小値が適切に設定されない問題を修正しました。
時系列チャートの Y 軸の最小値と最大値が、自動的に調整されるよう修正しました。		
