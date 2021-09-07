# リリース ノート

以下は、Reveal SDK の各バージョンに含まれる新機能および拡張機能です。

<table>
    <colgroup>
        <col style="width: 15%" />
        <col style="width: 15%" />
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
            <td rowspan="2">9 月 2021 年</td>
            <td rowspan="2">1.0.2013</td>
            <td>[公開バグ修正] Calculated field export to excel resulting in empty cells<br>
            When exporting to excel a calculated field doing division by zero, the result included empty cells.
            </td>
        </tr>
        <tr>
            <td>[公開バグ修正] Data blending with custom queries and server-side processing issues<br>
            When turning on “Process Data On Server” in Web .NET and performing a custom query, data blending was not working as expected.
            </td>
        </tr>
        <tr>
            <td rowspan="3">9 月 2021 年</td>
            <td rowspan="3">1.0.2012</td>
            <td>[公開バグ修正] [SDK] Decimal point hidden when Sparkline chart exceeds 100%<br>
            In the Web SDK, the property canSaveAs was not being honored if it was changed after a dashboard is set.
            </td>
        </tr>
        <tr>
            <td>[公開バグ修正] [SDK] Small window sizes render Text chart unreadable<br>
            In both Web and Desktop, the Text Chart font becomes unreadable when the window’s size is small.
            </td>
        </tr>
        <tr>
            <td>[公開バグ修正] [SDK] Issues getting the list of date formats<br> When getting a list of date formats for a field editor in the Desktop SDK, you can now use <i>RVBaseFormattingService</i> with aggregated dates.
            </td>
        </tr>
        <tr>
            <td>8 月 2021 年</td>
            <td>1.0.2008</td>
            <td>[公開バグ修正] [SDK] Saving dashboard as a stream has issues<br> When saving dashboards as a stream, in some specific cases <i>dashboard.Serialize.Async()</i> was returning null.</td>
        </tr>
       <tr>
            <td rowspan="6">6 月 2021 年</td>
            <td rowspan="6">1.0.2005</td>
            <td>散布図が OpenStreetMap をサポートするようになりました!<br>
            デスクトップ (WPF) および Web クライアント (JS) で OpenStreetMap 画像タイルを構成して使用できるようになりました。
            </td>
        </tr>
        <tr>
            <td>新しいサムネイル コンポーネント!<br>
            <i>RevealDashboardThumbnailView<i> を使用してダッシュボードのサムネイルを描画できるようになりました。
            </td>
        </tr>
        <tr>
            <td>Web クライアントからサーバー側のデータ ソースへの資格情報<br>
            新しいタイプの資格情報 <i>RVHeadersDataSourceCredentials<i> を使用すると、認証ヘッダーとクッキーを REST および Web リソースのデータ ソースに送信できます。詳細については、GitHub で次の<a href="https://github.com/RevealBi/sdk-samples-aspnetcore/tree/main/Cookies-Auth">サンプル</a>をご覧ください。
            </td>
        </tr>
        <tr>
            <td>SDK AspNetCore サービス挿入<br>
            <i>RevealSdkContext<i> および <i>RevealUserContext<i> の実装をタイプのみ (インスタンスを渡さない) として登録できるようになり、これらのクラスがコンストラクターを介して挿入された他の AspNetCore サービスを取得できるようになりました。詳細については、GitHub で次の<a href="https://github.com/RevealBi/sdk-samples-aspnetcore/tree/main/Reveal.Sdk.Samples.Web.UpMedia.Backend">サンプル</a>をご覧ください。
            </td>
        </tr>
        <tr>
            <td>[公開バグ修正] 計算フィールド フィルターがサーバー上のデータ プロセスで機能しない問題<br>
            データのサーバー側集計を有効にすると、フィルターとして使用される計算フィールドが期待どおりにデータをフィルタリングしていなかった問題。
            </td>
        </tr>
        <tr>
            <td>[公開バグ修正] ダッシュボード フィルターに関する Google アナリティクスの問題<br>
            Google アナリティクス データ ソースからデータを取得するときに、ダッシュボード フィルターを作成できなかった問題。
            </td>
        </tr>
       <tr>
            <td rowspan="4">6 月 2021 年</td>
            <td rowspan="4">1.0.7 JAVA</td>
            <td>散布図が OpenStreetMap をサポートするようになりました!<br>
            SDK Web クライアント (JS) で OpenStreetMap 画像タイルを構成して使用できるようになりました。
            </td>
        </tr>
        <tr>
            <td>[公開 SDK バグ修正] コンポーネントを再マウントした後、テキスト ボックスのコンテンツが表示されない問題<br>
            ダッシュボードとテキスト ボックスの視覚化で React を使用すると、コンポーネントの再マウント後にコンテンツが表示されませんでした。ページの再読み込みが必要でした。
            </td>
        </tr>
        <tr>
            <td>[公開バグ修正] 計算フィールド フィルターがサーバー上のデータ プロセスで機能しない問題<br>
            データのサーバー側集計を有効にすると、フィルターとして使用される計算フィールドが期待どおりにデータをフィルタリングしていなかった問題。
            </td>
        </tr>
        <tr>
            <td>[公開バグ修正] ダッシュボード フィルターに関する Google アナリティクスの問題<br>
            Google アナリティクス データ ソースからデータを取得するときに、ダッシュボード フィルターを作成できなかった問題。
            </td>
        </tr>
        <tr>
            <td rowspan="2">6 月 2021 年</td>
            <td rowspan="2">1.0.6 JAVA</td>
            <td>[バグ修正] [SDK] Grizzly サーバーが例外をスローする問題<br>
            Grizzly で Reveal を実行すると、<i>javax.servlet.ServletContext</i> クラス (javax.servlet:javaz.servlet-api アセンブリ) の依存関係が間違っているため、<i>NoClassDefFoundError</i> 例外がスローされていました。
            </td>
        </tr>
        <tr>
            <td>JAVA SDK の新しいサンプルがリリースされました!<br>
            <a href="https://javaee.github.io/grizzly/">Grizzly</a> サーバーで Reveal を使用する方法を示す新しい <a href="https://github.com/RevealBi/sdk-samples-java/blob/main/upmedia-backend-grizzly">GitHub サンプル</a>があります。
            </td>
        </tr>
        <tr>
            <td rowspan="1">6 月 2021 年</td>
            <td rowspan="1">1.0.5 JAVA</td>
            <td>Web クライアントからサーバー側のデータ ソースへの資格情報<br>
            新しいタイプの資格情報 <i>RVHeadersDataSourceCredentials</i> を使用すると、認証ヘッダーとクッキーを REST および Web リソースのデータ ソースに送信できます。詳細については、GitHub で次の<a href="https://github.com/RevealBi/sdk-samples-java/blob/main/cookies-auth">サンプル</a>をご覧ください。
            </td>
        </tr>
        <tr>
            <td rowspan="6">5 月 2021 年</td>
            <td rowspan="6">1.0.1956 (1.0.4 JAVA)</td>
            <td>[公開バグ修正] [SDK] 誤って表示されたデータ ソースの完全なリストの問題<br>
            Desktop SDK で DataSourcesRequested コールバックを使用すると、明示的に追加されたデータ ソースの代わりに、データ ソースのリスト全体が表示されていました。
            </td>
        </tr>
        <tr>
            <td>[公開バグ修正] [SDK] Desktop SDK の Excel へのエクスポートが期待どおりに機能しない問題<br>
            ダッシュボードを歳読み込んでから単一の視覚化を Excel にエクスポートすると、ダッシュボードの最初の視覚化は常にエクスポートされたものでした。
            </td>
        </tr>
        <tr>
            <td>[公開バグ修正] [SDK] 動的ポートを使用する SQL データ ソースを含むダッシュボードが読み込まれていない問題<br>
            動的ポート (ホスト フィールドにインスタンスを提供) を使用して定義された SQL データ ソースを使用してダッシュボードを読み込むと、動的ポート構成の問題が原因でデータ ソース接続が機能しませんでした。
            </td>
        </tr>
        <tr>
            <td>[公開バグ修正] 視覚化フィルターとして設定された計算フィールドがエラーをスローしていた問題<br>
            別の計算フィールドに依存する計算フィールドに基づいて視覚化フィルターを構成すると、「無効な列名」というエラーが表示されていました。
            </td>
        </tr>
        <tr>
            <td>[公開バグ修正] "sort by:" 構成が異なるドリルダウン シナリオが期待どおりに機能しない問題<br>
            階層内のフィールドが "sort by: <any field>" と降順の並べ替えの組み合わせで構成されている場合、結果としてダッシュボードが読み込まれませんでした。
            </td>
        </tr>
        <tr>
            <td>クロスドメイン アプリケーションでの Web クライアントからサーバー側への資格情報<br>
            バックエンドがフロントエンドと同じドメインになく、認証クッキーが必要な場合は、次の Web SDK 設定を使用して資格情報を要求できます: <b>$.ig.RevealSdkSettings.requestWithCredentialsFlag = true;<b>
            </td>
        </tr>
        <tr>
            <td rowspan="2">5 月 2021 年</td>
            <td rowspan="2">1.0.3 JAVA</td>
            <td>新しい Snowflake コネクタ!<br>
            Reveal Java SDK は、Snowflake データ ソース コネクタをサポートするようになりました。これには、同じ Snowflake データベース内のテーブル間のデータ ブレンディングも含まれます。
            </td>
        </tr>
        <tr>
            <td>Java 用の Reveal BI エンジンが強化されました。<br>
            Java プラットフォームは他のプラットフォームと同じくらい堅固になり、可視化が大量のデータをクライアントに送り返すときにサーバーがクラッシュするのを防ぐのに役立ちます。 <b>InitializeParameterBuilder</b> のいくつかの新しいプロパティがこれを制御します: <i>maxInMemoryCells</i>、<i>maxStorageCells</i>、<i>maxStringCellSize</i>、および <i>maxTotalStringSize</i>。
            </td>
        </tr>
        <tr>
            <td rowspan="2">4 月 2021 年</td>
            <td rowspan="2">1.0.0 JAVA</td>
            <td>新しい JAVA SDK のリリース<br>
            Reveal は、.NET 以外の別の Web サーバー オプションとして JAVA をサポートするようになりました。JAVA SDK には JAVA 11+ が必要であり、Maven モジュールのセットとして配布されます。詳細については、<a
                href="../java-sdk/setup-configuration.html">セットアップと構成</a>を参照してください。
            </td>
        </tr>
        <tr>
            <td>JAVA SDK サンプルのリリース<br>
            使用可能な JAVA SDK UpMedia サンプルは <a
                href="https://github.com/RevealBi/sdk-samples-java">Github</a> に掲載されています。
            </td>
        </tr>
        <tr>
            <td rowspan="3">3 月 2021 年</td>
            <td rowspan="3">1.0.1866</td>
            <td>Web および Desktop SDK の新しいプロパティ:<br>
            <i>showEditDataSource</i> - データ ソース オーバーフロー メニューで通常使用できる [編集] ボタンを無効にするために使用できます。<br>
            <i>canAddDashboardFilter</i> - このプロパティは、[フィルターの追加] メニューの [ダッシュボード フィルターの追加] オプションを非表示にすることができます。これらのオプションは、ダッシュボード編集モードで使用できます。<br>
            <i>canAddDateFilter</i> - このプロパティは、[フィルターの追加] メニューの [日付フィルターの追加] オプションを非表示にすることができます。これらのオプションは、ダッシュボード編集モードで使用できます。
            </td>
        </tr>
        <tr>
            <td>[公開バグ修正] [SDK] revealView.canSaveAs プロパティが正しく動作しない問題。<br>
            Web SDK では、ダッシュボードの設定後に変更された場合、canSaveAs プロパティが優先されませんでした。
            </td>
        </tr>
        <tr>
            <td>[公開バグ修正] [SDK] HttpContextAccessor.HttpContext プロパティが正しく動作しない問題。<br> Web SDK では、ダッシュボードを保存する際に (SaveDashboardAsync メソッドからアクセスした場合)、HttpContextAccessor.HttpContext が null になります。
            </td>
        </tr>
        <tr>
            <td>3 月 2021 年</td>
            <td>1.0.1821</td>
            <td>[公開バグ修正] [SDK] SDK アプリが NRE 例外をスローすることがある問題。<br> ユーザーが操作せずに SDK アプリケーションを 90 分以上開いた場合、操作を実行すると例外がスローされていました。</td>
        </tr>
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
