# フィールドで並べ替え

Reveal では、データを昇順または降順に並べ替えることで、表示形式のデータの表示方法を変更できます。さらに、元のデータ ソースで選択したフィールドで並べ替えることで、表示形式の外観をさらに制御することもできます。

<img src="images/sort-visualization-by-field.png" alt="Sort Visualization by setting dialog" class="responsive-img"/>

## フィールドで並べ替えを有効にする 

**並べ替え条件**オプションはフィールド設定の一部ですが、デフォルトでは非表示になっています。有効にする方法:

1. **[ラベル]** プレースホルダーからフィールドを選択します。
2. **[フィールド設定]**で、**[並べ替え]** に **[昇順]** または **[降順]** を選択します。
3. **[並べ替え条件]** は、**[並べ替え]** 設定の下に表示されます。右側のドロップダウンからフィールドを選択できます (上記を参照)。

より実用的な情報については、この機能を示す次の例をご覧ください。

  - [企業を優先順位で順序](#by-priority)

  - [文字列日付を時系列で並べ替え](#string-date-chr-order)

<a name='by-priority'></a>
## サポート ケースを優先順位で順序

フィールドをアルファベット順に並べ替えるのではなく、ビジネス ロジックを使用して並べ替えたいシナリオがあります。
たとえば、以下は、その週の新しいサポート ケースを昇順で表示する表示形式です。

<img src="images/RevenueCompanyFilterSample_All.png" alt="Welcome image for Reveal" class="responsive-img"/>

_Priority_ フィールドはテキスト フィールドであるため、デフォルトでは A-Z の順序になっています。ただし、ビジネス ロジックを使用する場合、_Priority_ 値は次のように並べ替える必要があります: _Low_ - _Normal_ - _High_。これを実現するには、データセットに優先度ステータスの数値表現を示す _Priority Level_ 列が必要です (以下を参照)。

<img src="images/RevenueCompanyPriority_All.png" alt="Welcome image for Reveal" class="responsive-img"/>

[並べ替え条件] フィールド オプションを使用して、*Priority Level* フィールドをデータ エディターに実際にドラッグアンドドロップせずに、チャート内の情報を優先度レベル別に整理します。

<img src="images/ForecastPriorityLevel_All.png" alt="Welcome image for Reveal" class="responsive-img"/>

したがって、結果のウィジェットは、優先度が *Low* の新しいケースを最初に配置し、A-Z の順序で並べ替え、その後に *Normal* の優先度のケースを配置し、最後に優先度の *High* のケースを配置します。

<img src="images/ForecastSortByFieldFinal_All.png" alt="Welcome image for Reveal" class="responsive-img"/>  

<a name='string-date-chr-order'></a>
## 文字列日付を時系列で順序

次の表示形式を見てみましょう。ここでは、[積層型柱状チャート](~/jp/visualization-tutorials/stacked-charts.html#create-stacked-chart)で企業の現金と売掛金の増加をプロットしています。

<img src="images/SortByFieldSalesInformation_All.png" alt="SortByFieldSalesInformation\_All" class="responsive-img"/>

値は、**Month Name** (文字列フィールド) で並べ替えされています。ただし、月はデフォルトでアルファベット順に並べ替えされているため、結果の表示形式は分析には適しません。

ただし、書式を変更し、**Date** の順に情報を並べ替えることで、**Month Name** の表示方法を変更できます。Y 軸 (**Date**) に 1-12 の数値を表示する必要はないかもしれませんが、それでもその順序を優先する必要があります。データ エディターのラベル プレースホルダーで **Month Name** フィールドを選択し、目的の並べ替えを選択します。

<img src="images/FieldSettingsSortBy_All.png" alt="FieldSettingsSortBy\_All" class="responsive-img"/>

この後、**[フィールドの更新]** を選択します。情報は時系列順に並べ替えられます。

<img src="images/FinalSortingFinancialSample_All.png" alt="FinalSortingFinancialSample\_All" class="responsive-img"/>

