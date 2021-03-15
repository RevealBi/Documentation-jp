## リリース ノート

以下は、Reveal SDK の各バージョンに含まれる新機能および拡張機能です。

<table>
    <colgroup>
        <col style="width: 10%" />
        <col style="width: 20%" />
        <col style="width: 70%" />
    </colgroup>
    <thead>
        <tr>
            <th>日付</th>
            <th>SDK バージョン</th>
            <th>説明</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td rowspan="4">3 月 2021 年</td>
            <td rowspan="4">1.0.1821</td>
            <td>[公開バグ修正] [SDK] SDK アプリが NRE 例外をスローすることがある問題。<br> ユーザーが操作せずに SDK アプリケーションを 90 分以上開いた場合、操作を実行すると例外がスローされていました。</td>
        </tr>
        <tr>
            <td>[公開バグ修正] iOS で総計が間違った値を表示する問題。<br>iOS プラットフォームでは、ピボット テーブルに総計の値が正しく表示されませんでした。</td>
        </tr>
        <tr>
            <td>[公開バグ修正] iOS で SQL Server の異種クエリが機能しない問題。<br>iOS プラットフォームでは、SQL サーバーの異種クエリが期待どおりに機能していませんでした。</td>
        </tr>
        <tr>
            <td>[公開バグ修正] iOS でエラーを示す無限大記号を含む SQL Server の結果の問題。<br>iOS プラットフォームでは、無限大記号を含む SQL Server の結果にエラーが表示されていました。</td>
        </tr>
        <tr>
            <td>2 月 2021 年</td>
            <td>1.0.1772</td>
            <td>[公開バグ修正] [SDK] packages.config で WPF NuGet パッケージのインストールが失敗する問題。<br>ホスト プロジェクトが packages.config を使用した場合、WPF NuGet パッケージのインストールが失敗していました。
            </td>
        </tr>
        <tr>
            <td rowspan="6">2 月 2021 年</td>
            <td rowspan="6">1.0.1763</td>
            <td>[公開バグ修正] [SDK] HasPendingChanges プロパティが正しく動作しない問題。<br> Desktop SDK では、ダッシュボードを変更して保存した後、HasPendingChanges プロパティが false に設定されていませんでした。</td>
        </tr>
        <tr>
            <td>[公開バグ修正] [SDK] カスタム フィルタリングが正しく動作しない問題。 <br>Desktop SDK では、カスタム クエリが正しくデータをフィルタリングしていませんでした。</td>
        </tr>
        <tr>
            <td>[公開バグ修正] [SDK] SQL Server テーブルを非表示にすると、ビューも非表示になる問題。<br>RVDataSourceItemsFilter を使用してすべてのテーブルを非表示にし、ビューのみを表示すると、[ビュー] タブも非表示になりました。</td>
        </tr>
        <tr>
            <td>[公開バグ修正] [SDK] AzureSQL データ プロバイダーがエラーを発生する問題。 <br>AzureSQL 接続を追加すると、エラー メッセージが表示されました。</td>
        </tr>
        <tr>
            <td>[公開バグ修正] [SDK] LocalizationProvider が設定されている場合に日付フィルターが表示されない問題。<br>LocalizationProvider が設定されている場合、表示形式エディターに日付フィルターの開始/終了は表示されません。</td>
        </tr>
        <tr>
            <td>[公開バグ修正] 日本語にローカライズされていない単語。<br>「Others」は、日本語の「その他」にローカライズされていませんでした。</td>
        </tr>
        <tr>
        <td rowspan="2">1 月 2021 年</td>
        <td rowspan="2">1.0.1712</td>
        <td>[公開バグ修正] [SDK] サーバー コンポーネントは Newtonsoft.Json シリアライザー に依存しています。<br> Reveal サーバー コンポーネントは、MVC アプリケーションのデフォルトの JSON シリアル化設定に依存していました。これで、ホスティング アプリは必要に応じて JSON シリアル化設定を構成できます。</td>
    </tr>
    <tr>
        <td>[公開バグ修正] [SDK] SQL Server フィルタリングが NVARCHAR 列で機能しない問題。<br>フィルタリングされた値にマルチバイト文字が含まれている場合、Microsoft SQL Server のフィルタリングが NVARCHAR 列に対して機能しませんでした。</td>
    </tr>
        <tr>
            <td rowspan="2">12 月 2020 年</td>
            <td rowspan="2">1.0.1669</td>
            <td>[公開バグ修正] [サーバーでデータを処理] で SDK ピボット階層フィルタリングが機能しない問題。<br>[サーバーでデータを処理] オプションがオンになっている場合、ピボット エディターでのドリルダウン階層はデータをフィルタリングしていなかった問題。</td>
        </tr>
        <tr>
            <td>[公開バグ修正] [サーバーでデータを処理] で SDK カスタム フィルタリングが機能しない問題。<br>[サーバーでデータを処理] オプションがオンになっている場合、カスタム クエリは正しい行数を返しなかった問題。</td>
        </tr>
        <tr>
            <td rowspan="4">12 月 2020 年</td>
            <td rowspan="4">1.0.1629</td>
            <td>JSON ファイルを使用してダッシュボードを保存/ロード<br>Reveal SDK を使用して、JSON ファイルからダッシュボードを保存/ロードできるようになりました。</td>
        </tr>
        <tr>
            <td>[公開バグ修正] カテゴリ フィールド ラベルが表示されない問題。<br>カテゴリ チャートでは、ツールチップにフィールド ラベルではなく、カテゴリの元のフィールド名が表示されていました。</td>
        </tr>
        <tr>
            <td>[公開バグ修正] ドリルダウン ブレッドクラムの日付が誤って表示される問題。<br>日付フィールドをドリルダウンすると、ブレッドクラムに値が正しく表示されませんでした。これで、ブレッドクラムはドリルダウン レベルに関する明確な情報を提供することになりました。</td>
        </tr>
        <tr>
            <td>[公開バグ修正] ホバー ツールチップと十字線がデフォルトで表示されない問題。<br>ダッシュボード ビュー モードでは、ユーザーが有効にするまで、ホバー ツールチップと十字線は表示されませんでした。現在、これらはデフォルトで有効になっています。</td>
        </tr>
        <tr>
            <td rowspan="5">9 月 2020 年</td>
            <td rowspan="5">1.0.1422</td>
            <td>Amazon Athena コネクター (ベータ版)<br>
            Amazon のサーバーレス インタラクティブな Athena クエリ サービスに接続できるようになりました。</td>
        </tr>
        <tr>
            <td>新しいビルド済みテーマ<br>4 つのビルド済みアプリ テーマを追加しました。いずれかを選択し、カスタマイズ可能な設定を使用して、表示形式およびダッシュボード エディターのルックアンドフィールをカスタマイズします。次のテーマから選択できます: 
            MountainLightTheme (Desktop) / $.ig.MountainLightTheme (Web);
            MountainDarkTheme (Desktop) / $.ig.MountainDarkTheme (Web);
            OceanLightTheme (Desktop) / $.ig.OceanLightTheme (Web);
            OceanDarkTheme (Desktop) / $.ig.OceanDarkTheme (Web)。
</td>
        </tr>
        <tr>
            <td>Marketo プロバイダーを利用できるようになりました。<br>Marketo マーケティング プラットフォームに接続し、データを Reveal で使用します。</td>
        </tr>
        <tr>
            <td>Amazon Redshift を利用できるようになりました。<br>Amazon Redshift クラウド データ ウェアハウスのデータを使用して、新しいインサイトを得ることができます。</td>
        </tr>
        <tr>
            <td>新しい「サーバーでデータを処理」機能<br>MS SQL、MySQL、Postgres データ ソースからのデータをサーバー側で集計することが可能です。</td>
        </tr>
        <tr>
            <td rowspan="6">7 月 2020 年</td>
            <td rowspan="6">1.0.1374</td>
            <td>チャートの軸範囲を設定する新しい API<br> 特定の表示形式のためにランタイムで軸範囲をプログラム的に変更できるようになりました。</td>
        </tr>
        <tr>
            <td>Salesforce データ ソースの機能強化<br>Reveal で Salesforce レポートを使用できます。</td>
        </tr>
        <tr>
            <td>新しい Quickbooks データ ソース<br>Quickbooks アカウントに接続し、エンティティを使用して Reveal でデータ分析を実行します。</td>
        </tr>
        <tr>
            <td>新しい Hubspot データ ソース<br>Hubspot に接続できます。</td>
        </tr>
        <tr>
            <td>Sharepoint リストとドキュメント ライブラリのサポート<br>SharePoint ライブラリのすべてのファイルについて収集されたメタデータ (名前、タイプなど) を Reveal のデータ ソースとして使用できるようになりました。</td>
        </tr>
        <tr>
            <td>新しい階級区分図<br>階級区分図の表示形式により、美しい主題図を作成できます。地理空間データを驚くほどわかりやすく表示できます。色によって、マップ上のパターン、トレンド、および異常をすばやく発見できます。</td>
        </tr>
        <tr>
            <td rowspan="2">5 月 2020 年</td>
            <td rowspan="2">1.0.1255</td>
            <td>新しい Azure Analysis Services データ ソース<br>この新しいデータ ソースにより、Azure Analysis Services のデータ モデルを使用してダッシュボードを作成できます。</td>
        </tr>
        <tr>
            <td>Google スプレッドシート ファイルの新しいアイコン<br>Google スプレッドシート ファイルのアイコンが変更されました。</td>
        </tr>
        <tr>
            <td rowspan="5">5 月 2020 年</td>
            <td rowspan="5">1.0.1222</td>
            <td>新しいホバー イベント API<br>
            この新しいイベントは、WPF では revealView.TooltipShowing、Web では .onTooltipShowing と呼ばれ、エンドユーザーが表示形式でシリーズをホバーするか、シリーズをクリックするたびに発生されます。</td>
        </tr>
        <tr>
            <td>新しい TreeMap 表示形式<br>この新しい表示形式タイプを使用して、大きな階層をネストされた四角形の集合で表示できます。四角形のサイズは、さまざまなメトリック間の部分と全体の関係を示し、同様のデータ間のパターンと関係を識別します。
</td>
        </tr>
        <tr>
            <td>Excel へエクスポート機能拡張<br>エクスポートする際に複数の表示形式タイプをスプレッドシートに追加できます。散布図、バブル チャート、スパークライン チャートが利用できるようになりました。</td>
        </tr>
        <tr>
            <td>UI/UX の改善<br>表示形式、ダッシュボード、新しいデータ ソース ダイアログなどのユーザーエクスペリエンスを向上するために、小さな変更が追加されました。</td>
        </tr>
        <tr>
            <td>Google ドライブで共有ドライブのサポートを追加<br>G Suite Business アカウントをお持ちの場合、共有ドライブ データにアクセスし、それを使用して Reveal で表示形式を構築できます。</td>
        </tr>
        <tr>
            <td>4 月 2020 年</td>
            <td>1.0.1136</td>
            <td>新しいカスタム テーマ<br>
            新しい RevealTheme (デスクトップ) / $.ig.RevealTheme (Web) クラスでカスタマイズ可能な設定の一部またはすべてを構成することにより、Reveal で独自のテーマを作成できるようになりました。</td>
        </tr>
        <tr>
            <td rowspan="3">2 月 2020 年</td>
            <td rowspan="3">1.0.981</td>
            <td>RevealSettings の新しいプロパティ<br>$.ig.RevealSettings にさまざまな機能を制御するための複数の新しいプロパティを追加しました。ShowExportToPDF、ShowExportToPowerpoint、ShowExportToExcel、ShowStatisticalFunctions、ShowDataBlending、ShowMachineLearningModelsIntegration、StartWithNewVisualization、InitialThemeName。</td>
        </tr>
        <tr>
            <td>アクセント色のサポート<br>SetAccentColor メソッドが $.ig.RevealView に追加されました。</td>
        </tr>
        <tr>
            <td>Trigger プロパティが DataSourceRequested イベントに追加されました。<br>DataSourcesRequestedTriggerType 型の Trigger プロパティを DataSourcesRequested イベント引数に追加しました。このイベントのユーザーは、DataSourcesRequested の目的について詳細なコンテキストを取得できます。</td>
        </tr>
            <td>11 月 2019 年</td>
            <td>1.0.825</td>
            <td>画像エクスポート機能が利用できるようになりました。<br>サーバー側の画像エクスポート (プログラム上およびユーザー操作の両方により) が再び有効になりました。修正の詳細については、以下のトピックを参照してください。<a
                href="../setup-configuration/setup-configuration-web.html#server-side-image-export">サーバー側画像生成の有効化</a></td>
        <tr>
        </tr>
            <td rowspan="4">9 月 2019 年</td>
            <td rowspan="4">1.0.80x</td>
            <td>Reveal Desktop SDK のローカリゼーション サービス<br>さまざまなダッシュボード要素のタイトルおよびラベルをローカライズすることができます。ローカライゼーション サービスでは、数値および非集計の日付フィールドの書式設定を変更することもできます。</td>
        <tr>
        <tr>
            <td>Reveal Desktop SDK の書式設定サービス<br>数値データ、集計および非集計の日付フィールドを好みに合わせて書式設定できます。デフォルトの書式設定を無視して、ダッシュボード データを書式設定します。</td>
        </tr>
        <tr>
            <td>セットアップと構成の変更 (Server SDK)<br>Reveal Server SDK には、.NET Core 2.2+ および .NET Framework 4.6.1+ ASP MVC アプリケーション プロジェクトがサポートされます。また、NuGet パッケージ マネージャーのみを使用すると、アセンブリを参照し、依存関係パッケージをインストールします。</td>
        </tr>        
        </tr>
            <td rowspan="4">9 月 2019 年</td>
            <td rowspan="4">1.0.70x</td>
            <td>ステップバイステップ ガイド<br>Reveal SDK の前提条件、セットアップや構成に必要な手順全般に関するトピックを追加。</td>
        <tr>
        <tr>
            <td>ウィジェット データ ソースの変更<br>エンドユーザーによってウィジェットのデータ ソースを変更する機能を有効または無効にできます。編集モードで [可視化データ] 画面を開いた際に、UI の [データ ソースの変更] ボタンを表示または非表示にできます</td>
        </tr>
        <tr>
            <td>ダッシュボード テーマの変更<br>エンドユーザーによってダッシュボードのテーマを変更する機能を有効または無効にできます。ダッシュボードの編集モードに入る際に、使用可能なテーマを表示するためのボタンを表示または非表示にできます。</td>
        </tr>        
    </tbody>
</table>
