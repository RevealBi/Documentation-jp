## 手順に従ってカスタム表示形式の作成

このセクションでは、カスタム表示形式機能を使用してデータの独自のビューを作成する方法を示します。

以下のタスクを示します:

-	HTML ファイルを作成し、必要なスクリプト参照を追加します。

-	Reveal (ホスト アプリケーション) に送信された表示データを処理し、イベントを通知するために JavaScript コードを追加します。

-	受信データを読み込み、そのカスタムな表示を作成します。

### HTML ファイルを作成する
jQuery と Revealbridgeutils への参照を含む空の html ファイルを作成します。

``` js
<html>
   <head>
      <script type="text/javascript" src="https://download.infragistics.com/reveal/custom-visualization/reveal_bridge_utils.js">
      </script>
      <script src="https://code.jquery.com/jquery-1.11.0.min.js"></script>
   </head>
   <body>
   </body>
</html>
```

-	最初の参照 (rplus_bridge_utils.js) は、Reveal が DOM を操作するのに役立ちます。

-	jquery-1.11.0.min.js は、表示形式をホストに接続します。

必要に応じて、[**reveal_bridge_utils.js ファイルをダウンロード**](https://download.infragistics.com/reveal/custom-visualization/reveal_bridge_utils.js)してローカルで参照することもできます。

### データを受信する準備ができていることをホストに通知する
2 番目のステップとして、次の目的で必要な javascript コードを追加します。

-	ビューがデータを受け取る準備ができたことをホストに通知します。これを行うには、RPBridgeUtils.notifyExtensionIsReady を呼び出します。

-	dataReady イベント ハンドラーを登録します。これは、データを消費する準備ができた後にホストによって呼び出されます。

このステップの後、コードは次のようになります:

``` js
<html>
   <head>
      <script type="text/javascript" src="reveal_bridge_utils.js"></script>
      <script src="https://code.jquery.com/jquery-1.11.0.min.js"></script>
      <script type="text/javascript">
         window.RPBridgeListener = {
         dataReady: function (tabularData) {
      // Render the view
         }
         };
      $(function () {
         RPBridgeUtils.notifyExtensionIsReady();
      });
      </script>
   </head>
   <body>
   </body>
</html>
```

### カスタム ビューを描画する HTML 要素を作成する
最後に dataReady 関数に送信したデータを処理して、データを描画するために使用する html タグを動的に生成します。

この場合、テーブル行を作成する tabularData.data 配列を反復し、HTML DOM の “myTable” div 内に追加します。

``` js
dataReady: function (tabularData) {
   var tableView = $("<table></table>");
      var headerRow = $("<tr></tr>").appendTo(tableView);
      for (var c = 0; c < tabularData.metadata.columns.length; c++) {
         var column = tabularData.metadata.columns[c];
         var headerCell = $("<th></th>").append(column.name + ":" +
         getColumnTypeName(column.type));
      headerRow.append(headerCell);
   }
   for (var i = 0; i < tabularData.data.length; i++) {
      var rowData = tabularData.data[i];
      var rowView = $("<tr></tr>");
      for (var j = 0; j < rowData.length; j++) {
         var cellValue = rowData[j];
         var cellView = $("<td></td>").append(cellValue);
         rowView.append(cellView);
      }
      tableView.append(rowView);
   }
   $("#myTable").append(tableView); }
   };
```

### 全サンプル コード

``` js
<html>
   <head>
      <script type="text/javascript" src="reveal_bridge_utils.js"></script>
      <script src="https://code.jquery.com/jquery-1.11.0.min.js"></script>
      <script type="text/javascript">
         var helpLink = "https://help.revealbi.io/en/data-visualizations/visualization-types/diy-visualizations.html";
         function getColumnTypeName(type) {
         	switch (type) {
         	case 0:
         		return "String";
         	case 1:
         		return "Number";
         	case 2:
         		return "Date";
         	case 3:
         		return "DateTime";
         	case 4:
         		return "Time"
         	default:
         		return "Unknown";
         	}
         }
         function openHelpLink() {
         	RPBridgeUtils.openUrl(helpLink);
         }
         window.RPBridgeListener = {
         dataReady: function (tabularData) {
         	var tableView = $("<table></table>");
         	var headerRow = $("<tr></tr>").appendTo(tableView);
         	for (var c = 0; c < tabularData.metadata.columns.length; c++) {
         		var column = tabularData.metadata.columns[c];
         		var headerCell = $("<th></th>").append(column.name + ":" + getColumnTypeName(column.type));
         		headerRow.append(headerCell);
         	}
         	for (var i = 0; i < tabularData.data.length; i++) {
         		var rowData = tabularData.data[i];
         		var rowView = $("<tr></tr>");
         		for (var j = 0; j < rowData.length; j++) {
         			var cellValue = rowData[j];
         			var cellView = $("<td></td>").append(cellValue);
         			rowView.append(cellView);
         		}
         		tableView.append(rowView);
         	}
         	$("#myTable").append(tableView);
         }
         };
         $(function () {
         RPBridgeUtils.notifyExtensionIsReady();
         });
      </script>
   </head>
   <body>
      <div>Follow <a href="#" onclick="openHelpLink();">this link</a> for this visualization's implementation.
      </div>
      <br />
      <div id="myTable" style="height:100%"></div>
   </body>
</html>
```
