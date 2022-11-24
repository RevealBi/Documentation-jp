---
title: JSON ファイルを使用して Slingshot で表示形式を作成する手順
_description: JSON ファイルを使用して表示形式を向上し、データ インサイトを向上させる方法を説明します。
_language: ja
---

# JSON ファイルの作業

Reveal では、JSON ファイル データの表示形式をサポートします。

JSON ファイル形式を読み込んだ後、Reveal は使用する可能性のあるデータ構造を提供します。さらに、カスタム データ構造を選択できる[**高度な選択**](#json-advanced-selection)モードがあります。

## JSON 書式の情報

JSON (**J**ava**S**cript **O**bject **N**otation) は、データを保存および交換するための自己記述型の軽量な書式です。

書式のハイライト:

  - JSON の書式は、**データのさまざまな構造を表す**ために使用できます。

  - データは常に**コンマで区切られた名前/値のペア**として配置されます。

  - データ型の表記には、**オブジェクトの波括弧 {}** と**配列の角括弧 \[\]** が含まれます。

## JSON ファイルの読み込み

JSON ファイルのデータを使用する新しい表示形式を作成するには、次の手順に従います。

1.  **ファイルを利用できるようにする**。

    JSON ファイルをストレージ プロバイダーのいずれかにアップロードして、後で Reveal からアクセスできるようにします。次の使用可能なオプションから選択できます: Dropbox、OneDrive、Box、Google Drive、および SharePoint。

2.  **新しい表示形式を作成する**。

    ダッシュボード内で、JSON ファイルのデータを使用する表示形式を作成します。

3.  **ファイルを参照する**。

    a.  ファイルのあるストレージ プロバイダーを選択し、ログイン認証情報を提供します。

    b.  プロバイダーを参照し、JSON ファイルを選択します。

    <img src="images/add-data-file-json.png" alt="A JSON file located in a cloud data source" class="responsive-img" width="85%"/>

4.  **必要なデータ構造を選択する**。

    ファイルをスキャンした後、Reveal は選択可能なデータ構造のリストを表示します。

    <img src="images/json-data-source-details-dialog.png" alt="Json Files Choose Data table" class="responsive-img" width="55%"/>

    リストに目的のデータ構造が含まれていない場合は、[**高度な選択モード**](#json-advanced-selection)を使用して、カスタムデータ構造を選択できます。

5.  **[データの読み込み]** をクリック / タップする。

    データ構造を選択し、[データの読み込み] ボタンをクリック / タップして、表示形式エディターを開きます。

    <img src="images/visualization-editor-json-file-data.png" alt="Json Files Visualizations Editor" class="responsive-img" width="85%"/>

<a name='json-advanced-selection'></a>
## 高度な選択モード

JSON ファイルを使用して、さまざまなデータ構造を表すことができます。このため、Reveal では、作業するカスタム データ構造を選択できます。処理したいデータ列を選択した後、それらの上に表示形式を構築することができます。

1.  **高度な選択モードを開く**。

    **[+ テーブル]** ボタンをクリック/タップして、**[高度な選選択]** 画面にアクセスします。

    <img src="images/json-data-source-details-table-option.png" alt="Table option for advanced selection in the data source details dialog for json" class="responsive-img" width="55%"/>

2.  **JSON ツリーをナビゲートする**。

    ノードを展開し、データを選択する最も深いレベルを選択します。

    <img src="images/advanced-selection-json-tree.png" alt="Json Files Navigate Tree" class="responsive-img" width="85%"/>

3.  **ツリー要素とフィールドを選択する**。
    子の選択を有効にするには、ツリー要素 (オブジェクト **[ ]** または配列 **{ }**) を選択する必要があります。

    |                                                                             |                                                                                                                                           |
    | --------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------- |
    | <img src="images/unselect-elements-json-file.png" alt="Json Files Unselect Elements" class="responsive-img"/> | 1 つ以上の子の選択後、親要素 (オブジェクトと配列) の選択を解除し、データ構造から除外できます。 |


4.  (*オプション*) **テキスト フィールドを日付/時刻または数値に書式設定する**。

    フィールドを選択すると、Reveal はその値を読み取り、最適な形式を自動検出し、実行する操作を選択できるダイアログを表示します。

    <img src="images/different-format-options-json-advanced-selection.png" alt="Json Files Format Fields" class="responsive-img"/>

5.  **[テーブルの作成]** をクリック / タップする。

    カスタム データ構造を選択後、**[テーブルの作成]** ボタンをクリック / タップして、表示形式エディターを開きます。

    <img src="images/visualization-editor-json-file.png" alt="Using the data from json file to create visualization" class="responsive-img" width="85%"/>
