# データ制限

ダウンロードされたファイルのサイズ、結果セット内のセルの数 (集計後)、ピボット テーブルとグリッドのサイズ (セルの数として指定) に関して、Reveal Web を使用する場合のサーバー側のサイズ制限があります。
これらの制限の目的は、サーバーのリソース (メモリとディスク領域) が不足するのを防ぐことです。

デフォルトの制限値:

-	csv/json/excel をダウンロードする場合は 200mb
-	1000 万のセル
-	6400 万文字 (すべてのセルにすべての文字列を追加)

## デフォルト値を変更

### ソース 
[**InitializeParameterBuilder**](https://help.revealbi.io/api/java/latest/com/infragistics/reveal/engine/init/InitializeParameterBuilder.html).


| プロパティ  |   型| 説明  |  
|---|---|---|
|  setMaxInMemoryCells | Long  |  このプロパティを、セルの数として指定されたピボット テーブルまたはグリッドの予想される最大サイズに設定します。 |
|  setMaxStorageCells | Long  | このプロパティを、任意のデータ ソースから処理されるセルの予想される最大サイズに設定します。  |
|  setMaxStringCellSize | Integer  |  データセット列の文字列が持つことができる文字数の制限を設定します。 |
|  SsetMaxTotalStringsSize | Long  | このプロパティを、すべてのセルの文字の総数として指定された、ピボット テーブルまたはグリッドの予想される最大サイズに設定します。 |
