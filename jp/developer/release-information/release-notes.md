## リリース ノート

以下は、Reveal SDK の各バージョンに含まれる新機能および拡張機能です。

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 80%" />
</colgroup>
    <thead>
        <tr>
            <th>SDK バージョン</th>
            <th>説明</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td rowspan="5">1.0.1422</td>
            <td><i>Amazon Athena connector in BETA</i><br>
            You can now connect to Amazon's serverless, interactive query service Athena.</td>
        </tr>
        <tr>
            <td><i>NEW Pre-built Themes</i><br>We added four pre-built app themes. Set one of them and use the customizable settings to additionaly personalize the look and feel of the Visualization and Dashboard editor. You can choose from one of the following themes:
            MountainLightTheme (Desktop) / $.ig.MountainLightTheme (Web); 
            MountainDarkTheme (Desktop) / $.ig.MountainDarkTheme (Web);
            OceanLightTheme (Desktop) / $.ig.OceanLightTheme (Web);
            OceanDarkTheme (Desktop) / $.ig.OceanDarkTheme (Web).
</td>
        </tr>
        <tr>
            <td><i>Marketo provider is Now Available</i><br>You can now connect to the marketing platform Marketo and use your data in Reveal.</td>
        </tr>
        <tr>
            <td><i>Amazon Redshift provider is Now Available</i><br>You can now use and gain new insights from your data in the Amazon Redshift cloud data warehouse.</td>
        </tr>
        <tr>
            <td><i>New "Data Process on Server" feature</i><br>You can now have server-side aggregation of the data coming from the MS SQL, MySQL and Postgres data sources</td>
        </tr>
        <tr>
            <td rowspan="6">1.0.1374</td>
            <td><i> New API to set axis bounds for charts</i><br> You can now programmatically change the axis bounds in runtime for a particular visualization.</td>
        </tr>
        <tr>
            <td><i>Salesforce data source enhancements</i><br>Now you can use your Salesforce reports in Reveal.</td>
        </tr>
        <tr>
            <td><i>New QuickBooks data source</i><br>Connect to your Quickbooks account and use your entities to perform data analysis in Reveal.</td>
        </tr>
        <tr>
            <td><i>New Hubspot data source</i><br>You can now connect to Hubspot.</td>
        </tr>
        <tr>
            <td><i>Sharepoint lists and document libraries support</i><br>You can now use the metadata (name, type, etc.) collected for all files in a SharePoint library as a data source in Reveal.</td>
        </tr>
        <tr>
            <td><i>New Choropleth Map Visualization</i><br>The Choropleth map visualization allows you to create beautiful thematic maps. You can now present geospatial data in an incredibly digestible manner. Let color guide you and help you quickly discover patterns, trends and anomalies on the map.</td>
        </tr>
        <tr>
            <td rowspan="2">1.0.1255</td>
            <td><i>New Azure Analysis Services data source</i><br>With this new data source, you can create dashboards using your data models in Azure Analysis Services.</td>
        </tr>
        <tr>
            <td><i>New icon for Google Sheets files</i><br>The look of the Google Sheets files icon was changed.</td>
        </tr>
        <tr>
            <td rowspan="5">1.0.1222</td>
            <td><i>New Hover Events API</i><br>
            This new event is called *revealView.TooltipShowing* in WPF and .onTooltipShowing in Web and is triggered whenever the end-user hovers over a series in a visualization or clicks on the series.</td>
        </tr>
        <tr>
            <td><i>New TreeMap visualization</i><br>You can use this new visualization type to present large hierarchies with a set of nested rectangles. Rectangles’ size will show you part-to-whole relationships amongst a variety of metrics, helping you identify patterns and relations between similar data.
</td>
        </tr>
        <tr>
            <td><i>Export to Excel enhancements</i><br>You can include more visualization types in your spreadsheets upon export. Scatter, Bubble and Sparkline charts are now available.</td>
        </tr>
        <tr>
            <td><i>Various UI/UX improvements</i><br>Various minor changes were added to improve user experience in the Visualization, Dashboard, New Data Source dialog, etc.</td>
        </tr>
        <tr>
            <td><i>Added support for Shared Drives in Google Drive</i><br>If you have a GSuite Business account, you can now access your Shared Drives data and use it to build visualizations in Reveal.</td>
        </tr>
        <tr>
            <td>1.0.1136</td>
            <td><i>新しいカスタム テーマ</i><br>
            新しい RevealTheme (デスクトップ) / $.ig.RevealTheme (Web) クラスでカスタマイズ可能な設定の一部またはすべてを構成することにより、Reveal で独自のテーマを作成できるようになりました。</td>
        </tr>
        <tr>
            <td rowspan="3">1.0.981</td>
            <td><i>RevealSettings の新しいプロパティ</i><br>$.ig.RevealSettings にさまざまな機能を制御するための複数の新しいプロパティを追加しました。ShowExportToPDF、ShowExportToPowerpoint、ShowExportToExcel、ShowStatisticalFunctions、ShowDataBlending、ShowMachineLearningModelsIntegration、StartWithNewVisualization、InitialThemeName。</td>
        </tr>
        <tr>
            <td><i>アクセント色のサポート</i><br>SetAccentColor メソッドが $.ig.RevealView に追加されました。</td>
        </tr>
        <tr>
            <td><i>Trigger プロパティが DataSourceRequested イベントに追加されました。</i><br>DataSourcesRequestedTriggerType 型の Trigger プロパティを DataSourcesRequested イベント引数に追加しました。このイベントのユーザーは、DataSourcesRequested の目的について詳細なコンテキストを取得できます。</td>
        </tr>
            <td>1.0.825</td>
            <td><i>画像エクスポート機能が利用できるようになりました。</i><br>サーバー側の画像エクスポート (プログラム上およびユーザー操作の両方により) が再び有効になりました。修正の詳細については、以下のトピックを参照してください。 <a href="setup-configuration-server-web#server-side-image-export">サーバー側画像生成の有効化</a></td>
        <tr>
        </tr>
            <td rowspan="4">1.0.80x</td>
            <td><i>Reveal Desktop SDK のローカリゼーション サービス</i><br>さまざまなダッシュボード要素のタイトルおよびラベルをローカライズすることができます。ローカライゼーション サービスでは、数値および非集計の日付フィールドの書式設定を変更することもできます。</td>
        <tr>
        <tr>
            <td><i>Reveal Desktop SDK の書式設定サービス</i><br>数値データ、集計および非集計の日付フィールドを好みに合わせて書式設定できます。デフォルトの書式設定を無視して、ダッシュボード データを書式設定します。</td>
        </tr>
        <tr>
            <td><i>セットアップと構成の変更 (Server SDK)</i><br>Reveal Server SDK には、.NET Core 2.2+ および .NET Framework 4.6.1+ ASP MVC アプリケーション プロジェクトがサポートされます。また、NuGet パッケージ マネージャーのみを使用すると、アセンブリを参照し、依存関係パッケージをインストールします。</td>
        </tr>        
        </tr>
            <td rowspan="4">1.0.70x</td>
            <td><i>ステップバイステップ ガイド</i><br>Reveal SDK の前提条件、セットアップや構成に必要な手順全般に関するトピックを追加。</td>
        <tr>
        <tr>
            <td><i>ウィジェット データソースの変更</i><br>エンドユーザーによってウィジェットのデータソースを変更する機能を有効または無効にできます。編集モードで [可視化データ] 画面を開いた際に、UI の [データソースの変更] ボタンを表示または非表示にできます</td>
        </tr>
        <tr>
            <td><i>ダッシュボード テーマの変更</i><br>エンドユーザーによってダッシュボードのテーマを変更する機能を有効または無効にできます。ダッシュボードの編集モードに入る際に、使用可能なテーマを表示するためのボタンを表示または非表示にできます。</td>
        </tr>        
    </tbody>
</table>
