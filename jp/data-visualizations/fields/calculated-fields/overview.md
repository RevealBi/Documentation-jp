# 計算フィールド

Reveal では、計算フィールドというフィールドをデータセットに定義することができます。フィールドは、式 (数式) を使用して作成されます。式は、既存のフィールド、定数値、および以下の組み合わせにすることができます。

  - [定義済み関数](#predefined-functions)および/または

  - [単純な数学関数および定義されていない他の関数](#without-predefined-functions)。

以下の 2 種類の計算フィールドがあります。

  - [事前計算](#precalculated-fields) (計算済み) および

  - [事後計算](#postcalculated-fields)。

<a name='precalculated-fields'></a>
## 事前計算フィールド

事前計算フィールドは、データ エディターの集計を実行する前に評価されます。つまり、特定の数式を適用するために、Reveal はフィールドのデータセット内のすべてのレコードを 1 回または複数回調べます。そのため、大規模なデータセットを使用する場合、事前計算のパフォーマンスが低下する可能性があります。

新しい計算フィールドを追加するには、[フィールド] パネルの [+] ボタンをクリック/タップします。

<img src="images/pre-calculated-field-button.png" alt="計算フィールドのボタン" class="responsive-img"/>

[計算フィールドの作成] 画面が開きます。

<img src="images/new-calculated-field-screen.png" alt="New calculated field screen" class="responsive-img"/>

以下の手順を実行します。

1.  新しい計算フィールドに名前を割り当てます。

2.  数式(式)を入力します。[フィールド] セクションで、すべての既存のフィールドのリストがら選択できます。1 つ以上のフィールドを使用して (選択したフィールドをクリックまたは角括弧で名前を入力) 数式を作成できます。[関数] セクションにリストされている定義済み関数のいずれかを選択して、または単純な数学計算を使用します (上記に表示)。

新しい計算フィールドは、[フィールド] リストの下部に表示されます。

<img src="images/new-calculated-field-bottom-list.png" alt="New calculated field shown at the bottom of fields list" class="responsive-img"/>

上記の例では、集計がデータ フィールドに適用されていないグリッドの表示形式で新しい計算フィールドが使用されます。事前計算フィールドは、ピボット グリッドでも使用できます。この場合、計算は事前計算フィールドで集計されたレコードに適用されます。

<a name='postcalculated-fields'></a>
## 事後計算フィールド

データ エディターでデータ フィールドの集計を実行するピボット テーブルやその他の表示形式を使用する場合、事後計算フィールドを作成できます。事後計算フィールドは、すでに集計された値に数式を適用することによって常に作成されます。

事後計算フィールドを作成する手順:

1.  データ エディターでデータ ソースからフィールドを追加して、表示形式 (またはピボット テーブル) を作成します。

    <img src="images/post-calculated-fields-data-editor.png" alt="Post calculated fields in the Data editor" class="responsive-img"/>

2.  [値] の横にある [F(x)] ボタンをクリック/タップして、[計算フィールドの作成] 画面を開きます。

    <img src="images/post-calculated-field-new-calculated-field-screen.png" alt="Post calculated field new calculated field screen" class="responsive-img"/>

3.  事後計算のフィールドの [計算フィールドの作成] 画面
計算フィールドに名前を付け、集計値に数式を適用します。
注: 値のリストには、集計後に表示形式で使用したデータ フィールドが含まれています (Spend、Budget ではなく、Sum of Spend、Sum of Budget)。

データ エディターに含まれていないデータ ソースの他のフィールドを使用する場合は、[値] の横の [+] ボタンをクリック/タップして追加できます。事後計算フィールドは集計値のみで作成されるため、最初にデータ フィールドで実行する集計をドロップダウン リストから選択する必要があります。

<img src="images/post-calculated-field-new-calculated-field-screen-adding-fields.png" alt="Adding fields in the calculated field screen" class="responsive-img"/>

手順 1 をスキップして、最初に事後計算フィールドを作成するか、表示形式で事後計算フィールドのみを使用することもできます。

大規模なデータセットを使用する場合、事後計算は事前計算よりパフォーマンスが向上します。

<a name='predefined-functions'></a>
## Reveal 定義済み関数の使用

事前計算フィールドと事後計算フィールドの両方で、Reveal で使用可能な機能のいずれかを使用できます。

  - [**集計**](aggregation.html):
    [AVERAGE](aggregation.html#average)、
    [AVERAGEIF](aggregation.html#averageif)、
    [COUNT](aggregation.html#count)、
    [COUNTIF](aggregation.html#countif)、
    [MAX](aggregation.html#max)、
    [MAXIF](aggregation.html#maxif)、
    [MIN](aggregation.html#min)、
    [MINIF](aggregation.html#minif)

  - [**日付**](date.html):
    [DATE](date.html#date-date)、
    [DATEVALUE](date.html#datevalue)、
    [DAY](date.html#day)、
    [FORMATDATE](date.html#formatdate)、
    [FQUARTER](date.html#fquarter)、
    [FYEAR](date.html#fyear)、
    [HOUR](date.html#hour)、
    [MILLISECOND](date.html#millisecond)、
    [MINUTE](date.html#minute)、
    [MONTH](date.html#month)、
    [MONTHNAME](date.html#monthname)、
    [MONTHSHORTNAME](date.html#monthshortname)、
    [NOW](date.html#now)、
    [QUARTER](date.html#quarter)、
    [SECOND](date.html#second)、
    [TIME](date.html#date-time)、
    [TODAY](date.html#today)、
    [WEEKDAY](date.html#weekday)、
    [WEEKNUM](date.html#weeknum)、
    [YEAR](date.html#year)

  - [**情報**](information.html):
    [EMPTY](information.html#empty)、
    [ISEMPTY](information.html#isempty)

  - [**ロジック**](logic.html):
    [AND](logic.html#and)、
    [FALSE](logic.html#false)、
    [IF](logic.html#if)、
    [NOT](logic.html#not)、
    [OR](logic.html#or)、
    [TRUE](logic.html#true)

  - [**検索/行列**](lookup-reference.html):
    [PREVIOUS](lookup-reference.html#previous)、
    [ROW](lookup-reference.html#row)

  - [**数学**](math.html):
    [ABS](math.html#abs)、
    [EXP](math.html#exp)、
    [LOG](math.html#log)、
    [LOG10](math.html#log10)、
    [MOD](math.html#mod)、
    [RAND](math.html#rand)、
    [RANDBETWEEN](math.html#randbetween)、
    [SIGN](math.html#sign)、
    [SQRT](math.html#sqrt)、
    [TRUNC](math.html#trunc)

  - [**文字列**](string.html):
    [CONCATENATE](string.html#concatenate)、
    [FIND](string.html#find)、
    [LEN](string.html#len)、
    [LOWER](string.html#lower)、
    [MID](string.html#mid)、
    [REPLACE](string.html#replace)、
    [SORTINTERVAL](string.html#sortinterval)、
    [TRIM](string.html#trim)、
    [UPPER](string.html#upper)

>[!NOTE]
>IF 条件の制限: 事前計算のフィールドの集計関数に含まれる場合、IF 条件には既知の制限があります。計算式内の IF 条件を確認するためにすべてのレコードを複数回調べる必要があり、パフォーマンスが低下する問題が発生するため、サポートされていません。

<a name='without-predefined-functions'></a>
## 定義済み関数を使用せず計算フィールドを作成

定義済み関数を使用せずに計算フィールドを作成することもできます。たとえば、減算、除算、加算、乗算などの単純な数学計算用。[こちらの表](samples.html)には、定義済み関数を使用しない例があります。

## Reveal 関数を使用する際に以下に注意してください。

  - **テキスト文字列は引用符で囲む必要があります**。
    例えば、ロケール ("en") および日付書式 ("dd/mm/yyyy") 。

  - **数式に含まれるフィールドは角括弧で囲む必要があります**。たとえば、HR データセットの [Wage]、[BirthDate]、[EmployeeID] などです。
