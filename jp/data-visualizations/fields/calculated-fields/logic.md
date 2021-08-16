# 論理計算フィールド


論理計算フィールドは、データ ソースの 2 つ以上の値の比較に使用できます。値を送信した論理テストに基づいて常に 0 または 1 を返します。

Reveal では、論理計算フィールドは次のとおりです。

  - **引数のない関数**: それぞれ 1 と 0 を返す `true()` および `false()`。

  - **論理テストのある複素関数**: 各関数の詳細な情報は、以下の表にあるリンクをクリックしてください。

**注:** *以下の表のすべてのサンプルは [HR Dataset 2016](https://download.infragistics.com/reportplus/help/samples/HR%20Dataset_2016.xlsx) スプレッドシートで作成されました。*

以下は論理カテゴリに含まれる関数です。
<style type="text/css">
.tg  {border-collapse:collapse;border-spacing:0;}
.tg td{font-family:Arial, sans-serif;font-size:14px;padding:10px 5px;border-style:solid;border-width:1px;overflow:hidden;word-break:normal;border-color:black;}
.tg th{font-family:Arial, sans-serif;font-size:14px;font-weight:normal;padding:10px 5px;border-style:solid;border-width:1px;overflow:hidden;word-break:normal;border-color:black;}
.tg .tg-cly1{text-align:left;vertical-align:middle}
.tg .tg-0lax{text-align:left;vertical-align:top}
.gray-snippet-cstm{color: #666;background-color: #ddd;}
</style>
<table class="tg">
  <tr>
    <th class="tg-cly1"><span style="font-weight:bold">関数名</span></th>
    <th class="tg-cly1"><span style="font-weight:bold">構文とサンプル</span></th>
  </tr>
  <tr>
    <td class="tg-cly1" rowspan="2"><a href="https://https://help.revealbi.io/jp/logic.html#calc-fields-and-or">and</a>: <span class="gray-snippet-cstm">and</span> は 2 つの論理テストを実行します。<span style="font-weight:bold">論理テストは true の場合、1 を返します。1 つまた 2 つは false の場合、0 を返します。</span></td>
    <td class="tg-cly1"><span style="font-weight:bold">構文</span>:  <span class="gray-snippet-cstm">and({logical1},{logical2})</span></td>
  </tr>
  <tr>
    <td class="tg-cly1"><span style="font-weight:bold">サンプル</span>:  <span class="gray-snippet-cstm">and([BirthDate]&gt;date(1983, 07, 15, 04, 06, 55),[Department]="CPA")</span></td>
  </tr>
  <tr>
    <td class="tg-cly1" rowspan="2"><a href="https://https://help.revealbi.io/jp/logic.html#true-false"><span style="font-weight:bold">false</span></a>: <span class="gray-snippet-cstm">false</span> は論理値 の <span style="font-weight:bold">false</span> である 0 を返します。</td>
    <td class="tg-cly1"><span style="font-weight:bold">構文</span>:  <span class="gray-snippet-cstm">false()</span></td>
  </tr>
  <tr>
    <td class="tg-cly1"><span style="font-weight:bold">サンプル</span>:  <span class="gray-snippet-cstm">false()</span></td>
  </tr>
  <tr>
    <td class="tg-0lax" rowspan="2"><a href="https://https://help.revealbi.io/jp/logic.html#calc-fields-if"><span style="font-weight:bold">if</span></a>: <span class="gray-snippet-cstm">if</span> は論理テストを実行します。<span style="font-weight:bold">論理テストは true の場合、1 を返します。</span> <span style="font-weight:bold">論理テストは false の場合、0 を返します。</span></td>
    <td class="tg-0lax"><span style="font-weight:bold">構文</span>:  <span class="gray-snippet-cstm">if({logical test},{value if true},{value if false})</span></td>
  </tr>
  <tr>
    <td class="tg-0lax"><span style="font-weight:bold">サンプル</span>:  <span class="gray-snippet-cstm">if([BirthDate]&lt;(1971,04,15,4,06,55),1,0)</span></td>
  </tr>
  <tr>
    <td class="tg-0lax" rowspan="2"><a href="https://https://help.revealbi.io/jp/logic.html#calc-fields-not">not</a>: <span class="gray-snippet-cstm">not</span> は論理テストを実行します。<span style="font-weight:bold">論理テストは false の場合、1 を返します。論理テストは true の場合、0 を返します。</span></td>
    <td class="tg-0lax"><span style="font-weight:bold">構文</span>:  <span class="gray-snippet-cstm">not({logical})</span></td>
  </tr>
  <tr>
    <td class="tg-0lax"><span style="font-weight:bold">サンプル</span>:  <span class="gray-snippet-cstm">not([OfficeId]&gt;=3)</span></td>
  </tr>
  <tr>
    <td class="tg-0lax" rowspan="2"><a href="https://https://help.revealbi.io/jp/logic.html#calc-fields-and-or"><span style="font-weight:bold">or</span></a>: <span class="gray-snippet-cstm">or</span> は 2 つの論理テストを実行します (if ステートメント)。<span style="font-weight:bold">論理テスト の 1 つのいずれか true の場合、1 を返します。両方が false の場合、0 を返します。</span></td>
    <td class="tg-0lax"><span style="font-weight:bold">構文</span>:  <span class="gray-snippet-cstm">or({logical1},{logical2})</span></td>
  </tr>
  <tr>
    <td class="tg-0lax"><span style="font-weight:bold">サンプル</span>:  <span class="gray-snippet-cstm">or(if([Office]="London,UK",1,0),if([BirthDate]&lt;date(1992,09,15,4,06,55),1,0))</span></td>
  </tr>
  <tr>
    <td class="tg-0lax" rowspan="2"><a href="https://https://help.revealbi.io/jp/logic.html#true-false">true</a>: <span class="gray-snippet-cstm">true</span> は論理値 の <span style="font-weight:bold">true</span> である 1 を返します。</td>
    <td class="tg-0lax"><span style="font-weight:bold">構文</span>:  <span class="gray-snippet-cstm">true()</span></td>
  </tr>
  <tr>
    <td class="tg-0lax"><span style="font-weight:bold">サンプル</span>:  <span class="gray-snippet-cstm">true()</span></td>
  </tr>
</table>


<a name='calc-fields-if'></a>
## If

If 関数で論理テストで定義した特定の条件を満たす結果を見つけることができます。3 つの引数で構文されます。

  - `論理テスト`: 平均を計算するための式に必要な条件。

  - `value if true` 論理テストが true の場合に関数がアウトプットする値。

  - `value if false`: 論理テストが false の場合に関数がアウトプットする値。

### 基本サンプル

たとえば、上記の表の例です。

`if([BirthDate]<date(1971,04,15,4,06,55),1,0)`

より明確にするために関数を上記で定義した用語に基づいて区別します。

| 関数名 | 論理テスト                           | true の場合の値 | false の場合の値 |
| ------------- | -------------------------------------- | ------------- | -------------- |
| **if** (…​)   | `[BirthDate]<date(1971,04,15,4,06,55)` | `1`           | `0`            |

論理テストでデータ ソースの`式`と論理テストを組み合わせます。

| 式    | 演算子 | 条件の引数          |
| ------------- | -------- | -------------------------- |
| `[BirthDate]` | `<`      | `date(1971,04,15,4,06,55)` |

date 引数は [date](date.html#date-date)で説明された構文に従います。

| 関数名 | 年   | 月 | 日  | 時 | 分 | 秒 |
| ------------- | ------ | ----- | ---- | ---- | ------ | ------ |
| `date(…​)`    | `1971` | `04`  | `15` | `4`  | `06`   | `55`   |

以下は数値以外の例です。

`if([Department]="Development",1,0)`

説明:

| 関数名 | 論理テスト                 | true の場合の値 | false の場合の値 |
| ------------- | ---------------------------- | ------------- | -------------- |
| **if** (…​)   | `[Department]="Development"` | `1`           | `0`            |

### ネスト IF 文のサンプル

論理演算子 (`and`、`or`) の後ろに続けてネスト IF 文を使用できます。

以下は if 文が 2 つある例ですが、if 文を使用する際の上限はありません。

`maxif([Wage], and([OfficeId]=1, [Department]="Development"))`

説明:

| 関数名 | 式 | 管理演算子 |
| ------------- | ---------- | ---------------- |
| maxif (…​)    | [Wage]     | and              |

`if 文`のステートメント:

  - `[BirthDate]>date(1992,09,15,4,06,55)`

  - `[Department]="Development"`

論理演算子が `and` であるため、実行する `maxif` 集計の両方の条件が true である必要があります。

<a name='calc-fields-and-or'></a>
## And と Or

`and` および `or` 関数は、適用する必要のある 2 つの論理テストを宣言してネスト if 条件を構築できます。and および or に同じ構文があります。

| 関数名 | 論理テスト 1 | 論理テスト 2 | 出力                                                                                                                    |
| ------------- | -------------- | -------------- | ------------------------------------------------------------------------------------------------------------------------- |
| **and** (…​)  | `logical1`     | `logical2`     | **両方の条件が満たされる場合、1 を返します**。 **条件の 1 つのみを満たす**場合、または **条件が満たされない**場合、**0 を返します**。              |
| **or** (…​)   | `logical1`     | `logical2`     | **両方の条件、または条件の1 つのみを満たす場合、1 を返します**。**条件が満たされない**場合、**0 を返します**。 |

### サンプル

以下は and および or サンプルの例です。場合、0 を返します。

  - `and([BirthDate]>date(1983,07,15,04,06,55), [Department]="CPA")`

  - `or([Office]="London,UK",[BirthDate]<date(1992,09,15,4,06,55))`

含まれる構文は同じです。

| 関数名 | 論理テスト 1                          | 論理テスト 2                         | 出力                         |
| ------------- | --------------------------------------- | -------------------------------------- | ------------------------------ |
| `and (…​)`    | `[BirthDate]>date(1983,07,15,04,06,55)` | `[Department]="CPA"`                   | 行に基づいた 1 および 0。 |
| `or (…​)`     | `[Office]="London,UK"`                  | `[BirthDate]<date(1992,09,15,4,06,55)` | 行に基づいた 1 および 0。 |

and 計算フィールドは 4 つの TRUE 行のみ返します。

  - 行 7 (従業員 Zolleis Walker)。

  - 行 57 (従業員 Yancy Martinez)。

  - 行 94 (従業員 Nicolas Favarelli)。

  - 行 96 (従業員 Jorge Stanatto)。

[ルールでフィルターする](~/jp/data-visualizations/fields/field-filters-rules.html#rules-numeric-fields) または [値を選択する](~/jp/data-visualizations/fields/field-filters-rules.html#select-values) 1.00 を適用した場合のみ 2 つの行を確認します。

Zolleis Walker を見つけるために and 条件を設定し直す場合、以下の論理テストを使用できます。

<style type="text/css">
.tg  {border-collapse:collapse;border-spacing:0;}
.tg td{font-family:Arial, sans-serif;font-size:14px;padding:10px 5px;border-style:solid;border-width:1px;overflow:hidden;word-break:normal;border-color:black;}
.tg th{font-family:Arial, sans-serif;font-size:14px;font-weight:normal;padding:10px 5px;border-style:solid;border-width:1px;overflow:hidden;word-break:normal;border-color:black;}
.tg .tg-cly1{text-align:left;vertical-align:middle}
.tg .tg-ycr8{background-color:#ffffff;text-align:left;vertical-align:top}
.tg .tg-yla0{font-weight:bold;text-align:left;vertical-align:middle}
.tg .tg-0lax{text-align:left;vertical-align:top}
.gray-snippet-cstm{color: #666;background-color: #DDDDDD;}
</style>

<table class="tg">
  <tr>
    <th class="tg-yla0">関数名</th>
    <th class="tg-cly1"><span style="font-weight:bold">論理テスト 1</span></th>
    <th class="tg-0lax"><span style="font-weight:bold">論理テスト 2</span></th>
    <th class="tg-0lax"><span style="font-weight:bold">論理テスト 3</span></th>
  </tr>
  <tr>
    <td class="tg-0lax" rowspan="2"><span class="gray-snippet-cstm">and (…)</span></td>
    <td class="tg-0lax" rowspan="2"><span class="gray-snippet-cstm">[BirthDate]&gt;date(1981,07,15,4,06,05)</span></td>
    <td class="tg-0lax" rowspan="2"><span class="gray-snippet-cstm">[Department]="CPA"</span></td>
    <td class="tg-0lax"><span class="gray-snippet-cstm">[Wage]&gt;150000</span></td>
  </tr>
  <tr>
    <td class="tg-ycr8"><span class="gray-snippet-cstm">[Office]="Tokyo,Japan"</span></td>
  </tr>
</table>

and/or 関数を [isempty](information.html#isempty) 計算フィールドと組み合わせて同じ結果を取得することも可能です。

| 関数名 | 論理テスト 1 | 論理テスト 2 | 論理テスト 3  | 論理テスト 4            |
| ------------- | -------------- | -------------- | --------------- | ------------------------- |
| `and (…​)`    | 同上  | 同上  | `[OfficeId]>=3` | `ISEMPTY([ResignedDate])` |

構文が追加の引数によって複雑になるため、追加の条件をネストして論理テストをグループ化できます。結果に影響はありませんが、2 つ目の and を明確に定義する必要があります。

`and([BirthDate]>date(1981,07,15,4,06,05),[Department]="CPA",[OfficeId]>=3,ISEMPTY([ResignedDate]))`

  - 論理テスト 1: `[BirthDate]>date(1983,07,15,4,06,55)`

  - 論理テスト 2: `[Department]="CPA"`

  - 論理テスト 3: `[OfficeId]>=3`

  - 論理テスト 4: `ISEMPTY([ResignedDate])`

### 複雑な計算フィールドの簡素化

複数の if 条件に基づいた結果が必要な場合は、上記のサンプルの数式などが便利ですが、構文は複雑になります。個別の計算フィールドを作成して 1 つの数式に結合することにより簡素化できます。たとえば、以下の計算フィールドがあります。

`and([BirthDate]>date(1981,07,15,4,06,05),[Department]="CPA",[OfficeId]>=3,ISEMPTY([ResignedDate]))`

4 つの if 条件があります。

  - `[BirthDate]>date(1983,07,15,4,06,55)`

  - `[Department]="CPA"`

  - `[OfficeId]>=3`

  - `ISEMPTY([ResignedDate])`

各 IF 条件の計算フィールドをわかりやすい名前で作成できます。

| IF ステートメント  | 新しい計算フィールド          | 計算済の数式                     |
| -------------- | ---------------------------------- | -------------------------------------- |
| IF ステートメント 1 | Employees Born after July 15, 1981 | `[BirthDate]>date(1981,07,15,4,06,05)` |
| IF ステートメント 2 | CPA Employees                      | `[Department]="CPA"`                   |
| IF ステートメント 3 | JP, UY and BG Employees            | `[OfficeId]>=3`                        |
| IF ステートメント 4 | Current Employees                  | `ISEMPTY([ResignedDate])`              |

これらの新しいステートメントを新しい計算フィールドに結合します。

`and([Employees Born after 1981],[CPA Employees],[JP, UY and BG
Employees],[Current Employees])`

<a name='calc-fields-not'></a>
## Not

Not 関数を使用して、論理テストが true かどうかを確認できます。デフォルトでは、Not をタップすると以下の構造が表示されます。

`not(logical)`

### サンプル

| 関数名 | 論理テスト     |
| ------------- | ---------------- |
| `not (…​)`     | `[OfficeId]>=3)` |

説明:

| 式   | 演算子 1 | 演算子 2 | 条件の引数 |
| ------------ | ---------- | ---------- | ----------------- |
| `[OfficeId]` | `>`        | `=`        | `3`               |

### Not を and/or と組み合わせる

Not を使用して `and`/`or` 計算フィールドで反対の結果を取得できます。

以下の and 計算フィールドは、両方の if 条件が同時に true の EmployeeId 66 (Zerbe Johansen) のみに 1 を返します。すべての他の行は 0 を返します。

| 関数名 | 論理テスト 1       | 論理テスト 2                         |
| ------------- | -------------------- | -------------------------------------- |
| `and (…​)`     | `[Department]="CPA"` | `[BirthDate]>date(1992,09,15,4,06,55)` |

`not` を計算フィールドの前に追加することにより、反対の結果を取得できます。

| not        | and        | 論理テスト 1       | 論理テスト 2                         |
| ---------- | ---------- | -------------------- | -------------------------------------- |
| `not (…​)`  | `and (…​)`  | `[Department]="CPA"` | `[BirthDate]>date(1992,09,15,4,06,55)` |

以前 0 を返したすべての行は 1 を返し、すべての 1 は 0 になります。

<a name='true-false'></a>
## True と False

`true` と false 関数が引数なしで使用されます。つまり論理テストが適用されていないため、**論理テストを実行する式や特定のステートメントがありません**。

これらを if などの他の論理計算フィールドと組み合わせて使用すると便利です。以下は一般的な if 構文の例です。

| 関数名 | 引数 1     | 引数 2      | 引数 3       |
| ------------- | -------------- | --------------- | ---------------- |
| **if** (…​)    | `logical test` | `value if true` | `value if false` |

この式を、セクションの最初にある if の例で置き換えましょう (`if([BirthDate]<date(1971,04,15,4,06,55),1,0)`)。更に true の場合の値と false の場合の値の引数の値を 3 と 4 に変更します。

| 関数名 | 論理テスト                           | true の場合の値 | false の場合の値 |
| ------------- | -------------------------------------- | ------------- | -------------- |
| if (…​)        | `[BirthDate]<date(1971,04,15,4,06,55)` | `3`           | `4`            |

if ステートメントの出力は、論理テストが true の場合 3、論理テストが false の場合 4 です。標準 1.0 ブール値の結果を使用する場合、その位置に `true()` and `false()` を含むことができます。

| 関数名 | 論理テスト                           | true の場合の値 | false の場合の値 |
| ------------- | -------------------------------------- | ------------- | -------------- |
| if (…​)        | `[BirthDate]<date(1971,04,15,4,06,55)` | `true()`      | `false()`      |

論理テストに基づいて if 数式の出力を強制的に 1 と 0 にします。
