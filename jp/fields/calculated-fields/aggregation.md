## 集計計算フィールド


集計式は元のデータソースを操作してその値を分析し、多くの場合、再編成するか、単にそれに含まれる情報を要約する場合に便利です。異なる値 (`average` など) の計算や最大  `max` と `min` の検索に使用することも可能です。そのため、**すべての数式**は**数値フィールドのみで使用します**。

Reveal では、集計計算フィールドに以下が含まれます。

  - **標準関数**: 各情報は、[関数名] の下の対応するハイパーリンクをクリックします。

  - **if 文を含む標準関数**: [このセクション](#aggregation-if-condition) は、*if 文* [ネスト if 文 を含む](#nested-if-conditions)) の詳細および構成方法について説明します。

**Note:** *以下の表のすべてのサンプルは HR dashboard サンプルに含まれる [HR Dataset 2016](http://download.infragistics.com/reportplus/help/samples/HR%20Dataset_2016.xlsx)スプレッドシートで作成されました。*

以下はこの関数に含まれる集計カテゴリです。

<style type="text/css">
.tg  {border-collapse:collapse;border-spacing:0;}
.tg td{font-family:Arial, sans-serif;font-size:14px;padding:10px 5px;border-style:solid;border-width:1px;overflow:hidden;word-break:normal;border-color:black;}
.tg th{font-family:Arial, sans-serif;font-size:14px;font-weight:normal;padding:10px 5px;border-style:solid;border-width:1px;overflow:hidden;word-break:normal;border-color:black;}
.tg .tg-cly1{text-align:left;vertical-align:middle}
.tg .tg-0lax{text-align:left;vertical-align:top}
.gray-snippet-cstm{color: #666;background-color: #ddd;}
</style>
<table class="tg" style="undefined;table-layout: fixed">
  <tr>
    <th class="tg-cly1"><span style="font-weight:bold">関数名と説明</span></th>
    <th class="tg-cly1"><span style="font-weight:bold">関数の構文とサンプル</span></th>
  </tr>
  <tr>
    <td class="tg-cly1" rowspan="2"><span style="font-weight:bold">average</span>: <span class="gray-snippet-cstm">average</span> 集計は、選択した<span class="gray-snippet-cstm">式</span>のすべての行の平均値で計算される数値を返します。</td>
    <td class="tg-cly1"><span style="font-weight:bold">構文</span>: <span class="gray-snippet-cstm">average({expression})</span></td>
  </tr>
  <tr>
    <td class="tg-cly1"><span style="font-weight:bold">サンプル</span>: <span class="gray-snippet-cstm">average([Wage])</span></td>
  </tr>
  <tr>
    <td class="tg-cly1" rowspan="2"><span style="font-weight:bold">averageif</span>: <a href="#aggregation-if-condition">if-条件</a>のある正則関数を使用する場合、結果が条件内で定義される特定の条件を満たす必要があります。</td>
    <td class="tg-cly1"><span style="font-weight:bold">構文</span>: <span class="gray-snippet-cstm">averageif({expression},{if-condition})</span></td>
  </tr>
  <tr>
    <td class="tg-cly1"><span style="font-weight:bold">サンプル</span>: <span class="gray-snippet-cstm">averageif([Wage],[OfficeId]=1)</span></td>
  </tr>
  <tr>
    <td class="tg-cly1" rowspan="2"><span style="font-weight:bold">count</span>: <span class="gray-snippet-cstm">count</span> 集計は、データソースの行数である<span style="font-weight:bold">数値</span>を返します。その他の引数は必要ありません。</td>
    <td class="tg-cly1"><span style="font-weight:bold">構文</span>: <span class="gray-snippet-cstm">count()</span></td>
  </tr>
  <tr>
    <td class="tg-0lax"><span style="font-weight:bold">サンプル</span>: <span class="gray-snippet-cstm">count()</span></td>
  </tr>
  <tr>
    <td class="tg-0lax" rowspan="2"><span style="font-weight:bold">countif</span>: <a href="#aggregation-if-condition">if-条件</a>のある正則関数を使用する場合、結果が条件内で定義される特定の条件を満たす必要があります。</td>
    <td class="tg-0lax"><span style="font-weight:bold">構文</span>: <span class="gray-snippet-cstm"> <span class="gray-snippet-cstm">countif({if-condition})</span></td>
  </tr>
  <tr>
    <td class="tg-0lax"><span style="font-weight:bold">サンプル</span>: <span class="gray-snippet-cstm">countif([OfficeId]=1)</span></td>
  </tr>
  <tr>
    <td class="tg-0lax" rowspan="2"><span style="font-weight:bold">max</span>: <span class="gray-snippet-cstm">max</span> 集計は、選択した<span class="gray-snippet-cstm">式</span>の最大値となる<span style="font-weight:bold">数値</span>を返します。</td>
    <td class="tg-0lax"><span style="font-weight:bold">構文</span>: <span class="gray-snippet-cstm"> max({expression})</span></td>
  </tr>
  <tr>
    <td class="tg-0lax"><span style="font-weight:bold">サンプル</span>: <span class="gray-snippet-cstm"> max([Wage])</span></td>
  </tr>
  <tr>
    <td class="tg-0lax" rowspan="2"><span style="font-weight:bold">maxif</span>: <a href="#aggregation-if-condition">if-条件</a>のある正則関数を使用する場合、結果が条件内で定義される特定の条件を満たす必要があります。</td>
    <td class="tg-0lax"><span style="font-weight:bold">構文</span>: <span class="gray-snippet-cstm">maxif({expression},{if-condition})</span></td>
  </tr>
  <tr>
    <td class="tg-0lax"><span style="font-weight:bold">サンプル</span>: <span class="gray-snippet-cstm">maxif([Wage],[OfficeId]=1)</span></td>
  </tr>
  <tr>
    <td class="tg-0lax" rowspan="2"><span style="font-weight:bold">min</span>: <span class="gray-snippet-cstm">min</span> 集計は、選択した<span class="gray-snippet-cstm">式</span>の最小値となる<span style="font-weight:bold">数値</span>を返します。</td>
    <td class="tg-0lax"><span style="font-weight:bold">構文</span>: <span class="gray-snippet-cstm"> min({expression})</span></td>
  </tr>
  <tr>
    <td class="tg-0lax"><span style="font-weight:bold">サンプル</span>: <span class="gray-snippet-cstm"> min([Wage])</span></td>
  </tr>
  <tr>
    <td class="tg-0lax" rowspan="2"><span style="font-weight:bold">minif</span>: <a href="#aggregation-if-condition">if-条件</a>のある正則関数を使用する場合、結果が条件内で定義される特定の条件を満たす必要があります。</td>
    <td class="tg-0lax"><span style="font-weight:bold">構文</span>: <span class="gray-snippet-cstm"> minif({expression},{if-condition})</span></td>
  </tr>
  <tr>
    <td class="tg-0lax"><span style="font-weight:bold">サンプル</span>: <span class="gray-snippet-cstm"> minif([Wage],[OfficeId]=1)</span></td>
  </tr>
  <tr>
    <td class="tg-0lax" rowspan="2"><span style="font-weight:bold">sum</span>: <span class="gray-snippet-cstm">sum</span> 集計は、選択した<span class="gray-snippet-cstm">式</span>のすべての行の合計として算出された<span style="font-weight:bold">数値</span>を返します。</td>
    <td class="tg-0lax"><span style="font-weight:bold">構文</span>: <span class="gray-snippet-cstm"> sum({expression})</span></td>
  </tr>
  <tr>
    <td class="tg-0lax"><span style="font-weight:bold">サンプル</span>: <span class="gray-snippet-cstm"> sum([Wage])</span></td>
  </tr>
  <tr>
    <td class="tg-0lax" rowspan="2"><span style="font-weight:bold">sumif</span>: <a href="#aggregation-if-condition">if-条件</a>のある正則関数を使用する場合、結果が条件内で定義される特定の条件を満たす必要があります。</td>
    <td class="tg-0lax"><span style="font-weight:bold">構文</span>: <span class="gray-snippet-cstm"> sumif({expression},{if-condition})</span></td>
  </tr>
  <tr>
    <td class="tg-0lax"><span style="font-weight:bold">サンプル</span>: <span class="gray-snippet-cstm"> sumif([Wage],[OfficeId]=1)</span></td>
  </tr>
</table>


<a name='aggregation-if-condition'></a>
### if 文のある計算フィールド

`If 条件` のある正則関数 (`式`が必要) を使用する場合、結果が条件内で定義される特定の条件を満たす必要があります。

#### 構文

デフォルトでは、「IF」サフィックスのある関数を選択した際に以下の構成が表示されます。

`XXXXXXIF({expression},{if-condition})`

2 つの引数を定義する必要があります。

  - `式:`: データソースのフィールドの 1 つを選択します。

  - `if-条件`: if 条件は論理テストの実行が必要です。`if-条件`の`論理テスト`は、集計を計算するための式に必要な条件です。

#### 基本サンプル

たとえば、上記の表の例です。

`averageif([Wage],[OfficeId]=1)`

より明確にするために関数を上記で定義した用語に基づいて区別します。

| 関数名  | 式 | IF 条件  |
| -------------- | ---------- | ------------- |
| averageif (…​)  | [Wage]     | [OfficeId]=1) |

以下は数値以外の場合の例です。

`sumif([Wage],[Department]="Development")`

説明:

| 関数名 | 式 | IF 条件               |
| ------------- | ---------- | -------------------------- |
| sumif (…​)    | [Wage]      | [Department]="Development" |

<a name='nested-if-conditions'></a>
#### ネスト IF 文のサンプル

論理演算子 (AND, OR) を前に使用してネスト IF 文を使用できます。

以下は if 文が 2 つある例ですが、if 文を使用する際の上限はありません。

`maxif([Wage], and([OfficeId]=1, [Department]="Development"))`

説明:

| 関数名 | 式 | 論理演算子 |
| ------------- | ---------- | ---------------- |
| maxif (…​)     | [Wage]     | and              |

`if 文`のステートメント:

| 最初の論理テスト | true の場合の値 | false の場合の値 |
| ------------------ | ------------- | -------------- |
| [OfficeId]=1       | 1             | 0              |

| 2 番目の論理テスト        | true の場合の値 | false の場合の値 |
| -------------------------- | ------------- | -------------- |
| [Department]="Development" | 1             | 0              |

論理演算子が `and` であるため、実行する `maxif` 集計の両方の条件が true である必要があります。
