---
title: Slingshot で Google BigQuery データ ソースを使用する方法
_description: Google BigQuery データ ソースを設定して使用する方法と、速度低下することなく巨大なデータセットを使用する方法を説明します。
_language: ja
---

# Google BigQuery

Google BigQuery データ ソースは、Reveal 内でビッグ データを処理する際の速度を大幅に向上させます。これにより、速度低下することなく、何百万ものレコードを含むデータセットを表示形式に使用できます。

## Google BigQuery への接続

Google BigQuery を選択すると、**Google アカウント**に接続するように求められます。

Google アカウントを追加すると、BigQuery データセットにアクセスできるようになります。それらを表示形式に使用するには:

1.  **[データ ソースの作成]** ダイアログで**プロジェクトを選択します**。

    <img src="images/select-project-bigquery.png" alt="Select a project in the New Data Source dialog" class="responsive-img"/>

    >[!NOTE]
    >BigQuery の一般公開データセットを使ったデモ プロジェクト: 上のスクリーンショットの 2 つの公開 データ プロジェクトは、Reveal チームによって構成されたデモ プロジェクトです。BigQuery データセットを持たないユーザーは表示形式エディターでこのデータ ソースを操作して、ビッグ データがどのように迅速に処理されているかを確認できます。


2.  データ セットの横にある空の円をマークして、**データセットを選択します**。

    <img src="images/select-dataset-bigquery.png" alt="Select a dataset dialog" class="responsive-img"/>

3.  データセットから**表を選択します**。右側の*目のアイコン*を使用して、データをプレビューします。

    <img src="images/select-table-bigquery.png" alt="Select a table dialog" class="responsive-img"/>

これで、Google BigQuery から取得したデータを使用して表示形式の構築を開始できる、*表示形式エディター*に移動します。

## 表示形式エディターでの制限事項

Reveal でビッグ データを操作する場合、数百万のレコードを持つデータ ソースを処理するための特定のアプローチにより、表示形式エディターにはいくつかの制限があります。

### 計算フィールドで使用できる関数の制限

現在、BigQuery のデータを使用する*計算フィールド*で、使用できる**関数**の数は限られています。

- [日付](~/jp/data-visualizations/fields/calculated-fields/date.html) - date; time.

- [論理](~/jp/data-visualizations/fields/calculated-fields/logic.html) - false; true; if; not.

- [数学](~/jp/data-visualizations/fields/calculated-fields/math.html) - abs; exp; log; log10; mod; rand; sign; sqrt; trunc.

- [文字列](~/jp/data-visualizations/fields/calculated-fields/string.html) - find; len; trim; lower; mid; upper.

### データ ブレンディングの制限

現在、Google BigQuery データ ソースからのデータを使用する場合、データ ブレンディング ([データ ソースを 1 つの表示形式に統合](~/jp/datasources/data-blending.html)) は**使用できません**。
