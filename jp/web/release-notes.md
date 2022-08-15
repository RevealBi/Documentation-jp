# リリース ノート

## 1.2.0 (8 月 2022 年)
### 新機能
- **メイン Javascript ファイルのサイズを縮小しました。**
  メインの Javascript ファイルが最適化され、サイズが 30% 縮小されました。

- **カスタム メニュー項目のサポートを追加しました。**
以下のスニペットは、カスタムの「マイ メニュー項目」の作成を示しています。
```javascript
revealView.onMenuOpening = function(visualization, args) {
	if (args.isInEditMode && visualization == null) { //dashboard edit mode
		args.menuItems.push(new RevealApi.RVMenuItem(
			"My Menu Item",
			new RevealApi.RVImage("/images/save-24.png", "My Save"),
			function() {
				alert('my action');
			}
		));
	}
};
```

- **ダッシュボードのカスタムの空の状態の画像のサポートを追加しました。**
新規ダッシュボードの作成時に、表示されるプレースホルダー画像を変更する機能を追加しました。	
```javascript
revealView.assets.dashboardEmptyState = new RevealApi.RVImageAsset(
    new RevealApi.RVImage("/images/dashboard_empty.png", "Empty Dashboard State Image"), 
    "Add your First Visualization", 
    "Visualize all your data in perfect harmony");	
```

- **デフォルトの表示形式を変更する方法を追加しました。**
以下のスニペットでは、既定の表示形式をピボット グリッドに変更します。
```javascript
revealView.defaultChartType = RevealApi.RVChartType.PivotGrid;	
```

- **スキーマ属性を SQL Server データ ソースに追加しました。**
データ ソースのスキーマ プロパティにより、SDK ユーザーは表示されるリスト テーブル/ビュー/プロシージャを提供されたスキーマに制限できます。
```javascript
var msSqlAdventureDS = new RevealApi.RVSqlServerDataSource();
msSqlAdventureDS.host = "server.domain";
msSqlAdventureDS.host = "msSqlAdventureId";
msSqlAdventureDS.database = "AdventureWorks";
msSqlAdventureDS.port = 1433;
msSqlAdventureDS.title = "SQLServer Adventure DS";
msSqlAdventureDS.schema = "HumanResources";
```

- **チャート の表示形式の凡例で使用されるカテゴリ グループ区切り記号を変更する方法を追加しました。**
以下のスニペットでは、セパレーターをデフォルトのセパレーター (スラッシュ) からハイフンに変更しています。
```javascript
revealView.categoryGroupingSeparator = "-";
```

- **SQL Server データ ソースの TrustServerCertificate 設定のサポートを追加しました。**
この機能を RVSqlServerDataSource に実装するために、2 つの新しいブール プロパティを追加しました。
	- Encrypt
	- TrustServerCertificate

どちらも、接続文字列でまったく同じ名前のフラグを設定するために使用されます。		
```javascript
var msSqlAdventureDS = new RevealApi.RVSqlServerDataSource();
msSqlAdventureDS.host = "server.domain";
msSqlAdventureDS.id = "msSqlAdventureId";
msSqlAdventureDS.database = "AdventureWorks";
msSqlAdventureDS.port = 1433;
msSqlAdventureDS.title = "SQLServer Adventure DS";
msSqlAdventureDS.schema = "HumanResources";
msSqlAdventureDS.encrypt = true;
msSqlAdventureDS.trustServerCertificate = true;
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
