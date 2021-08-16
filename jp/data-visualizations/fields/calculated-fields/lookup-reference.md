# Lookup & 参照計算フィールド


検索/行列フィールドは、現在のスプレッドシートとダッシュボードで動作し、セル、行、ダッシュボード変数へのテキスト参照を返します。

>[!NOTE] 
>以下の表のすべてのサンプルは **HR Dataset 2016** スプレッドシートで作成されました。

以下はこの関数に含まれる集計カテゴリです。

<style type="text/css">
.tg  {border-collapse:collapse;border-spacing:0;}
.tg td{font-family:Arial, sans-serif;font-size:14px;padding:10px 5px;border-style:solid;border-width:1px;overflow:hidden;word-break:normal;border-color:black;}
.tg th{font-family:Arial, sans-serif;font-size:14px;font-weight:normal;padding:10px 5px;border-style:solid;border-width:1px;overflow:hidden;word-break:normal;border-color:black;}
.tg .tg-cly1{text-align:left;vertical-align:middle}
.tg .tg-yla0{font-weight:bold;text-align:left;vertical-align:middle}
.gray-snippet-cstm{color: #666;background-color: #ddd;}
</style>
<table class="tg">
  <tr>
    <th class="tg-yla0">関数名</th>
    <th class="tg-cly1"><span style="font-weight:bold">構文とサンプル</span></th>
  </tr>
  <tr>
    <td class="tg-cly1" rowspan="2"><a href="#calc-fields-previous">previous</a>: <span class="gray-snippet-cstm">previous</span> は、<span class="gray-snippet-cstm">式</span>として選択したフィールドの値で結果を取得できます。</td>
    <td class="tg-cly1"><span style="font-weight:bold">構文</span>: <span class="gray-snippet-cstm">previous({expression},{first value})</span></td>
  </tr>
  <tr>
    <td class="tg-cly1"><span style="font-weight:bold">サンプル</span>:<span class="gray-snippet-cstm"> previous([Wage],1)</span></td>
  </tr>
  <tr>
    <td class="tg-cly1" rowspan="2"><span style="font-weight:bold">row</span>: <span class="gray-snippet-cstm">row</span> は、データ ソース内のすべての行の現在の行の番号を返します。</td>
    <td class="tg-cly1"><span style="font-weight:bold">構文</span>:<span class="gray-snippet-cstm"> row()</span></td>
  </tr>
  <tr>
    <td class="tg-cly1"><span style="font-weight:bold">サンプル</span>:<span class="gray-snippet-cstm"> row()</span></td>
  </tr>
</table>

<a name='calc-fields-previous'></a>
## Previous

previous の計算フィールドでは、`式`で選択したフィールドの値で結果を取得できます。引数を 2 つ設定します。

  - `式`:  データ ソースのフィールドの 1 つ。

  - `最初の値`: デフォルトで空の最初の行の値。

### サンプル

以下は、HR Dataset 2016.xlsx「Employees」シートを抽出したものです。

| EMPLOYEEID | FULLNAME          | DEPARTMENT  | OFFICE                    | WAGE     |
| ---------- | ----------------- | ----------- | ------------------------- | -------- |
| 1.00       | Joan Baez         | Development | Montevideo, Uruguay       | 36542.00 |
| 2.00       | Zurbuch Thompson  | Development | Cranbury, New Jersey, USA | 76865.00 |
| 3.00       | Zimmermann Miller | Development | Cranbury, New Jersey, USA | 73768.00 |
| 4.00       | Zurcher Reid      | Development | Sofia, Bulgaria           | 36018.00 |

以下の計算フィールドを追加します。

`previous([Wage],1)`

以下は計算フィールドの結果です。

| EMPLOYEEID | FULLNAME          | DEPARTMENT  | OFFICE                    | WAGE         | previous Field |
| ---------- | ----------------- | ----------- | ------------------------- | ------------ | -------------- |
| 1.00       | Joan Baez         | Development | Montevideo, Uruguay       | **36542.00** | **1.00**       |
| 2.00       | Zurbuch Thompson  | Development | Cranbury, New Jersey, USA | **76865.00** | **36542.00**   |
| 3.00       | Zimmermann Miller | Development | Cranbury, New Jersey, USA | **73768.00** | **76865.00**   |
| 4.00       | Zurcher Reid      | Development | Sofia, Bulgaria           | 36018.00     | **73768.00**   |

表に示すように、2 つ目の行は 2 つ目の行に `[WAGE]` 値を返します。関数で設定したとおり列の最初のセルを `1` で埋めます。
