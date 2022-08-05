---
title: 数学計算フィールドを使用する方法
_description: 数学計算フィールドを使用してダッシュボードを完成させる方法を説明します。
_language: ja
---

# 数学計算フィールド


MATH カテゴリのすべての関数はオンザフライで計算を実行する際に大変便利です。`rand` や `randbetween` 関数などの特定の関数は、データ ソースの行の順序をランダム化する場合に便利です。

以下はこのカテゴリに含まれる関数です。

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
    <td class="tg-cly1" rowspan="2"><span style="font-weight:bold">abs</span>: <span class="gray-snippet-cstm">abs</span> 関数は入力した数値の絶対値 (記号なしの数値) を返します。</td>
    <td class="tg-cly1"><span style="font-weight:bold">構文</span>: <span class="gray-snippet-cstm">abs({number})</span></td>
  </tr>
  <tr>
    <td class="tg-cly1"><span style="font-weight:bold">サンプル</span>: <span class="gray-snippet-cstm">abs(-3)</span></td>
  </tr>
  <tr>
    <td class="tg-cly1" rowspan="2"><span style="font-weight:bold">exp</span>: <span class="gray-snippet-cstm">exp</span> 関数は e (<a href="https://www.nde-ed.org/EducationResources/Math/Math-e.php">Euler の数値</a>) を入力した値で乗した値を返します。</td>
    <td class="tg-cly1"><span style="font-weight:bold">構文</span>: <span class="gray-snippet-cstm">exp({number})</span></td>
  </tr>
  <tr>
    <td class="tg-cly1"><span style="font-weight:bold">サンプル</span>: <span class="gray-snippet-cstm">exp(8)</span></td>
  </tr>
  <tr>
    <td class="tg-0lax" rowspan="2"><span style="font-weight:bold">log</span>: <span class="gray-snippet-cstm">log</span> 関数は関数で指定された数を底とする数値の対数を返します。底が入力されていない場合、Reveal は対数の底が 10 であると仮定します。</td>
    <td class="tg-0lax"><span style="font-weight:bold">構文</span>: <span class="gray-snippet-cstm">log({number},{logbase})</span></td>
  </tr>
  <tr>
    <td class="tg-0lax"><span style="font-weight:bold">サンプル</span>: <span class="gray-snippet-cstm">log(10,4)</span></td>
  </tr>
  <tr>
    <td class="tg-0lax" rowspan="2"><span style="font-weight:bold">log10</span>: <span class="gray-snippet-cstm">log10</span> は数値の対数を返します。ただし、底は常に 10 に設定されます。</td>
    <td class="tg-0lax"><span style="font-weight:bold">構文</span>: <span class="gray-snippet-cstm">log10({number})</span></td>
  </tr>
  <tr>
    <td class="tg-0lax"><span style="font-weight:bold">サンプル</span>: <span class="gray-snippet-cstm">log10(1500)</span></td>
  </tr>
  <tr>
    <td class="tg-0lax" rowspan="2"><span style="font-weight:bold">mod</span>: <span class="gray-snippet-cstm">mod</span> は 2 つの数値を除算した場合の剰余または少数部を返します。</td>
    <td class="tg-0lax"><span style="font-weight:bold">構文</span>: <span class="gray-snippet-cstm">mod({number},{divisor})</span></td>
  </tr>
  <tr>
    <td class="tg-0lax"><span style="font-weight:bold">サンプル</span>: <span class="gray-snippet-cstm">od(5,3)</span></td>
  </tr>
  <tr>
    <td class="tg-0lax" rowspan="2"><span style="font-weight:bold">rand</span>: <span class="gray-snippet-cstm">rand</span> は 0 より大きく 1 未満の 実数を返します。関数に引数は必要ありません。引数を設定する必要はありませんが、乱数をさらに変更するための数学演算子を含むことができます。</td>
    <td class="tg-0lax"><span style="font-weight:bold">構文</span>: <span class="gray-snippet-cstm">rand()</span></td>
  </tr>
  <tr>
    <td class="tg-0lax"><span style="font-weight:bold">サンプル</span>: <span class="gray-snippet-cstm">rand()</span></td>
  </tr>
  <tr>
    <td class="tg-0lax" rowspan="2"><span style="font-weight:bold">randbetween</span>: <span class="gray-snippet-cstm">randbetween</span> は、関数の引数で指定した範囲に入る整数を返します。乱数をさらに変更するための数学演算子を含むことができます。</td>
    <td class="tg-0lax"><span style="font-weight:bold">構文</span>: <span class="gray-snippet-cstm">randbetween({bottom},{top}</span>)</td>
  </tr>
  <tr>
    <td class="tg-0lax"><span style="font-weight:bold">サンプル</span>: <span class="gray-snippet-cstm">randbetween(0,9878654)</span></td>
  </tr>
  <tr>
    <td class="tg-0lax" rowspan="2"><span style="font-weight:bold">sign</span>: <span class="gray-snippet-cstm">sign</span> 関数は数値の符号を決定して返します。</td>
    <td class="tg-0lax"><span style="font-weight:bold">構文</span>: <span class="gray-snippet-cstm">sign({number})</span></td>
  </tr>
  <tr>
    <td class="tg-0lax"><span style="font-weight:bold">サンプル</span>: <span class="gray-snippet-cstm">sign(-1564)</span></td>
  </tr>
  <tr>
    <td class="tg-0lax" rowspan="2"><span style="font-weight:bold">sqrt</span>: <span class="gray-snippet-cstm">sqrt</span> 関数は指定した数値の平方根を返します。</td>
    <td class="tg-0lax"><span style="font-weight:bold">構文</span>: <span class="gray-snippet-cstm">sqrt({number})</span></td>
  </tr>
  <tr>
    <td class="tg-0lax"><span style="font-weight:bold">サンプル</span>: <span class="gray-snippet-cstm">sqrt(427716)</span></td>
  </tr>
  <tr>
    <td class="tg-0lax" rowspan="2"><span style="font-weight:bold">trunc</span>: <span class="gray-snippet-cstm">trunc</span> 関数は数値の整数部分 (小数以外) を返します。</td>
    <td class="tg-0lax"><span style="font-weight:bold">構文</span>: <span class="gray-snippet-cstm">trunc({number})</span></td>
  </tr>
  <tr>
    <td class="tg-0lax"><span style="font-weight:bold">サンプル</span>: <span class="gray-snippet-cstm">trunc(65787.24657)</span></td>
  </tr>
</table>                                                                                                                                                                                                     
