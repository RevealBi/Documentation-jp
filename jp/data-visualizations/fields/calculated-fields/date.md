---
title: Slingshot で日付計算フィールドを使用する方法
_description: 日付計算フィールドを使用してさまざまな日時情報を出力する方法を説明します。
_language: ja
---

# 日付計算フィールド

日付数式は、ウィジェットでさまざまな日付と時刻の情報を出力するために使用できます。

**注:** 計算フィールドに数式に含まれる情報が表示されます。日付と時刻に設定した書式をオーバーライトします。

以下は日付カテゴリに含まれる関数です。

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
    <td class="tg-cly1" rowspan="2"><a href="https://help.revealbi.io/jp/date-calculated-fields#date-date">date</a>: date は数式に含まれる値へ日付セットを返します。</td>
    <td class="tg-cly1"><span style="font-weight:bold">構文</span>: <span class="gray-snippet-cstm">date({year},{month},{day},{hour},{minute},{second})</span></td>
  </tr>
  <tr>
    <td class="tg-cly1"><span style="font-weight:bold">サンプル</span>: <span class="gray-snippet-cstm">date(1971,11,08,12,59,08)</span></td>
  </tr>
  <tr>
    <td class="tg-cly1" rowspan="2"><span style="font-weight:bold">datevalue</span>: datevalue  は最初の (日付) 書式のない日付に指定した書式を適用します。その後指定した言語 (ロケール) の日付を返します。</td>
    <td class="tg-cly1"><span style="font-weight:bold">構文</span>: <span class="gray-snippet-cstm">datevalue({date},{format},{locale})</span></td>
  </tr>
  <tr>
    <td class="tg-cly1"><span style="font-weight:bold">サンプル</span>: <span class="gray-snippet-cstm">datevalue("23/05/2015","dd/mm/yyyy","en")</span></td>
  </tr>
  <tr>
    <td class="tg-cly1" rowspan="2"><span style="font-weight:bold">day</span>: day は date の構文を使用して数式での 3 番目の値を返します。</td>
    <td class="tg-cly1"><span style="font-weight:bold">構文</span>: <span class="gray-snippet-cstm">day({date})</span></td>
  </tr>
  <tr>
    <td class="tg-cly1"><span style="font-weight:bold">サンプル</span>: <span class="gray-snippet-cstm">day(date(1971,11,08,01,22,44))</span></td>
  </tr>
  <tr>
    <td class="tg-cly1" rowspan="2"><span style="font-weight:bold">formatdate</span>: formatdate は date の構文を使用して日付に指定した式を適用します。その後指定した言語 (`ロケール`) の日付を含むテキストを返します。</td>
    <td class="tg-cly1"><span style="font-weight:bold">構文</span>: <span class="gray-snippet-cstm">formatdate({date},{format},{locale})</span></td>
  </tr>
  <tr>
    <td class="tg-cly1"><span style="font-weight:bold">サンプル</span>: <span class="gray-snippet-cstm">formatdate(date(1971,11,08,01,22,44),"dd/mm/yyyy","en")</span></td>
  </tr>
  <tr>
    <td class="tg-cly1" rowspan="2"><span style="font-weight:bold">fquarter</span>: fquarter は date の構文と `数値` の 2 番目の引数を使用して指定した日付の会計年度の四半期を返します。</td>
    <td class="tg-cly1"><span style="font-weight:bold">構文</span>: <span class="gray-snippet-cstm">fquarter({date},{number})</span></td>
  </tr>
  <tr>
    <td class="tg-cly1"><span style="font-weight:bold">サンプル</span>: <span class="gray-snippet-cstm">fquarter(date(2017,12,1,12,33,48),4)</span></td>
  </tr>
  <tr>
    <td class="tg-cly1" rowspan="2"><span style="font-weight:bold">fyear</span>: fyear は date の構文と `数値`の 2 番目の引数を使用して指定した日付の会計年度を返します。</td>
    <td class="tg-cly1"><span style="font-weight:bold">構文</span>: <span class="gray-snippet-cstm">fyear({date},{number})</span></td>
  </tr>
  <tr>
    <td class="tg-cly1"><span style="font-weight:bold">サンプル</span>: <span class="gray-snippet-cstm">fyear(date(2017,12,1,12,33,48),2)</span></td>
  </tr>
  <tr>
    <td class="tg-cly1" rowspan="2"><span style="font-weight:bold">hour</span>: hour は date の構文を使用して数式での 4番目の値を返します。</td>
    <td class="tg-cly1"><span style="font-weight:bold">構文</span>: <span class="gray-snippet-cstm">hour({date})</span></td>
  </tr>
  <tr>
    <td class="tg-cly1"><span style="font-weight:bold">サンプル</span>: <span class="gray-snippet-cstm">hour(date(2017,12,1,12,33,48))</span></td>
  </tr>
  <tr>
    <td class="tg-cly1" rowspan="2"><span style="font-weight:bold">millisecond</span>: millisecond は time の構文を使用して数式での 4 番目の値を返します。</td>
    <td class="tg-cly1"><span style="font-weight:bold">構文</span>: <span class="gray-snippet-cstm">millisecond({time})</span></td>
  </tr>
  <tr>
    <td class="tg-cly1"><span style="font-weight:bold">サンプル</span>: <span class="gray-snippet-cstm">millisecond(time(11,29,48,799))</span></td>
  </tr>
  <tr>
    <td class="tg-cly1" rowspan="2"><span style="font-weight:bold">minute</span>: は date の構文を使用して数式での 5番目の値を返します。</td>
    <td class="tg-cly1"><span style="font-weight:bold">構文</span>: <span class="gray-snippet-cstm">minute({date})</span></td>
  </tr>
  <tr>
    <td class="tg-cly1"><span style="font-weight:bold">サンプル</span>: <span class="gray-snippet-cstm">minute(date(2017,12,1,12,33,48))</span></td>
  </tr>
  <tr>
    <td class="tg-cly1" rowspan="2"><span style="font-weight:bold">month</span>: month は date の構文を使用して数式での 2 番目の値を返します。</td>
    <td class="tg-cly1"><span style="font-weight:bold">構文</span>: <span class="gray-snippet-cstm">month({date})</span></td>
  </tr>
  <tr>
    <td class="tg-cly1"><span style="font-weight:bold">サンプル</span>: <span class="gray-snippet-cstm">month(date(2017,12,1,12,33,48))</span></td>
  </tr>
  <tr>
    <td class="tg-0lax" rowspan="2"><span style="font-weight:bold">monthname</span>: monthname は date の構文を使用して日付の月名を返します。</td>
    <td class="tg-0lax"><span style="font-weight:bold">構文</span>: <span class="gray-snippet-cstm">monthname({date},{locale})</span></td>
  </tr>
  <tr>
    <td class="tg-0lax"><span style="font-weight:bold">サンプル</span>: <span class="gray-snippet-cstm">monthname(date(2017,12,1,12,33,48),"en")</span></td>
  </tr>
  <tr>
    <td class="tg-0lax" rowspan="2"><span style="font-weight:bold">monthshortname</span>: monthshortname は date の構文を使用して月の名前を日付の短い 3 文字書式でを返します。</td>
    <td class="tg-0lax"><span style="font-weight:bold">構文</span>: <span class="gray-snippet-cstm">monthshortname({date},{locale})</span></td>
  </tr>
  <tr>
    <td class="tg-0lax"><span style="font-weight:bold">サンプル</span>: <span class="gray-snippet-cstm">monthshortname(date(2017,12,1,12,33,48),"en")</span></td>
  </tr>
  <tr>
    <td class="tg-0lax" rowspan="2"><span style="font-weight:bold">now</span>: now  は日付と時刻を返します。</td>
    <td class="tg-0lax"><span style="font-weight:bold">構文</span>: <span class="gray-snippet-cstm">now()</span></td>
  </tr>
  <tr>
    <td class="tg-0lax"><span style="font-weight:bold">サンプル</span>: <span class="gray-snippet-cstm">now()</span></td>
  </tr>
  <tr>
    <td class="tg-0lax" rowspan="2"><span style="font-weight:bold">quarter</span>: quarter は date の構文を使用して<span style="font-weight:bold">日付が属す四半期</span>を返します。</td>
    <td class="tg-0lax"><span style="font-weight:bold">構文</span>: <span class="gray-snippet-cstm">quarter({date})</span></span></td>
  </tr>
  <tr>
    <td class="tg-0lax"><span style="font-weight:bold">サンプル</span>: <span class="gray-snippet-cstm">quarter(date(2017,12,1,12,33,48))</span></span></td>
  </tr>
  <tr>
    <td class="tg-0lax" rowspan="2"><span style="font-weight:bold">second</span>: second は date の構文を使用して数式での 6 番目の値を返します。</td>
    <td class="tg-0lax"><span style="font-weight:bold">構文</span>: <span class="gray-snippet-cstm">second({date})</span></span></td>
  </tr>
  <tr>
    <td class="tg-0lax"><span style="font-weight:bold">サンプル</span>: <span class="gray-snippet-cstm">second(date(2017,12,1,12,33,48))</span></td>
  </tr>
  <tr>
    <td class="tg-0lax" rowspan="2"><a href="https://help.revealbi.io/jp/date-calculated-fields#date-time">time</a>: time を使用する場合、Reveal は数式に含まれる値に設定した時刻を返します。</td>
    <td class="tg-0lax"><span style="font-weight:bold">構文</span>: <span class="gray-snippet-cstm">time({hour},{minute},{second},{millisecond})</span></td>
  </tr>
  <tr>
    <td class="tg-0lax"><span style="font-weight:bold">サンプル</span>: <span class="gray-snippet-cstm">time(11,08,08,11)</span></td>
  </tr>
  <tr>
    <td class="tg-0lax" rowspan="2"><span style="font-weight:bold">today</span>: は現在の日付を返します。</td>
    <td class="tg-0lax"><span style="font-weight:bold">構文</span>: <span class="gray-snippet-cstm">today()</span></td>
  </tr>
  <tr>
    <td class="tg-0lax"><span style="font-weight:bold">サンプル</span>: <span class="gray-snippet-cstm">today()</span></td>
  </tr>
  <tr>
    <td class="tg-0lax" rowspan="2"><span style="font-weight:bold">weekday</span>: は date 構文を使用して<span style="font-weight:bold">日付の曜日</span>を返します。</td>
    <td class="tg-0lax"><span style="font-weight:bold">構文</span>: <span class="gray-snippet-cstm">weekday({date})</span></td>
  </tr>
  <tr>
    <td class="tg-0lax"><span style="font-weight:bold">サンプル</span>: <span class="gray-snippet-cstm">weekday(date(2017,12,1,12,33,48))</span></td>
  </tr>
  <tr>
    <td class="tg-0lax" rowspan="2"><span style="font-weight:bold">weeknum</span>: は date の構文を使用して、<span style="font-weight:bold">指定した年内の日付が該当する週の数</span>を返します。</td>
    <td class="tg-0lax"><span style="font-weight:bold">構文</span>: <span class="gray-snippet-cstm">weeknum({date})</span></td>
  </tr>
  <tr>
    <td class="tg-0lax"><span style="font-weight:bold">サンプル</span>: <span class="gray-snippet-cstm">weeknum(date(2017,12,1,12,33,48))</span></td>
  </tr>
  <tr>
    <td class="tg-0lax" rowspan="2"><span style="font-weight:bold">year</span>: year は date の構文を使用して数式での 1 番目の値を返します。</td>
    <td class="tg-0lax"><span style="font-weight:bold">構文</span>: <span class="gray-snippet-cstm">year({date})</span></td>
  </tr>
  <tr>
    <td class="tg-0lax"><span style="font-weight:bold">サンプル</span>: <span class="gray-snippet-cstm">year(date(2017,12,1,12,33,48))</span></td>
  </tr>
</table>

<a name='date-date'></a>
## Date

`date` を使用する場合、Reveal は日付セットを数式に含まれる値へ返します。

### 構文

デフォルトで、date を選択した際に以下の構成が表示されます。

`date({year},{month},{day},{hour},{minute},{second})`

すべての値 (`month` を含む) は、数値で表す必要があります。

### サンプル

次の構造の数式は 08-Nov-1971 12:59 を返します。

| 関数名 | Year | Month | Day | Hour | Minute | Second |
| ------------- | ---- | ----- | --- | ---- | ------ | ------ |
| date (…​)      | 1971 | 11    | 08  | 12   | 59     | 08     |

次の構造の数式は、hour の値が 24 時を超えているため 09-Nov-1971 03:59 を返します。数式の要素の順序は変更しないでください。

| 関数名 | Year | Month | Day | Hour   | Minute | Second |
| ------------- | ---- | ----- | --- | ------ | ------ | ------ |
| date (…​)      | 1971 | 11    | 08  | **27** | 59     | 08     |

<a name='date-time'></a>
## Time

time を使用する場合、Reveal は数式に含まれる値に設定した時刻を返します。

### 構文

デフォルトで、time を選択した際に以下の構成が表示されます。

`time({hour},{minute},{second},{millisecond})`

### サンプル

次の構造の数式は 11:08:08 を返します。

| 関数名 | Hour | Minute | Second | Millisecond |
| ------------- | ---- | ------ | ------ | ----------- |
| time (…​)      | 11   | 08     | 08     | 11          |

ミリ秒パラメーターは、計算フィールドに含まれません。ただし、異なる数式 (millisecond) 内の time に含まれる、値のみを表示することができます。