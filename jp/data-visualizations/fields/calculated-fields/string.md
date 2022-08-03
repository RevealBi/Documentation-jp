---
title: How to use String Calculated Fields
_description: Learn how to use String Calculated Fields to create a more precise data visualization.
_language: ja
---

# 文字列計算フィールド

文字列計算フィールド (`sortinterval` 以外) はテキストを編集でき、さまざまな結果を取得することができます。

**文字列の間に引用符 (" ") を常に含めてください。**

以下は String カテゴリに含まれる関数です。


<style type="text/css">
.tg  {border-collapse:collapse;border-spacing:0;}
.tg td{font-family:Arial, sans-serif;font-size:14px;padding:10px 5px;border-style:solid;border-width:1px;overflow:hidden;word-break:normal;border-color:black;}
.tg th{font-family:Arial, sans-serif;font-size:14px;font-weight:normal;padding:10px 5px;border-style:solid;border-width:1px;overflow:hidden;word-break:normal;border-color:black;}
.tg .tg-cly1{text-align:left;vertical-align:middle}
.tg .tg-yla0{font-weight:bold;text-align:left;vertical-align:middle}
.tg .tg-0lax{text-align:left;vertical-align:top}
.gray-snippet-cstm{color: #666;background-color: #ddd;}
</style>
<table class="tg">
  <tr>
    <th class="tg-cly1"><span style="font-weight:bold">関数名</span></th>
    <th class="tg-cly1"><span style="font-weight:bold">構文とサンプル</span></th>
  </tr>
  <tr>
    <td class="tg-cly1" rowspan="2"><span style="font-weight:bold">concatenate</span>: <span class="gray-snippet-cstm">concatenate</span> は、複数の文字列 <span class="gray-snippet-cstm">テキスト</span>を結合して句を構成できます。スペースは自動的には含まれません。必要な場合は、テキスト引数に含む必要があります。</td>
    <td class="tg-cly1"><span style="font-weight:bold">構文</span>: <span class="gray-snippet-cstm">concatenate()</span></td>
  </tr>
  <tr>
    <td class="tg-cly1"><span style="font-weight:bold">サンプル</span>: <span class="gray-snippet-cstm">concatenate("Getting started"," with"," the"," Reveal"," application")</span></td>
  </tr>
  <tr>
    <td class="tg-cly1" rowspan="2"><a href="#calc-fields-find">find</a>: <span class="gray-snippet-cstm">find</span> は引数で指定した 2 つ目の文字列内 の 1 つ目 の文字列の開始位置 <span class="gray-snippet-cstm">(数値)</span> を返します。</td>
    <td class="tg-cly1"><span style="font-weight:bold">構文</span>: <span class="gray-snippet-cstm">find({find text},{within text},{start number})</span></td>
  </tr>
  <tr>
    <td class="tg-cly1"><span style="font-weight:bold">サンプル</span>: <span class="gray-snippet-cstm">find("with","Getting Started with Reveal visualizations",3)</span></td>
  </tr>
  <tr>
    <td class="tg-cly1" rowspan="2"><span style="font-weight:bold">len</span>: <span class="gray-snippet-cstm">len</span> は入力した <span class="gray-snippet-cstm">テキスト</span> 文字列のすべて大文字を小文字へ変換します。</td>
    <td class="tg-cly1"><span style="font-weight:bold">構文</span>: <span class="gray-snippet-cstm">len({text})</span></td>
  </tr>
  <tr>
    <td class="tg-cly1"><span style="font-weight:bold">サンプル</span>: <span class="gray-snippet-cstm">len("Getting Started with Reveal")</span></td>
  </tr>
  <tr>
    <td class="tg-yla0" rowspan="2">lower: <span style="font-weight:normal"><span class="gray-snippet-cstm">lower</span> は指定した<span class="gray-snippet-cstm">テキスト</span>文字列のすべて大文字を小文字へ変換します。</span></td>
    <td class="tg-cly1"><span style="font-weight:bold">構文</span>: <span class="gray-snippet-cstm">lower({text})</span></td>
  </tr>
  <tr>
    <td class="tg-cly1"><span style="font-weight:bold">サンプル</span>: <span class="gray-snippet-cstm">lower("Getting Started with Reveal")</span></td>
  </tr>
  <tr>
    <td class="tg-cly1" rowspan="2"><a href="#calc-fields-mid">mid</a>: <span class="gray-snippet-cstm">mid</span> は引数で指定したことに基づいて指定した文字列<span class="gray-snippet-cstm">テキスト</span>の部分文字列 (<span class="gray-snippet-cstm">長さ</span>) を返します。</td>
    <td class="tg-cly1"><span style="font-weight:bold">構文</span>: <span class="gray-snippet-cstm">mid({text},{start},{length})</span></td>
  </tr>
  <tr>
    <td class="tg-cly1"><span style="font-weight:bold">サンプル</span>: <span class="gray-snippet-cstm">mid("Getting Started with Reveal",9,12)</span></td>
  </tr>
  <tr>
    <td class="tg-cly1" rowspan="2"><a href="#calc-fields-replace">replace</a>: <span class="gray-snippet-cstm">replace</span> は文字列を関数で指定した他の文字列と置き換えます。</td>
    <td class="tg-cly1"><span style="font-weight:bold">構文</span>: <span class="gray-snippet-cstm">replace({text},{old text},{new text})</span></td>
  </tr>
  <tr>
    <td class="tg-cly1"><span style="font-weight:bold">サンプル</span>: <span class="gray-snippet-cstm">replace("Getting Started with Reveal","Getting Started","Creating Visualizations with")</span></td>
  </tr>
  <tr>
    <td class="tg-cly1" rowspan="4"><a href="#calc-fields-sortinterval">sortinterval</a>: <span class="gray-snippet-cstm">sortinterval</span> は、関数で設定された間隔で値を返します。<span class="gray-snippet-cstm">NN [from,to]</span> の書式として文字列が返されます。</td>
    <td class="tg-cly1"><span style="font-weight:bold">構文</span>: <span class="gray-snippet-cstm">sortinterval()</span></td>
  </tr>
  <tr>
    <td class="tg-cly1"><span style="font-weight:bold">サンプル 1</span>: <span class="gray-snippet-cstm">sortinterval(33,140)</span></td>
  </tr>
  <tr>
    <td class="tg-0lax"><span style="font-weight:bold">サンプル 2</span>: <span class="gray-snippet-cstm">sortinterval([Wage],150000)</span></td>
  </tr>
  <tr>
    <td class="tg-cly1"><span style="font-weight:bold">サンプル 3:</span> <span class="gray-snippet-cstm">sortinterval([Wage],50000,80000,110000,140000)</span></td>
  </tr>
  <tr>
    <td class="tg-cly1" rowspan="2"><span style="font-weight:bold">trim</span>: <span class="gray-snippet-cstm">trim</span> は入力した文字列と同じ文字列を返しますが、先行または後続の空白を削除し、単語間の空白のみ保持します。</td>
    <td class="tg-cly1"><span style="font-weight:bold">構文</span>: <span class="gray-snippet-cstm">trim({text})</span></td>
  </tr>
  <tr>
    <td class="tg-cly1"><span style="font-weight:bold">サンプル</span>: <span class="gray-snippet-cstm">trim(" Getting Started with Reveal ")</span></td>
  </tr>
  <tr>
    <td class="tg-cly1" rowspan="2"><span style="font-weight:bold">upper</span>: <span class="gray-snippet-cstm">upper</span> は指定したテキスト文字列のすべて大文字を小文字へ変換します。</td>
    <td class="tg-cly1"><span style="font-weight:bold">構文</span>: <span class="gray-snippet-cstm">upper({text})</span></td>
  </tr>
  <tr>
    <td class="tg-0lax"><span style="font-weight:bold">サンプル</span>: <span class="gray-snippet-cstm">upper("Caution: Hot. Do not touch")</span></td>
  </tr>
</table>


<a name='calc-fields-find'></a>
## Find

find 関数は、引数で指定した 1 つ目と 2 つ目の文字列の開始位置を返します。

### 構文

引数を 3 つ設定する必要があります。

  - `テキスト`: 検索するテキスト。

  - `テキスト内`: 検索を実行するテキスト。

  - `開始番号`: 検索を開始する文字。

### サンプル

以下は上記の表のサンプルです。

| 関数名 | 検索テキスト | テキスト内                                    | 開始番号 | 出力 |
| ------------- | --------- | ---------------------------------------------- | ------------ | ------ |
| find(…​)      | `"with"`  | `"Getting Started with Reveal visualizations"` | `3`          | 15     |

検索は Getting の 最初の `t` で開始します。結果の 15 は `with` の `w` が位置する文字番号です。

| C. 1  | C. 2 | C. 3 | C. 4 | C. 5 | C. 6 | C. 7 | C. 8 | C. 9 | C. 10 | C. 11 | C. 12 | C. 13 | C. 14 | C. 15 |
| ----- | ---- | ---- | ---- | ---- | ---- | ---- | ---- | ---- | ----- | ----- | ----- | ----- | ----- | ----- |
| **t** | t    | i    | n    | g    |      | S    | t    | a    | r     | t     | e     | d     |       | **w** |

`with` が句で複数回繰り返される場合、計算フィールドは**単語の最初の発生**の文字を返します。

<a name='calc-fields-mid'></a>
## Mid

Mid 計算フィールドは関数の構成に基づいて指定した文字列の一部を返します。

### 構文

3 つのパラメーターを構成します。

  - `テキスト`: 文字列を選択するテキスト。

  - `開始`: 新しい部分文字列を開始する文字。

  - `長さ`: 部分文字列の長さ。

### サンプル

以下は上記の表のサンプルです。

| 関数名 | テキスト                            | 開始 | 長さ | 出力       |
| ------------- | ------------------------------- | ----- | ------ | ------------ |
| mid(…​)       | `"Getting Started with Reveal"` | `9`   | `12`   | Started with |

テキスト文字列の開始が文字 9 で始まり、12 文字であるため、出力は`Started with` です。

| C. 9  | C. 10 | C. 11 | C. 12 | C. 13 | C. 14 | C. 15 | C. 16 | C. 17 | C. 18 | C. 19 | C. 20 |
| ----- | ----- | ----- | ----- | ----- | ----- | ----- | ----- | ----- | ----- | ----- | ----- |
| **S** | **t** | **a** | **r** | **t** | **e** | **d** |       | **w** | **i** | **t** | **h** |

<a name='calc-fields-replace'></a>
## Replace

Replace 関数は文字列を関数で指定した他の文字列と置き換えます。

### 構文

3 つの引数で構文されます。

  - `テキスト`: 元の完全な文字列テキスト。

  - `古いテキスト`: 置き換えられるテキスト。

  - `新しいテキスト`: 古いテキストを置き換えるテキスト。

### サンプル

以下はサンプルです。

| 関数名 | テキスト                                                                                                                         | 古いテキスト   | 新しいテキスト        | 出力                                                                                                                                      |
| ------------- | ---------------------------------------------------------------------------------------------------------------------------- | ---------- | --------------- | ------------------------------------------------------------------------------------------------------------------------------------------- |
| replace(…​)   | `"Using Reveal for iOS can be fast and easy. First, open the AppStore and look for Reveal. Then, install it. You're ready!"`  | `"Reveal"` | `"our BI tool"` | Using **our BI tool** for iOS can be fast and easy. First, open the AppStore and look for **our BI tool**. Then, install it. You're ready\! |

古いテキストはいずれの場合も置き換えられます。**変更する前に用語が表示されるたびに変更されることを考慮してください**。

<a name='calc-fields-sortinterval'></a>
## Sortinterval

Sortinterval 関数は、関数で設定された間隔で値を返します。

### 構文

返却文字列の書式は `NN [from, to]` です。

### サンプル

以下は上記の表のサンプルです。

| 関数名    | 数値   | 間隔 |
| ---------------- | -------- | -------- |
| sortinterval(…​)  | `[Wage]` | `150000` |

この場合、`Wage` を 1 つの値に対して比較し、2 つのカテゴリ (150K より大きい、150K 未満)に分類します。
150K.

以下の例は、`Wage` が 4 つの異なる値に対して比較し、5 つのカテゴリ (50000 未満、50000 から 80000、80000 から 110000、110000 から 140000、140000 より大きい) に分類します。

| 関数名    | 数値   | 間隔 1 | 間隔 2 | 間隔 3 | 間隔 4 |
| ---------------- | -------- | ---------- | ---------- | ---------- | ---------- |
| sortinterval(…​)  | `[Wage]` | `50000`    | `80000`    | `110000`   | `140000`   |
