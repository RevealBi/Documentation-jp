## Google アナリティクス

Google アナリティクスは、ウェブで最も使用されているウェブ分析サービスの 1 つであり、ウェブサイトのトラフィックを追跡して報告します。さらに、Google は、iOS および Android アプリから使用状況データを収集するための SDK も提供しています。

### Google アナリティクス データソースの構成

1.  **ログイン**

    1.  データソースとして Google アナリティクスを選択すると、Google のログイン画面が表示されます。

    2.  ログイン情報を入力して [サインイン] をクリック/タップします。承認プロンプトが表示されます。[許可] をクリック/タップします。

2.  **アカウントを選択**

    複数の Google アナリティクス アカウントがある場合は、使用するアカウントを選択します。

    <img src="images/choose-ga-account.png" alt="Select a Google account to be used with Reveal's Google Analytics data source" width="80%"/>

    ログインすると、データソースを削除しない限り、他の表示形式の作成時に同じアカウントを使用できます。

3.  **プロパティを選択**

    使用する Google アナリティクス プロパティを選択します。

    <img src="images/choose-ga-property.png" alt="Select a Google property to be used with Reveal's Google Analytics data source" width="80%"/>

    Google アナリティクスでは、**プロパティ**はウェブサイト、モバイル アプリ、ブログなどです。

4.  **データベース キューブを選択**

    使用するデータ キューブを選択します。

    <img src="images/choose-ga-datacube.png" alt="Select a data cube to be used with Reveal's Google Analytics data source" width="80%"/>

    このダイアログでは、データの更新間隔を次のように設定できます:

      - 常に

      - 1 時間に 1 回

      - 1 日に 1 回

      - 週に １ 回

資格情報が確認されると、Reveal は表示形式エディターに移動します。

### 表示形式エディターでの作業

Google Analytics からの情報でダッシュボードを作成する場合、以下のスクリーンショットのようにフィールドが異なって体系化されます。

<img src="images/ga-visualizationeditor.png" alt="Visualization Editor showing a Google Analytics data cube" width="80%"/>

左側に「フィールド」の見出しはありません。代わりに、クエリ フィールドに 2 つのセクションがあります。

1.  **ディメンション** (ピンク色の側面の立方体アイコンで表示): ディメンションはデータの属性です。たとえば、_Gender_ ディメンション (_Audience_ キューブの下) は、Web サイトのユーザーの性別を示します。

2.  **メジャー** ([123] アイコンで表示): メジャーは数値データで構成されます。たとえば、_AdX Clicks_ メジャーは、サイトで AdX 広告がクリックされた回数です。

詳細については、Google Analytics の記事をご覧ください: [ディメンションと指標](https://support.google.com/analytics/answer/1033861?hl=ja)。

>[!NOTE] 
> 一部のディメンションとメジャーは併用できません。有効なディメンションとメジャーの組み合わせのリストについては、Google Developer　ウェブサイトの [Dimensions ＆ Metrics Explorer (英語)](https://ga-dev-tools.appspot.com/dimensions-metrics-explorer/)を参照してください。

#### データ フィルター

Reveal で Google Analytics データソースを使用する場合、2 つのデータ フィルターがあります。

* **セグメント** フィルター。**セグメント フィルター** はあらかじめ定義されています。**システム** セグメントは Google によって定義し、**カスタム** セグメントは Google Analytics のウェブサイトのユーザーによって定義します。
データをフィルターするセグメントは 1 つのみ選択できます。
* **日付範囲**。データをフィルターするには、カレンダーで特定の日付範囲を選択します。右上の矢印をクリックして、日付範囲プリセットの 1 つを選択することもできます。

  <img src="images/ga-data-source-date-range-preset.png" alt="Date Range dialog" width="80%"/>

  >[!NOTE] デフォルトの日付範囲は「過去 30 日間」です。つまり、今日を含む過去 30 日間のデータが取得されます。


#### Google アナリティクスの目標を使用する

Google アナリティクスで定義された*目標*を*表示形式エディター*で使用できます。*目標*は、**ディメンション**と**メジャー**の両方のデータ型のメトリックの一部としてリストされます。

<img src="images/goals-google-analytics-2-option.png" alt="goals google analytics 2 option" width="80%"/>

上記の例でわかるように、Reveal での Google アナリティクスの*目標*のタイトルには、次の 1 つ以上が含まれています:

  - 1 から 20 までの**数値 ID**。

  - 最初の**ラベル** - これは、特定の目標に設定した目標の名前です。例えば、*目標 19* の*ダウンロード完了*。

  - 最後の目標**タイプ** - 例えば、*完了*、*放棄されたファネル*など。

目標の詳細については、Google アナリティクスの[ヘルプ ページ](https://support.google.com/analytics/answer/1012040?hl=en)をご覧ください。

### データソースの制限

現在、Google Analytics データで[ダッシュボード フィルター](~/jp/filters/dashboard-filters.html)を作成することはできません。
