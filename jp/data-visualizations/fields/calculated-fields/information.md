---
title: Slingshot で情報計算フィールドを使用する方法 
_description: 情報計算フィールドで選択したフィールドの値を使用してテストする方法を説明します。
_language: ja
---

# 情報計算フィールド

情報計算フィールドは、指定したフィールドの値のテストに使用します。サイズの大きいスプレッドシートの場合、2 回目の計算を実行する前に作業する情報のタイプを確認できるため、大変便利です。

以下は情報カテゴリに含まれる関数です。

<style type="text/css">
.tg  {border-collapse:collapse;border-spacing:0;}
.tg td{font-family:Arial, sans-serif;font-size:14px;padding:10px 5px;border-style:solid;border-width:1px;overflow:hidden;word-break:normal;border-color:black;}
.tg th{font-family:Arial, sans-serif;font-size:14px;font-weight:normal;padding:10px 5px;border-style:solid;border-width:1px;overflow:hidden;word-break:normal;border-color:black;}
.tg .tg-cly1{text-align:left;vertical-align:middle}
.gray-snippet-cstm{color: #666;background-color: #ddd;}
</style>
<table class="tg">
  <tr>
    <th class="tg-cly1"><span style="font-weight:bold">関数名</span></th>
    <th class="tg-cly1"><span style="font-weight:bold">構文とサンプル</span></th>
  </tr>
  <tr>
    <td class="tg-cly1" rowspan="2"><span style="font-weight:bold">empty</span>: <span class="gray-snippet-cstm">empty</span> は、空のセルを含む列を挿入するために使用できます。構成する引数はありません。</td>
    <td class="tg-cly1"><span style="font-weight:bold">構文</span>:  <span class="gray-snippet-cstm">empty()</span></td>
  </tr>
  <tr>
    <td class="tg-cly1"><span style="font-weight:bold">サンプル</span>:  <span class="gray-snippet-cstm">empty()</span></td>
  </tr>
  <tr>
    <td class="tg-cly1" rowspan="2"><a href="https://help.revealbi.io/jp/information-calculated-fields#calculated-isempty"><span style="font-weight:bold">isempty</span></a>: <span class="gray-snippet-cstm">isempty</span>は指定した<span class="gray-snippet-cstm">`式`</span>を評価して<span style="font-weight:bold">データ ソースの各行の値が空かどうかをチェックします</span>。</td>
    <td class="tg-cly1"><span style="font-weight:bold">構文</span>:  <span class="gray-snippet-cstm">isempty({value})</span></td>
  </tr>
  <tr>
    <td class="tg-cly1"><span style="font-weight:bold">サンプル</span>:  <span class="gray-snippet-cstm">isempty([ResignedDate])</span></td>
  </tr>
</table>

<a name='isempty'></a>
## isempty

empty とは異なり、isempty は選択したフィールドおよびデータ シートの各行を確認します。行に値がない場合、出力は 1 です。値がある場合、0 が出力されます。

### Sample

| 関数名 | 構文             | サンプル                    |
| ------------- | ------------------ | ------------------------- |
| isempty       | `isempty({value})` | `isempty([ResignedDate])` |

`HR Dataset 2016.xlsx` スプレッドシートの 4 行について確認します。

| EmployeeID | FullName          | …​ | Resigned Date   | …​ | Calculated Field |
| ---------- | ----------------- | -- | --------------- | -- | ---------------- |
| 1.00       | Joan Baez         | …​ |                 | …​ | 1.00             |
| 4.00       | Zurcher Reid      | …​ | **28-Dec-2016** | …​ | 0.00             |
| 22.00      | Zornes Hall       | …​ |                 | …​ | 1.00             |
| 35.00      | Zdiarski Campbell | …​ | **09-Apr-2016** | …​ | 0.00             |
