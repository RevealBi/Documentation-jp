## リリース ノート

以下は、Reveal SDK の新機能および追加予定のアップデートです。

<table>
    <colgroup>
        <col style="width: 15%" />
        <col style="width: 10%" />
        <col style="width: 75%" />
    </colgroup>
    <thead>
        <tr>
            <th>日付</th>
            <th>SDK バーション</th>
            <th>説明</th>
        </tr>
    </thead>
    <tbody>
           <tr>
        <td rowspan="5">12 月 2021 年</td>
        <td rowspan="5">1.1.1 .NET</td>
        <td>タイトルやケバブ メニューなど、ダッシュボード ヘッダーを非表示にするオプションが追加されました。<br>
            <a hre="/api/wpf/latest/Reveal.Sdk.RevealView.html#Reveal_Sdk_RevealView_ShowHeader">ShowHeader</a> (WPF) & <a href="/api/javascript/latest/classes/revealview.html#showheader">showHeader</a> (JS)。
        </td>
    </tr>
    <tr>
        <td>Added an option to enable/disable the end user ability to maximize visualizations<br>
            <a hre="/api/wpf/latest/Reveal.Sdk.RevealView.html#Reveal_Sdk_RevealView_CanMaximizeVisualizationProperty">CanMaximizeVisualizationProperty</a> (WPF) & <a href="/api/javascript/latest/classes/revealview.html#canmaximizevisualization">canMaximizeVisualizationProperty</a> (JS)。 
        </td>
    </tr>
    <tr>
        <td>視覚化エディターで特定の視覚化の背景色を変更するエンド ユーザー機能を有効/無効にするための新しいオプションがエディターに追加されました。</br>
           <a href="/api/wpf/latest/Reveal.Sdk.RevealView.html#Reveal_Sdk_RevealView_CanChangeVisualizationBackgroundColorProperty">CanChangeVisualizationBackgroundColorProperty</a> (WPF) & <a href="/api/javascript/latest/classes/revealview.html#canchangevisualizationbackgroundcolor">canChangeVisualizationBackgroundColor</a> (JS)。
    </tr>
    <tr>
        <td>プログラムで視覚化の背景色を変更する新しい方法。</br>
            <a href="/api/wpf/latest/Reveal.Sdk.RevealView.html#Reveal_Sdk_RevealView_SetVisualizationBackgroundColor_Reveal_Sdk_RVVisualization_System_Windows_Media_Color_">SetVisualizationBackgroundColor</a> (WPF) & <a href="/api/javascript/latest/classes/revealview.html#setvisualizationbackgroundcolor">setVisualizationBackgroundColor</a> (JS)。
        </td>
    </tr>
        <tr>
        <td>[公開バグ修正]<br>
        - データセットに null の日付値がある場合の Excel へのエクスポートを修正しました。<br>
        - カスタム ブランド ロゴを使用して PDF または PPT にエクスポートする際の問題を修正しました。
        </td>
    </tr>
    <tr>
        <td rowspan="3">10 月 2021 年</td>
        <td rowspan="3">1.1.0 .NET</td>
        <td>.NET Server SDK は、いくつかの変更を加えて拡張されました:<br>
        - Registering Reveal services is more flexible - You now can inject other services in your implementations of Reveal interfaces. You only register the type of your implementations of your Reveal providers interfaces.<br>
        - RevealSDKContext removed - RVUserContext is now first class citizen across reveal providers. You need to register a UserContextProvider, which will be instantiating that class and it would be passed to the methods of other Reveal services like IRVDashboardProvider.<br>
        - .NET Core 3.1 or newer is now required - Reveal dropped support for .NET Core running on top of .NET Framework v4.6.2 or higher and .NET core 2.2 as it is out of support.<br>
        - Improved setup for default implementations - Greatly improved setup for default implementations - Now it's pretty simple to setup Reveal if you have your dashboards in a "Dashboards" folder and your local data files (csv or excel) are located in your "Data" folder on the project root level. Example:<br>
        services<br>
        &emsp;&emsp;.AddMvc()<br>
        &emsp;&emsp;.AddReveal();<br>
        For further details, please refer to <a
                href="../release-information/upgrade-to-net-1.1.html">Reveal .NET SDK Upgrade to v1.1</a>.
        </td>
    </tr>
    <tr>
        <td>IRVDataSourceProvider インターフェイスが変更されました (デスクトップ および .NET サーバー SDK)<br>
        IRVDataSourceProvider インターフェイスには単一の ChangeDataSourceItem があり、ダッシュボードがデータ ソース アイテムを使用する必要があるときはいつでも呼び出されます。
        </td>
    </tr>
    </tr>
    <tr>
        <td>データ ブレンディング画面の検索フィールド<br>
            結果に結合/追加するフィールドを検索する機能を追加することにより、データ ブレンディング UI が改善されました。
        </td>
    </tr>
    <tr>
            <td rowspan="2">9 月 2021 年</td>
            <td rowspan="2">1.0.2013</td>
            <td>[公開バグ修正] Calculated field export to excel resulting in empty cells<br>
            ゼロ除算を行う計算フィールドを Excel にエクスポートすると、結果には空のセルが含まれていました。
            </td>
        </tr>
        <tr>
            <td>[公開バグ修正] Data blending with custom queries and server-side processing issues<br>
            Web .NET で [サーバーでデータを処理] をオンにしてカスタム クエリを実行すると、データ ブレンディングが期待どおりに機能しませんでした。
            </td>
        </tr>
        <tr>
            <td rowspan="2">9 月 2021 年</td>
            <td rowspan="2">1.0.2012</td>
            <td>[公開バグ修正] [SDK] Small window sizes render Text chart unreadable<br>
            Web とデスクトップの両方で、ウィンドウのサイズが小さいと、テキスト チャート フォントが読み取れなくなります。
            </td>
        </tr>
        <tr>
            <td>[公開バグ修正] [SDK] Issues getting the list of date formats<br> When getting a list of date formats for a field editor in the Desktop SDK, you can now use RVBaseFormattingService with aggregated dates.
            </td>
        </tr>
        <tr>
            <td>8 月 2021 年</td>
            <td>1.0.2008</td>
            <td>[公開バグ修正] [SDK] Saving dashboard as a stream has issues<br> When saving dashboards as a stream, in some specific cases dashboard.Serialize.Async() was returning null.</td>
        </tr>
       <tr>
            <td rowspan="4">6 月 2021 年</td>
            <td rowspan="4">1.0.2005</td>
            <td>散布図が OpenStreetMap をサポートするようになりました!<br>
            デスクトップ (WPF) および Web クライアント (JS) で OpenStreetMap 画像タイルを構成して使用できるようになりました。
            </td>
        </tr>
        <tr>
            <td>新しいサムネイル コンポーネント!<br>
            RevealDashboardThumbnailView を使用してダッシュボードのサムネイルを描画できるようになりました。.
            </td>
        </tr>
        <tr>
            <td><a name="java-sdk-1.0.7"></a>[公開バグ修正] Calculated field filter not working with data process on server<br>
            データのサーバー側集計を有効にすると、フィルターとして使用される計算フィールドが期待どおりにデータをフィルタリングしていなかった問題
            </td>
        </tr>
        <tr>
            <td>[公開バグ修正] Google Analytics issues with dashboard filters<br>
            Google アナリティクス データ ソースからデータを取得するときに、ダッシュボード フィルターを作成できなかった問題
            </td>
        </tr>
        <tr>
            <td rowspan="5">5 月 2021 年</td>
            <td rowspan="5">1.0.1956</td>
            <td>[公開バグ修正] [SDK] Full list of Data Sources displayed by mistake<br>
            When using DataSourcesRequested callback in the Desktop SDK, the whole list of data sources was being displayed instead of the ones explicitly added.
            </td>     
        </tr>
        <tr>
            <td>[公開バグ修正] [SDK] Desktop SDK export to Excel not working as expected<br>
            ダッシュボードを歳読み込んでから単一の視覚化を Excel にエクスポートすると、ダッシュボードの最初の視覚化は常にエクスポートされたものでした。
            </td>
        </tr>
        <tr>
            <td>[公開バグ修正] [SDK] Dashboard with SQL data source using a dynamic port not loading<br>
            動的ポート （ホスト フィールドにインスタンスを提供） を使用して定義された SQL データ ソースを使用してダッシュボードを読み込むと、動的ポート構成の問題が原因でデータ ソース接続が機能しませんでした。
            </td>
        </tr>
        <tr>
            <td>[公開バグ修正] Calculated field set as Visualization filter were throwing an error<br>
            別の計算フィールドに依存する計算フィールドに基づいて視覚化フィルターを構成すると、「無効な列名」 というエラーが表示されていました。
            </td>
        </tr>
        <tr>
            <td>[公開バグ修正] Drill down scenario with different "sort by" configurations not working as expected<br>
            When the fields in a hierarchy were configured with a combination of "sort by: <any field>" and a descending sorting, the result was the dashboard not loading.
            </td>
        </tr>
        <tr>
            <td rowspan="1">3 月 2021 年</td>
            <td rowspan="1">1.0.1866</td>
            <td>New Properties for Desktop SDK:<br>
            ShowEditDataSource - can be used to disable the Edit button normally available in the data source overflow menu.<br>
            CanAddDashboardFilter - this property can hide the "Add Dashboard Filter" option in the Add Filter menu. これらのオプションは、ダッシュボード編集モードで使用できます。<br>
            CanAddDateFilter - this property can hide the "Add Date Filter" option in the Add Filter menu. これらのオプションは、ダッシュボード編集モードで使用できます。
            </td>     
        </tr>
        <tr>
            <td>3 月 2021 年</td>
            <td>1.0.1821</td>
            <td>[公開バグ修正] [SDK] SDK apps sometimes throw an NRE exception<br> When an SDK application was opened for more than 90 minutes without users interacting with it, performing an action was throwing an exception.</td>
        </tr>
            <td>2 月 2021 年</td>
            <td>1.0.1772</td>
            <td>[Bug Fix] [SDK] Installation of WPF NuGet package failing with packages.config<br> The installation of WPF NuGet package was failing when the host project used packages.config.
            </td>
        </tr>
        <tr>
            <td rowspan="6">2 月 2021 年</td>
            <td rowspan="6">1.0.1763</td>
            <td>[公開バグ修正] [SDK] HasPendingChanges property not working as expected<br> In Desktop SDK, the
                HasPendingChanges property was not set to false after saving a dashboard with changes.</td>
        </tr>
        <tr>
            <td>[公開バグ修正] [SDK] Custom filtering not working <br>In Desktop SDK, custom queries were not
                filtering data as expected.</td>
        </tr>
        <tr>
            <td>[公開バグ修正] [SDK] Hiding SQLServer tables also hides views<br>When using
                RVDataSourceItemsFilter to hide all tables and show only views, the Views tab was also hidden.</td>
        </tr>
        <tr>
            <td>[公開バグ修正] [SDK] AzureSQL Data Provider  throwing an error <br>When adding an AzureSQL
                connection, an error message was displayed.</td>
        </tr>
        <tr>
            <td>[公開バグ修正] [SDK] Date filters not displayed if LocalizationProvider set<br>When a
                LocalizationProvider was set, date filters from/to were not displayed in the visualizations editor.</td>
        </tr>
        <tr>
            <td>[公開バグ修正] Word not localized to Japanese<br>The word "Others" was not localized to "その他"
                in Japanese.</td>
        </tr>
        <tr>
            <td rowspan="2">1 月 2021 年</td>
            <td rowspan="2">1.0.1712</td>
            <td>[公開バグ修正] [SDK] The server component relies on Newtonsoft.Json serializer<br> The Reveal
                server component was relying on the default JSON serialization settings of the MVC application. Now the
                hosting app can configure JSON serialization settings as needed.</td>
        </tr>
        <tr>
            <td>[公開バグ修正] [SDK] SQL Server filtering not working for NVARCHAR columns<br>Filtering for
                Microsoft SQL Server was not working for NVARCHAR columns when the filtered value contained multibyte
                characters.</td>
        </tr>
        <tr>
            <td rowspan="2">12 月 2020 年</td>
            <td rowspan="2">1.0.1669</td>
            <td>[公開バグ修正] [SDK] Pivot hierarchies filtering not working with "Processing Data on
                    Server"<br>If the option "Processing Data on Server" was checked, drill down hierarchies in the
                Pivot Editor were not filtering data.</td>
        </tr>
        <tr>
            <td>[公開バグ修正] [サーバーでデータを処理] で [SDK] カスタム フィルタリングが機能しない問題。<br>If the
                option "Processing Data on Server" was checked, custom queries were not returning the correct number of
                rows.</td>
        </tr>
        <tr>
            <td rowspan="4">12 月 2020 年</td>
            <td rowspan="4">1.0.1629</td>
            <td>JSON ファイルを使用してダッシュボードを保存/ロード<br>You can now use Reveal SDK to save/load dashboards to/from
                JSON files.</td>
        </tr>
        <tr>
            <td>[公開バグ修正] カテゴリ フィールド ラベルが表示されない問題。<br>In Category Charts, tooltips were not
                displaying the field label but the original field name of a category instead.</td>
        </tr>
        <tr>
            <td>[公開バグ修正] ドリルダウン ブレッドクラムの日付が誤って表示される問題。<br>When drilling down on a
                date field, breadcrumbs did not display values properly. Now breadcrumbs give clear information about
                your drill down level.</td>
        </tr>
        <tr>
            <td>[公開バグ修正] ホバー ツールチップと十字線がデフォルトで表示されない問題。<br>In Dashboard View mode,
                Hover Tooltips and Crosshairs were not displayed until users enable them. Now they are enabled by
                default.</td>
        </tr>
        <tr>
            <td rowspan="5">9 月 2020 年</td>
            <td rowspan="5">1.0.1422</td>
            <td>Amazon Athena コネクター (ベータ版)<br>
                Amazon のサーバーレス インタラクティブな Athena クエリ サービスに接続できるようになりました。</td>
        </tr>
        <tr>
            <td>新しいビルド済みテーマ<br>4 つのビルド済みアプリ テーマを追加しました。 Set one of them and use the
                customizable settings to additionally personalize the look and feel of the Visualization and Dashboard
                editor. You can choose from one of the following themes:
                MountainLightTheme (Desktop) / $.ig.MountainLightTheme (Web);
                MountainDarkTheme (Desktop) / $.ig.MountainDarkTheme (Web);
                OceanLightTheme (Desktop) / $.ig.OceanLightTheme (Web);
                OceanDarkTheme (Desktop) / $.ig.OceanDarkTheme (Web).
            </td>
        </tr>
        <tr>
            <td>Marketo プロバイダーを利用できるようになりました。<br>You can now connect to the marketing platform Marketo and
                use your data in Reveal.</td>
        </tr>
        <tr>
            <td>Amazon Redshift を利用できるようになりました。<br>You can now use and gain new insights from your data
                in the Amazon Redshift cloud data warehouse.</td>
        </tr>
        <tr>
            <td>新しい「サーバーでデータを処理」機能<br>You can now have server-side aggregation of the data
                coming from the MS SQL, MySQL and Postgres data sources</td>
        </tr>
        <tr>
            <td rowspan="6">7 月 2020 年</td>
            <td rowspan="6">1.0.1374</td>
            <td> New API to set axis bounds for charts<br> You can now programmatically change the axis bounds in
                runtime for a particular visualization.</td>
        </tr>
        <tr>
            <td>Salesforce データソースの機能強化<br>Reveal で Salesforce レポートを使用できます。</td>
        </tr>
        <tr>
            <td>新しい Quickbooks データソース<br>Connect to your Quickbooks account and use your entities to perform
                data analysis in Reveal.</td>
        </tr>
        <tr>
            <td>新しい Hubspot データソース<br>Hubspot に接続できます。</td>
        </tr>
        <tr>
            <td>Sharepoint リストとドキュメント ライブラリのサポート<br>You can now use the metadata (name, type,
                etc.) collected for all files in a SharePoint library as a data source in Reveal.</td>
        </tr>
        <tr>
            <td>新しい階級区分図<br>The Choropleth map visualization allows you to create
                beautiful thematic maps. 地理空間データを驚くほどわかりやすく表示できます。 Let
                color guide you and help you quickly discover patterns, trends and anomalies on the map.</td>
        </tr>
        <tr>
            <td rowspan="2">5 月 2020 年</td>
            <td rowspan="2">1.0.1255</td>
            <td>新しい Azure Analysis Services データソース<br>With this new data source, you can create dashboards
                using your data models in Azure Analysis Services.</td>
        </tr>
        <tr>
            <td>Google スプレッドシート ファイルの新しいアイコン<br>Google スプレッドシート ファイルのアイコンが変更されました。</td>
        </tr>
        <tr>
            <td rowspan="5">5 月 2020 年</td>
            <td rowspan="5">1.0.1222</td>
            <td>新しいホバー イベント API<br>
                This new event is called *revealView.TooltipShowing* in WPF and .onTooltipShowing in Web and is
                triggered whenever the end-user hovers over a series in a visualization or clicks on the series.</td>
        </tr>
        <tr>
            <td>新しい TreeMap の表示形式<br>You can use this new visualization type to present large hierarchies
                with a set of nested rectangles. Rectangles’ size will show you part-to-whole relationships amongst a
                variety of metrics, helping you identify patterns and relations between similar data.
            </td>
        </tr>
        <tr>
            <td>Excel へエクスポート機能拡張<br>You can include more visualization types in your spreadsheets
                upon export. 散布図、バブル チャート、スパークライン チャートが利用できるようになりました。</td>
        </tr>
        <tr>
            <td>UI/UX の改善<br>Various minor changes were added to improve user experience in the
                Visualization, Dashboard, New Data Source dialog, etc.</td>
        </tr>
        <tr>
            <td>Google ドライブで共有ドライブのサポートを追加<br>If you have a GSuite Business account, you can
                now access your Shared Drives data and use it to build visualizations in Reveal.</td>
        </tr>
        <tr>
            <td>4 月 2020 年</td>
            <td>1.0.1136</td>
            <td>新しいカスタム テーマ<br>
                Now you can create your own theme in Reveal by configuring some or all of the customizable settings in
                the new RevealTheme (Desktop) / $.ig.RevealTheme (Web) class.</td>
        </tr>
        <tr>
            <td rowspan="3">2 月 2020 年</td>
            <td rowspan="3">1.0.981</td>
            <td>RevealSettings の新しいプロパティ<br>We added multiple new properties to $.ig.RevealSettings to
                control different features, including: ShowExportToPDF, ShowExportToPowerpoint, ShowExportToExcel,
                ShowStatisticalFunctions, ShowDataBlending, ShowMachineLearningModelsIntegration,
                StartWithNewVisualization, InitialThemeName.</td>
        </tr>
        <tr>
            <td>アクセント色のサポート<br>You can now find the SetAccentColor method added to
                $.ig.RevealView.</td>
        </tr>
        <tr>
            <td>Trigger プロパティが DataSourceRequested イベントに追加されました。<br>We added a Trigger (of type
                DataSourcesRequestedTriggerType) property to the DataSourcesRequested event arguments. The users of this
                event will now gain more context about the DataSourcesRequested purposes.</td>
        </tr>
        <td>11 月 2019 年</td>
        <td>1.0.825</td>
        <td>Export to Image Functionality is Now Working<br>Exporting images server-side (both programmatically
            and through user interaction) was enabled again. 修正の詳細については、<a
                href="../setup-configuration/setup-configuration-web.html#server-side-image-export">サーバー側画像生成の有効化</a>のトピックを参照してください。 </td>
        <tr>
        </tr>
        <td rowspan="4">9 月 2019 年</td>
        <td rowspan="4">1.0.80x</td>
        <td>Reveal Desktop SDK のローカリゼーション サービス<br>You can now localize titles and labels of a variety of
            dashboard elements. The Localization service also enables you to change the formatting settings of numeric
            and non-aggregated date fields.</td>
        <tr>
        <tr>
            <td>Reveal Desktop SDK の書式設定サービス<br>You can now format numeric data, aggregated and
                non-aggregated date fields to your own preferences. Ignore the default formatting and format your
                dashboard data the way you like it.</td>
        </tr>
        <tr>
            <td>Changes in Setup and Configuration (Server SDK)<br>Reveal Server SDK now supports .NET Core 2.2+
                as well as .NET Framework 4.6.1+ ASP MVC application projects. In addition, you will now use exclusively
                the NuGet package manager to reference assemblies and install dependency packages.</td>
        </tr>
        </tr>
        <td rowspan="4">9 月 2019 年</td>
        <td rowspan="4">1.0.70x</td>
        <td>Step by Step Guide<br>With this detailed guide, you will start with prerequisites and go through
            every step needed to setup and configure Reveal’s SDK.</td>
        <tr>
        <tr>
            <td>Change the Widget’s Data Source<br>You can now enable or disable the possibility to change a
                widget’s data source to end users. When opening the Visualization Data screen in edit mode, Reveal will
                either show or hide the change data source button in the UI.</td>
        </tr>
        <tr>
            <td>Reveal Desktop SDK の書式設定サービス<br>You can now enable or disable the possibility to
                change the dashboard’s theme to end users. When entering edit mode for a dashboard, Reveal will either
                show or hide the button used to display the available themes.</td>
        </tr>
    </tbody>
</table>
