---
title: ダッシュボード フィルターのプロパティを使用する方法
_description: ダッシュボード フィルター プロパティをすばやく適用して使用し、表示形式の効果を最大限に高める方法について説明します。
_language: ja
---

# ダッシュボード フィルターとそのプロパティ

## ダッシュボード フィルター プロパティにアクセスする

新しいダッシュボード フィルターを追加するには:

1.  ダッシュボード エディターに移動し、[フィルターの追加] ⇒ [ダッシュボード フィルターの追加] を選択します。

2.  [ダッシュボード フィルター] メニューが開きます。デフォルトで、選択されたデータ ソースは、初めての表示形式で使用されるデータ ソースになります。変更するには、データ ソース名の横にあるオーバーフロー ボタンを選択します。

    <img src="images/select-dashboard-filter-data-source-menu.png" alt="Selecting Dashboard Filter data source menu" class="responsive-img" width="80%"/>

3.  ダッシュボード フィルターとして使用するデータセットを選択し、[データの選択] をクリック/タップします。

## フィルター設定の概要

フィルターの以下の設定を変更できます:

<style type="text/css">
.tg  {border-collapse:collapse;border-spacing:0;}
.tg td{font-family:Arial, sans-serif;font-size:14px;padding:10px 5px;border-style:solid;border-width:1px;overflow:hidden;word-break:normal;border-color:black;}
.tg th{font-family:Arial, sans-serif;font-size:14px;font-weight:normal;padding:10px 5px;border-style:solid;border-width:1px;overflow:hidden;word-break:normal;border-color:black;}
.tg .tg-cly1{text-align:left;vertical-align:middle}
</style>
<table class="tg">
  <tr>
    <th class="tg-cly1" rowspan="5"><img src="images/dashboard-filter-dialog.png" alt="Dashboard Filter settings menu" width="400" height="300"></th>
    <th class="tg-cly1">タイトル。ダッシュボードのタイトルのすぐ下に表示される、ダッシュボード ィルターのタイトル。デフォルトで、これはフィルターとして使用されるフィールド名です。</th>
  </tr>
  <tr>
    <td class="tg-cly1"><a href="#displayed-field">表示フィールド/要素</a>。ダッシュボード フィルターとして使用されるデータセット内のフィールド。</td>
  </tr>
  <tr>
    <td class="tg-cly1"><span style="font-weight:bold">選択</span>。この設定では、次を構成できます。<a href="#multiple-selection">複数選択</a> (一度に複数の値を選択できます) および/または <a href="#required-selection">必須選択</a> (少なくとも 1 つの値を常に選択する必要があります)。</td>
  </tr>
  <tr>
    <td class="tg-cly1"><a href="#data-filters">データ フィルター</a>。この設定により、ダッシュボード フィルターに使用されるデータ ソースに<a href="~/jp/data-visualizations/fields/field-filters-rules.md">フィールド フィルターとルール</a>を適用できます。</td>
  </tr>
  <tr>
    <td class="tg-cly1"><a href="connecting-dashboard-filters-visualization.md">接続された表示形式</a>。ダッシュボードを表示形式に接続するかどうか。</td>
  </tr>
</table>

<a name='displayed-field'></a>
## 表示フィールド

>[!NOTE] 
>**Microsoft Analysis Services** および **Google アナリティクス**のデータを使用するダッシュボード フィルターの場合、この設定の名前は **[表示する要素]** です。

**表示するフィールド/要素**設定は、ダッシュボード フィルターの値を表示するために使用されるデータセット フィールドを指定します。リスト値は、元のデータセットで複数回表示された場合も繰り返されません。

ダッシュボード フィルター名の隣りのオーバーフロー メニューで [編集] ボタンをクリックして、編集モードで表示列を変更できます。

<img src="images/edit-mode-filter.png" alt="Accessing dashboard filter edit mode" class="responsive-img"/>

<a name='multiple-selection'></a>
## 複数選択

Reveal は、複数のダッシュボード フィルター値の同時選択をサポートしています。これにより、コレクション内で要素を並べて比較できます。たとえば、[HR ダッシュボード] で複数の選択を有効にすることで、さまざまなオフィスの雇用や欠勤を比較することができます。

<img src="images/multiple-selection-dashboard-filters.png" alt="Filters multiple selections applied to a dashboard" class="responsive-img" width="45%"/>

**[複数選択] を有効する**には、ダッシュボードを編集モードに替える必要があります。⇒ ダッシュボード フィルターのオーバーフロー ニューから [編集] を選択 ⇒ [選択] ⇒ [複数選択] チェックボックスをオンにします。

<img src="images/multiple-selection-option-dashboard-filter-dialog.png" alt="Enabling dashboard filters multiple selections" class="responsive-img" width="60%"/>

<a name='required-selection'></a>
## 必須選択

ダッシュボード フィルターで選択オプションを必須または無効にできます。
デフォルトでは、選択は不要です。選択オプションで、ユーザーがすべてのダッシュボード フィルター値を解除することができ、実行したクエリからフィルターを削除します。クエリはデータ ソースのすべてのデータを取得し、ダッシュボード フィルター行に「選択なし」と表示されます。

**[必須選択] を有効する**には、ダッシュボードを編集モードに替える必要があります。⇒ ダッシュボード フィルターのオーバーフロー ニューから [編集] を選択 ⇒ [選択] ⇒ [必須選択] チェックボックスをオンにします。

<img src="images/required-selection-option-filters.png" alt="Enabling dashboard filters required selection" class="responsive-img" width="60%"/>

<a name='data-filters'></a>
## データ フィルター

ダッシュボード フィルターに表示されるデータセットのフィールドにフィルターを適用することもできます。これにより、特定のフィールドの null または空の値をフィルター アウトできます ([空の値のフィルター](~/jp/data-visualizations/fields/field-filters-rules.html#empty-values))。[特定の値を選択する](~/jp/data-visualizations/fields/field-filters-rules.html#select-values)か、フィールド タイプに応じてオプションを変更するためにフィールドに[ルール](~/jp/data-visualizations/fields/field-filters-rules.html#rules)を追加することもできます。詳細は、「[フィールド フィルターとルール](~/jp/data-visualizations/fields/field-filters-rules.html)」トピックをご覧ください。

たとえば、**Fullname** フィールドを使用して **HR ダッシュボード**のデータをフィルタリングする場合、**ダッシュボード フィルター**は会社のすべてのオフィスの従業員リストを表示します。

<img src="images/data-filters-dashboard-filters-hr-dashboard-example.png" alt="Full name dashboard filter applied to HR Dashboard" class="responsive-img" width="50%"/>

ここでは、特定のオフィスで働いている従業員だけをフィルターとして使用する場合は、**データ フィルター** プロパティを適用でる、たとえば、*London, UK*。それにより、ダッシュボード フィルターには、ロンドンオフィスで働く従業員のリストが表示されます。

### ダッシュボード フィルターにデータ フィルターを適用

フィルター リストに特定のオフィスで働いている従業員のみ (たとえば、*London, UK*) を含める場合は、以下に示すようにデータ フィルターを適用します。

1.  ダッシュボード フィルター設定の**データ フィルター**に移動します。

2.  **表示フィールド**プロパティで **Employee Name** を選択します。

3.  [フィールドを選択] をクリック/タップして、リストから [オフィス] を選択します。

    <img src="images/dashboard-filter-select-data-filter-field.png" alt="Selecting a field for a data filter in the dashboard filter settings menu" class="responsive-img" width="60%"/>

4.  次のダイアログで、適用するフィルター タイプを選択します (この例では、**[値の選択]** を選択します)。

    <img src="images/option-filter-type.png" alt="Dashboard Filters Filter type option" class="responsive-img" width="60%"/>

5.  リストから *London, UK* を選択し、[フィルターの作成] ボタンをクリック/タップします。

## Microsoft Analysis Data を使用したダッシュボード フィルター

MS Analysis のダッシュボード フィルターを構成する場合、いくつかの詳細があります (以下のリストを参照)。

<img src="images/microsoft-analysis-services-dashboard-filter.png" alt="Dashboard Filter dialog when configuring an SSRS filter" class="responsive-img" width="60%"/>

 1. **表示される要素** - ダッシュボード フィルター値を表示するために **ディメンション**、**階層** または **レベル** データ フィールドを選択できますが、**メジャー** データ フィールドは選択できません。

 2. (オプション) **メジャーにデータがある場合のみ表示** - メジャーを選択して、ダッシュボードのフィルター リストを特定のメジャーのデータを含む値に制限します。

たとえば、上のスクリーンショットに見えるように、**Product** ディメンションは **[表示する要素]** として選択されているため、ダッシュボード フィルターには製品のリスト (自転車、衣服など) のリストが表示されます。
[メジャーにデータがある場合のみ表示] フィールドの **Interner orders** メジャーを追加選択すると、**Interner orders** メジャーに関する情報を含まないダッシュボード フィルター値を除外します。自転車のインターネット注文がない場合、その製品はダッシュボード フィルター リストに表示されません。

## 次の手順 

ダッシュボード フィルターを作成したので、フィルターを適用する**表示形式に接続する**必要があります。詳細は、「[ダッシュボード フィルターを表示形式に接続](connecting-dashboard-filters-visualization.html)」トピックをご覧ください。
