# リリース ノート

以下は、Reveal の新機能および追加予定のアップデートです。

<style type="text/css">
.tg  {border-collapse:collapse;border-spacing:0;}
.tg td{font-family:Arial, sans-serif;font-size:14px;padding:10px 5px;border-style:solid;border-width:1px;overflow:hidden;word-break:normal;border-color:black;}
.tg th{font-family:Arial, sans-serif;font-size:14px;font-weight:normal;padding:10px 5px;border-style:solid;border-width:1px;overflow:hidden;word-break:normal;border-color:black;}
.tg .tg-cly1{text-align:left;vertical-align:middle}
.tg .tg-0lax{text-align:left;vertical-align:top;column-width: 22rem;}
</style>
<table class="tg">
    <tr>
    <th class="tg-cly1"><span style="font-weight:bold">日付</span></th>
    <th class="tg-cly1"><span style="font-weight:bold">バージョン</span></th>
    <th class="tg-cly1"><span style="font-weight:bold">説明</span></th>
    </tr>
   <tr>
        <td class="tg-0lax" rowspan="4">9 月 2021 年</td>
        <td class="tg-0lax" rowspan="4"> 1.0.20 <br> [1.0.29 iOS]</td>
        <td class="tg-cly1">[公開バグ修正] ReportPlus のインポートされたダッシュボードのコンボ チャートに関する問題<br>
        ReportPlus からダッシュボードをインポートすると、非表示フィールドを含むコンボ チャートの視覚化が期待どおりに機能しませんでした。
        </td>
    </tr>
    <tr>
        <td class="tg-cly1">[公開バグ修正] ReportPlus のインポートされたダッシュボードの SharePoint 資格情報に関する問題<br>
        ReportPlus からダッシュボードをインポートすると、SharePoint オンプレミスの資格情報が期待どおりに機能しませんでした。
        </td>
    </tr>
    <tr>
        <td class="tg-cly1">[公開バグ修正] ダッシュボード フィルターのデータ ソースの変更の問題<br>
        ダッシュボード フィルターのデータ ソースを変更すると、ダッシュボードの最初のフィルターが変更されたフィルターに置き換えられていました。
        </td>
    </tr>
    <tr>
        <td class="tg-cly1">[公開バグ修正] MS Analysis Services ダッシュボードのリンクの問題<br>
        Microsoft Analysis Services からデータを取得する表示形式を含むダッシュボードをリンクできるようになり、問題が発生しなくなりました。
        </td>
    </tr>
    <tr>
        <td class="tg-0lax" rowspan="2">6 月 2021 年</td>
        <td class="tg-0lax" rowspan="2"> 1.0.20 <br> [1.0.28 iOS]</td>
        <td class="tg-cly1">[公開バグ修正] 計算フィールド フィルターがサーバー上のデータ プロセスで機能しない問題<br>
        データのサーバー側集計を有効にすると、フィルターとして使用される計算フィールドが期待どおりにデータをフィルタリングしていなかった問題。
        </td>
    </tr>
    <tr>
        <td class="tg-cly1">[公開バグ修正] ダッシュボード フィルターに関する Google アナリティクスの問題<br>
        Google アナリティクス データ ソースからデータを取得するときに、ダッシュボード フィルターを作成できなかった問題。
        </td>
    </tr>
    <tr>
        <td class="tg-0lax" rowspan="5">5 月 2021 年</td>
        <td class="tg-0lax" rowspan="5"> 1.0.19 <br> [1.0.26 iOS]</td>
        <td class="tg-cly1">SalesForce バケット フィールドが Reveal でサポートされるようになりました!<br>
        Reveal に SalesForce バケット フィールドを追加して、複数のカテゴリ (バケットと呼ばれます) を操作できます。
        </td>
    </tr>
    <tr>
        <td class="tg-cly1">時系列軸ラベルをさらに改善しました。<br>
            表示形式のサイズが変更されると、チャート軸のラベルは、利用可能なスペースに基づいて間隔をあけて調整します。
        </td>
    </tr>
    <tr>
        <td class="tg-cly1">[公開バグ修正] 画像の表示形式の描画が機能しない問題がありました。 <br>
            画像の表示形式を使用すると、画像が描画されないことがあり、ダッシュボードを更新する必要がありました。
        </td>
    </tr>
    <tr>
        <td class="tg-cly1">[公開バグ修正] グリッド可視化の DateTime 列に構成の問題がありました。<br>
            Reveal は、ddd-dd (Wed-21)、ddd-mmm-yy (Wed-Sep-21) の 2 つの新しい日付形式をサポートするようになりました。
        </td>
    </tr>
    <tr>
        <td class="tg-cly1">日付形式をさらに増加しました。<br>
            グリッド可視化で、DateTime 形式の列は、時間形式の値を表示するように適切に構成できませんでした。
        </td>
    </tr>
    <tr>
        <td class="tg-0lax" rowspan="1">3 月 2021 年</td>
        <td class="tg-0lax" rowspan="1">1.0.18 <br> [1.0.25 iOS]</td>
        <td class="tg-cly1">時系列の機能強化<br>
        - 高さと幅が小さい表示形式では、ラベル全体を含め (可能な場合)、それ以外の場合はラベルを含めない。といったより良い方法でラベルを表示するようになりました。<br>
        - iOS と Android で十字線が表示されるまでに必要な長押し時間が短縮されました。
        </td>
    </tr>
    <tr>
        <td class="tg-0lax" rowspan="4">3 月 2021 年</td>
        <td class="tg-0lax" rowspan="4"> 1.0.18 <br> [1.0.24 iOS]</td>
        <td class="tg-cly1">新しい時系列チャート<br>
        新しい時系列チャートを使用すると、より多くのインサイトを得て、傾向を一目で検出できます。これにより、時間の経過に伴う開発を簡単に観察できます。
        </td>
    </tr>
    <tr>
        <td class="tg-cly1">[公開バグ修正] iOS で総計が間違った値を表示する問題<br>
            iOS プラットフォームでは、ピボット テーブルに総計の値が正しく表示されませんでした。
        </td>
    </tr>
    <tr>
        <td class="tg-cly1">[公開バグ修正] iOS で SQL Server の異種クエリが機能しない問題<br>
            iOS プラットフォームでは、SQL サーバーの異種クエリが期待どおりに機能していませんでした。
        </td>
    </tr>
    <tr>
        <td class="tg-cly1">[公開バグ修正] iOS でエラーを示す無限大記号を含む SQL Server の結果の問題<br>
            iOS プラットフォームでは、無限大記号を含む SQL Server の結果にエラーが表示されていました。
        </td>
    </tr>
    <tr>
        <td class="tg-0lax" rowspan="5">2 月 2021 年</td>
        <td class="tg-0lax" rowspan="5"> 1.0.17 <br> [1.0.23 iOS]</td>
        <td class="tg-cly1"><span style="font-style:italic">新しい Snowflake データ ソース</span><br>
        Reveal で Snowflake からデータにアクセスできるようになりました。
        </td>
    </tr>
    <tr>
        <td class="tg-cly1"><span style="font-style:italic">新しい日付階層</span><br>
    日付フィールドは、ピボット エディターに階層 (年、四半期、月、日、分) を自動的に表示するようになりました。
        </td>
    </tr>
    <tr>
        <td class="tg-cly1"><span style="font-style:italic">散布マップの拡張機能</span><br>
            新しいズーム コントロールが散布マップに追加され、ズーム レベルをより適切に調整し、必要に応じてリセットできるようになりました。
        </td>
    </tr>
    <tr>
        <td class="tg-cly1"><span style="font-style:italic">新しい UI ナビゲーション</span><br>
            メイン ナビゲーションが変更され、UI と組織が異なるため、ナビゲーション エクスペリエンスが向上しました。
        </td>
    </tr>
    <tr>
        <td class="tg-cly1"><span style="font-style:italic">[公開バグ修正] 日本語にローカライズされていない単語。</span><br>
            「Others」は、日本語の「その他」にローカライズされていませんでした。
        </td>
    </tr>
    <tr>
    <td class="tg-0lax" rowspan="4">12 月 2020 年</td>
    <td class="tg-0lax" rowspan="4"> 1.0.16 <br> [1.0.20 iOS] </td>
<tr>
    <td class="tg-cly1">[公開バグ修正] カテゴリ フィールド ラベルが表示されない問題</span><br>カテゴリ チャートでは、ツールチップにフィールド ラベルではなく、カテゴリの元のフィールド名が表示されていました。
</td>
  </tr>
<tr>
  <td class="tg-cly1">
  [公開バグ修正] ドリルダウン ブレッドクラムの日付が誤って表示される問題</span><br>
  日付フィールドをドリルダウンすると、ブレッドクラムに値が正しく表示されませんでした。これで、ブレッドクラムはドリルダウン レベルに関する明確な情報を提供することになりました。
  </td>
</tr>
<tr>
  <td class="tg-cly1">
  [公開バグ修正] ホバー ツールチップと十字線がデフォルトで表示されない問題</span><br>
  ダッシュボード ビュー モードでは、ユーザーが有効にするまで、ホバー ツールチップと十字線は表示されませんでした。現在、これらはデフォルトで有効になっています。
  </td>
</tr>
  <tr>
        <td class="tg-0lax" rowspan="3">10 月 2020 年</td>
        <td class="tg-0lax" rowspan="3">1.0.15 <br> [1.0.17 iOS] </td>
    <td class="tg-cly1">新しい Amazon Athena データ ソース</span><br>Amazon Athena に接続して Amazon S3 からデータをクエリし、それを使用して Reveal で表示形式を構築できるようになりました。
</td>
<tr>
    <td class="tg-cly1">新しい Amazon S3 データ ソース</span><br>Reveal で Amazon S3 から直接データにアクセスします。
</td>
  </tr>
<tr>
  <td class="tg-cly1">
  新しい散布マップの表示形式 </span><br>
  地理空間データからより多くのインサイトを得て、配布、空間パターン、および外れ値を表示します。ズームしてより詳細なビューを表示し、背景として使用する多数のマッピング サービスに接続することもできます。
  </td>
</tr>
   <tr>
        <td class="tg-0lax" rowspan="3">9 月 2020 年</td>
        <td class="tg-0lax" rowspan="3">1.0.14</td>
    <td class="tg-cly1">新規の Amazon Redshift データ ソース</span><br>Amazon Redshift クラウド データ ウェアハウスのデータを使用して、新しいインサイトを得ることができます。
</td>
<tr>
    <td class="tg-cly1">新しい Marketo データ ソース</span><br>Marketo マーケティング プラットフォームのアカウントに接続し、データを Reveal で使用します。
</td>
  </tr>
  <tr>
    <td class="tg-cly1">サーバーでデータを処理</span><br>MS SQL、MySQL、Postgres データ ソースからのデータをサーバー側で集計することが可能です。
</td>
  </tr>
  <tr>
        <td class="tg-0lax" rowspan="7">7 月 2020 年</td>
        <td class="tg-0lax" rowspan="7">1.0.13</td>
    <td class="tg-cly1">新しい階級区分図</span><br>階級区分図の表示形式により、美しい主題図を作成できます。地理空間データを驚くほどわかりやすく表示できます。色によって、マップ上のパターン、トレンド、および異常をすばやく発見できます。
</td>
  <tr>
    <td class="tg-cly1">新規の Quickbooks データ ソース</span><br>Quickbooks アカウントに接続し、エンティティを使用して Reveal でデータ分析を実行します。
</td>
  </tr>
  <tr>
    <td class="tg-cly1">新しい Hubspot データ ソース</span><br>Hubspot オブジェクトを使用して、Reveal でダッシュボードを作成できるようになりました。
</td>
  </tr>
  <tr>
    <td class="tg-cly1">表示形式エディターの新しい検索機能</span><br>表示形式エディターで 10 を超えるデータ フィールドを含むデータセットを読み込むと、この新しい検索が有効になります。
</td>
  </tr>
  <tr>
    <td class="tg-cly1">Salesforce データ ソースの機能強化</span><br>Reveal で Salesforce レポートを使用できます。
</td>
  </tr>
  <tr>
    <td class="tg-cly1">SharePoint データ ソースの機能強化</span><br>SharePoint ライブラリのすべてのファイルについて収集されたメタデータ (名前、タイプなど) を Reveal のデータ ソースとして使用できるようになりました。
</td>
  </tr>
  <tr>
    <td class="tg-cly1">PostgreSQL データ ソースの機能強化</span><br>PostgreSQL データベースの関数を使用して、ダッシュボードを作成できるようになりました。
</td>
  </tr>
   <tr>
        <td class="tg-0lax" rowspan="2">5 月 2020 年</td>
        <td class="tg-0lax" rowspan="2">1.0.12</td>
    <td class="tg-cly1">新しい Microsoft Azure Analysis Services データ ソース</span><br>この新しいデータ ソースにより、Azure Analysis Services のデータ モデルを使用してダッシュボードを作成できます。
</td>
<tr>
    <td class="tg-cly1">Google スプレッドシート ファイルの新しいアイコン</span><br>Google スプレッドシート ファイルのアイコンを変更しました。
</td>
  </tr>
  <tr>
        <td class="tg-0lax" rowspan="5">5 月 2020 年</td>
        <td class="tg-0lax" rowspan="5">1.0.12</td>
    <td class="tg-cly1">新規の TreeMap の表示形式</span><br>この新しい表示形式タイプを使用して、大きな階層をネストされた四角形の集合で表示できます。四角形のサイズは、さまざまなメトリック間の部分と全体の関係を示し、同様のデータ間のパターンと関係を識別します。
</td>
  </tr>
  <tr>
    <td class="tg-cly1">Excel へエクスポート機能拡張</span><br>エクスポートする際に複数の表示形式タイプをスプレッドシートに追加できます。散布図、バブル チャート、スパークライン チャートが利用できるようになりました。
</td>
  </tr>
  <tr>
    <td class="tg-cly1">UI/UX の改善</span><br>表示形式、ダッシュボード、新しいデータ ソース ダイアログなどのユーザーエクスペリエンスを向上するために、小さな変更が追加されました。
</td>
  </tr>
  <tr>
    <td class="tg-cly1">Google ドライブで共有ドライブのサポートを追加</span><br>G Suite Business アカウントをお持ちの場合、共有ドライブ データにアクセスし、それを使用して Reveal で表示形式を構築できます。
</td>
  </tr>
  <tr>
    <td class="tg-cly1">Google 認証プロセスの改善</span><br>セキュリティを最大にするために、Reveal Desktop は Google アカウントにアクセスする際にシステム (デフォルト) ブラウザーを表示します。
</td>
  </tr>
  <tr>
        <td class="tg-0lax" rowspan="5">4 月 2020 年</td>
        <td class="tg-0lax" rowspan="5">1.0.10/11</td>
    <td class="tg-cly1">BigQuery Machine Learning との統合</span><br>Reveal のデータ ソースで BigQuery 機械学習モデルを使用できるようになりました。</td>
  </tr>
  <tr>
    <td class="tg-cly1">新規の Salesforce データ ソース</span><br>この新しいデータ ソースは、Salesforce のオブジェクトのデータを使用してダッシュボードを作成できます。</td>
  </tr>
  <tr>
    <td class="tg-cly1">新規の Google アナリティクスの目標</span><br>Reveal は、Google アナリティクスで定義された目標の指標を表示し、データを詳細に分析します。</td>
  </tr>
  <tr>
    <td class="tg-cly1">ダッシュボードの新しいスタイル設定</span><br>2 つのダッシュボード パレットから選択できます。追加予定Reveal はまったく新しいダッシュボード スタイル設定の準備をしています。</td>
  </tr>
  <tr>
    <td class="tg-cly1">Excel へエクスポート機能拡張</span><br>エクスポートの際、Reveal の表示形式をスプレッドシートに含めることができます。</td>
  </tr>
  <tr>
        <td class="tg-0lax" rowspan="10">2 月 2020 年</td>
        <td class="tg-0lax" rowspan="10">1.0.9</td>
    <td class="tg-cly1">新しい分析機能</span><br>既存のデータセットの統計分析を処理および実行できるようになりました。つまり、データをより細かく分析し、履歴データに基づいてパフォーマンスを予測することもできます。</td>
  </tr>
  <tr>
    <td class="tg-cly1">Azure Machine Learning モデルとの新たな統合</span><br>Reveal のデータを使用して Azure のモデルを評価し、その結果を可視フィールドとして使用できます。</td>
  </tr>
  <tr>
    <td class="tg-cly1">新規の Google Analytics データ ソース</span><br>この新しいデータ ソースは、Google Analytics の情報を使用してダッシュボードを作成できます。</td>
  </tr>
  <tr>
    <td class="tg-cly1">新規の Google BigQuery データ ソース</span><br>Reveal 内で Google の BigQuery ウェブサービスに接続し、大規模なデータセットをパフォーマンスを低下せずに処理できるようになりました。</td>
  </tr>
  <tr>
    <td class="tg-cly1">新しい Azure Synapse と Azure SQL データ ソース</span><br>Azure 分析サービスと SQL データベースに接続して、ビッグデータと高度なクエリ処理機能を操作します。</td>
  </tr>
  <tr>
    <td class="tg-cly1">新しい Microsoft Reporting Services (SSRS) データ ソース</span><br>表示形式に既存の SSRS レポートを使用できるようになりました。それらを PDF ファイルとして埋め込み、またはレポートのデータを取得して独自の表示形式を作成できます。</td>
  </tr>
  <tr>
    <td class="tg-cly1">フォルダーやチームのダッシュボード管理</span><br>フォルダーまたはチーム間でダッシュボードを移動およびコピーできるようになりました。</td>
  </tr>
  <tr>
    <td class="tg-cly1">Excel および PowerPoint へのエクスポート機能拡張</span><br>新しい UI では、データをスライドやスプレッドシートにエクスポートする方法をカスタマイズできます。</td>
  </tr>
  <tr>
    <td class="tg-cly1">PDF エクスポート</span><br>ダッシュボードを PDF 形式にエクスポートできるようになりました。</td>
  </tr>
  <tr>
    <td class="tg-cly1">ホバー ツールチップと十字線の追加の新しいデザイン</span><br>ツールチップが小さくなり、ポインターは削除されました。さらに、ツールチップにコンテキストを提供するために十字線が表示されるようになりました。</td>
  </tr>
  <tr>
        <td class="tg-0lax" rowspan="5">11 月 2019 年</td>
        <td class="tg-0lax" rowspan="5">1.0.8</td>
    <td class="tg-cly1">円およびドーナツ型チャートの凡例に、値 0 の要素を表示できるようになりました。</span><br>円とドーナツの表示形式の凡例に値 0 の要素を表示するオプションが追加されました。これにより、ラベルに選択されたフィールドのすべてのデータを見ることができますが、値 0 のデータはチャート自体には表示されません。</td>
  </tr>
  <tr>
    <td class="tg-cly1">サポートされる色合い</span><br>Reveal は、表示形式エディター パレットに 8 つの既存の色の陰影を自動的に生成できるようになりました。これにより、大きな値のセットを含むチャートで、分離/比較に必要なさまざまな色を表示できます。</td>
  </tr>
  <tr>
    <td class="tg-cly1">[バグ修正] Windows プラットフォームのローカリゼーション</span><br>Windows プラットフォームで設定された表示言語は検出されましたが、Reveal に適用されない問題。</td>
  </tr>
  <tr>
    <td class="tg-cly1">[バグ修正] 日本語の発音記号</span><br>日本語の発音記号が誤って表示される問題。</td>
  </tr>
  <tr>
    <td class="tg-cly1">[バグ修正] 開始パラメーターの検索関数</span><br>計算フィールドで使用される検索機能で開始位置パラメーターがオプションと見なされない問題。</td>
  </tr>
  <tr>
        <td class="tg-0lax" rowspan="6">11 月 2019 年</td>
        <td class="tg-0lax" rowspan="6">1.0.8</td>
    <td class="tg-cly1">Excel および PowerPoint へのエクスポート</span><br>ダッシュボードの表示形式を PowerPoint プレゼンテーションのスライドとしてエクスポートできるようになりました。さらに、ダッシュボードで使用されているデータを Excel 形式にエクスポートすることもできます。</td>
  </tr>
  <tr>
    <td class="tg-cly1">散布図/バブルの表示形式</span><br>これらの 2 つの新しい表示形式は非常によく似てますが、散布図の 2 つの変数またはバブル チャートの 3 つの変数間の関係を簡単に示すことができます。</td>
  </tr>
  <tr>
    <td class="tg-cly1">コンボ チャートを使用した表示形式の改善</span><br>前面に表示されるチャートに透明度のレベルが追加されました。さらに、どのチャートを前面または背面に表示するかを並べ替えるようになりました。</td>
  </tr>
  <tr>
    <td class="tg-cly1">テキスト ボックス表示形式</span><br>この新しい表示形式により、ダッシュボードにテキストで概要を追加できるようになりました。テキスト本文とオプションのタイトルで構成されます。</td>
  </tr>
  <tr>
    <td class="tg-cly1">UI ナビゲーションの変更</span><br>メイン ナビゲーションが変更され、UI と組織が異なるため、ナビゲーション エクスペリエンスが向上しました。</td>
  </tr>
  <tr>
    <td class="tg-cly1">チャート凡例の機能拡張</span>サイズ変更やレイアウト時のビジュアルが向上し、バッジではシリーズ タイプをより強調するように改善されました。</td>
  </tr>
  <tr>
        <td class="tg-0lax" rowspan="6">9 月 2019 年</td>
        <td class="tg-0lax" rowspan="6">1.0.7</td>
    <td class="cly1">ダッシュボード レベルの操作の改善:</span><br>ダッシュボード最小化時に表示形式をインタラクティブに操作できるようになりました。ズーム、スクロール、ドリル ダウン、他のダッシュボードへのリンク、およびダッシュボードの表示形式を最大化せずにチャート ポイントの詳細 (ツールチップ) を表示します。</td>
  </tr>
  <tr>
    <td class="cly1">クラウド ファイル共有の改善</span><br>Google ドライブ、OneDrive、Dropbox からデータ ソース ファイルへのアクセスを有効にして復元できるようになりました。共有されたダッシュボードに使用されるクラウド ファイルへのアクセスを要求します。</td>
  </tr>
  <tr>
    <td class="cly1">新しいコンボチャートの表示形式</span><br>新しい表示形式タイプを追加しました。コンボ (組み合わせ) チャート ビジュアリゼーション (2 つの Y 軸チャート) を使用して表示形式を構築できるようになりました。</td>
  </tr>
  <tr>
    <td class="cly1">新しいツールチップ ポップアップ オプションに合計を追加</span><br>ツールチップ ポップアップで合計値を有効にできるようになりました。</td>
  </tr>
  <tr>
    <td class="cly1">[バグ修正] </span>SQL Server and Azure connections</span><br>SQL Server と Azure の接続</span><br>Azure の SQL Server データベース接続時の問題。</td>
  </tr>
  <tr>
    <td class="cly1">[バグ修正]</span> クラウド プロバイダーからの Excel ヘッダー:</span><br>最初の行に使用されるラベル設定が、クラウド プロバイダー (Google ドライブ、Dropbox、OneDrive) でホストされる Excel ファイルで表示されない問題。</td>
  </tr>
  <tr>
        <td class="tg-0lax" rowspan="4">7 月 2019 年</td>
        <td class="tg-0lax" rowspan="4">1.0.6</td>
    <td class="tg-cly1">ローカライズ</span><br>Reveal は現在ドイツ語、スペイン語、フランス語、イタリア語、日本語、韓国語、マレー語、オランダ語、ポルトガル語、ロシア語、中国語 (簡体字および繁体字) にローカライズされています。</td>
  </tr>
  <tr>
    <td class="tg-cly1">Google または Microsoft アカウントに必要な権限が少ない</span><br>アプリケーションにサインインすると、Reveal は個人情報へのアクセスのみを要求するようになります。その後、Googleドライブまたは OneDrive を使用する場合、必要に応じて追加の権限が要求されます。</td>
  </tr>
  <tr>
    <td class="tg-cly1">ダッシュボードを共有してクラウド ストレージを操作するときの UX の向上</span><br>OneDrive、Google ドライブ、Dropbox アカウントのファイルからデータを取得するダッシュボードを共有するときのエクスペリエンスを改善しました。</td>
  </tr>
  <tr>
    <td class="tg-cly1">組織管理と権限管理</span><br>組織の管理者は、メンバーを招待し、組織内のユーザーに権限を設定できるようになりました。</td>
  </tr>
</table>
