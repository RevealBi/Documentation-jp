---
title: 階級区分図設定を使用する方法
_description: このページで提供されるヒントで階級区分図を最大限に活用します。
_language: ja
---

# 階級区分図設定の操作

<img src="images/choropleth-map-visualization-settings.png" alt="Settings in the Visualization editor of the choropleth map" class="responsive-img" width="35%"/>

階級区分図表示形式の [設定] セクションでは、以下を設定できます:

  - **[タイトルの表示]** - 表示形式のタイトルを表示するかどうかを選択します。
  - **[凡例の表示]** - マップの上にカラー スケール範囲を表示するかどうかを選択します。
  - **[カラー]** - 配色のベースとして選択する色を選択します。平均データ値の領域はこの色で塗りつぶされます。対照的に、データ値が低いマップ領域は明るい色で表示され、高いデータ領域は暗い色で表示されます。
  - **[カラー バリエーション]** - 以下から選択できます:
      * [値範囲] - 7 色の範囲を配色として使用し、データ値に基づいて領域を塗りつぶします。
      * [単色] - 単一の色を使用して、データを含むすべての領域を表示します。情報のない領域は灰色です。

    >[!NOTE]
    >[マップ カラー] プレースホルダーにフィールドを追加した場合、[設定] の [カラー バリエーション] は [カラーの基準値] に変更されます。マップ カラーを使用した階級区分図の作成の詳細については、[こちら](choropleth-map.html#map-color)を参照してください。

  - **[ラベルの表示]** - 選択したマップがラベルをサポートする場合、ラベルを [すべて] の領域に配置するか、情報を含む領域のみに配置するか [値がある場合のみ]、オフにするか [なし] を選択できます。
  - **[現在のラベル]** - [場所の略語] を選択して、ラベルを使用して地域の地名 (省略) を示すことができます。または、ラベルに各領域の [値] を表示できます。値ラベルは、[値] フィールドに選択した書式設定に基づいて、数値、パーセント、または通貨としてマップに表示できます。

  - *[Connect this visualization to another dashboard or a URL](https://www.slingshotapp.io/en/help/docs/analytics/dashboards/dashboard-linking)* - If you want to provide more details on the information displayed in the visualization, you can connect the visualization in the dashbord with other dashboards or URLs. 

## ローカライズ設定

現在、データセットは英語と日本語で提供できます。

場所データが日本語の場合、Reveal はそれを英語に翻訳して目的のマップに接続します。

Reveal で日本語のデータセットを使用し、言語および地域設定が日本語に設定されていない場合、Reveal が日本語 (*ja*) に切り替えてデータセットの言語を認識するために **[データの言語]** 設定を使用する必要があります。

<img src="images/data-is-written-in-option.png" alt="Choosing Japanese from the dropdown menu of the Data is written in option" class="responsive-img" width="85%"/>


### ラベルの言語

階級区分図のラベルの言語は、OS またはブラウザーで構成された言語と地域の設定によって定義されます。ロケール/言語を [Reveal がサポートする言語](~/jp/general/supported-languages.md)に設定したマシンで Reveal を実行している場合、アプリはラベルをその言語にローカライズしようとします。これは [データの言語] 設定とは関係ありません。

たとえば、日本人の従業員のマシンが母国語 (日本語) を使用するように設定されていて、そのデータが英語の場合、Reveal はラベルを日本語で表示します。ダッシュボードをドイツの投稿者と共有した場合、ドイツ語のラベルはマシンで使用する言語で表示されます (ドイツ語は Reveal でサポートされます)。
