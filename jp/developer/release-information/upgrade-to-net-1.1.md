## .NET 1.1.0 の重大な変更のリスト

1. **[.NET サーバー]** RevealSdkContext (RevealSdkContextBase クラスと IRevealSdkContext インターフェイス) を削除しました - これを提供していた主な目的は、Reveal に必要ないくつかのサービス/プロバイダーをバンドルすることだけでした。
2. **[.NET サーバー]** アプリケーションの Startup.cs クラスの Reveal サービスの登録と構成を更新しました。
   1. 以前は、RevealSdkProvider の具体的なインスタンスを登録する必要がありました。つまり、デフォルトの依存関係の挿入フレームワークを使用して、既存の ApsNetCore サービスを簡単にプラグインすることはできませんでした。これで、RevealSdkContext を削除した後、Reveal に必要なサービスの実装を登録し、それらをタイプとして登録するための、シンプルでより流暢な方法を提供します。
   2. バージョン 1.1 より前は、AddRevealServices と AddReveal の 2 つの呼び出しを行う必要がありましたが、今では 1 回の AddReveal() 呼び出しのみを行っています。
3. **[.NET サーバー]** Reveal.Sdk.Dashboard クラス コンストラクターのオーバーロードに小さな変更を加えて、一貫性を高めました。現在、ストリーム、ファイル パス、またはバイト配列から rdash 形式でダッシュボードを読み込む 3 つのコンストラクター オーバーロードがあります。Json からの読み込みは、FromJsonString と呼ばれる静的メソッドを介して利用できます。そして、Dashboard クラスのシリアル化メソッドは、ToStreamAsync、ToByteArrayAsync、rdash 形式の SaveToFileAsync、および Json 文字列として保存する ToJsonStringAsync です。
4. **[.NET サーバー、デスクトップ]** IRVDataSourceProvider インターフェイスが変更され、以前のバージョンのように、顧客からの最初のダッシュボード要求でのみ使用されなくなりました。これで、データの要求がサーバーに送信されるたびに呼び出されます。インターフェイスに実装される単一の ChangeDataSourceItemAsync もあります。
5. **[.NET サーバー]** Reveal.Sdk.Web.AspNetCore(.Trial) パッケージは、.NET 4.6.2 および NET Core 2.2 をサポートしなくなり、NET Core 3.1 以降のみをサポートします。
6. **[JS クライアント]** クライアント側 - onVisualizationLinkingDashboard イベントが RevealView クラスから削除され、同じ目的を果たし、エディターでダッシュボード リンクを作成するときに使用される onLinkedDashboardProviderAsync が優先されます。

## プロジェクトをアップグレードする方法

1. Reveal.Sdk.IRVDashboardProvider を実装するクラスを作成します - 以下のコード スニペットでは、MyDashboardProvider と呼ばれます。この新しいプロバイダーには、GetDashboardAsync と SaveDashboardAsync が含まれています。したがって、これらのメソッドの実装をここに移動する必要があります。これらの API メソッドのもう 1 つの重要な変更は、両方が文字列 userId の代わりに IRVUserContext インターフェイスを使用しており、GetDashboardAsync も userContext を取得するようになったことです。さらに、IRVUserContextProvider の実装を作成することで、ユーザー コンテキストとして渡されるものをより細かく制御できます。

2. Startup.cs ファイルに移動し、ConfigureServices の services.AddRevealServices() 呼び出しを削除します。
以下に示すように、.AddReveal 呼び出しを変更します。
```csharp
services
      .AddMvc()
      .AddReveal(builder => 
      {
         builder
            .AddDashboardProvider<MyDashboardProvider>()
            .AddSettings(s =>
            {
                  s.CachePath = s.DataCachePath = cacheFilePath;
                  s.LocalFileStoragePath = GetLocalFileStoragePath();
            });
      });
```
これで、ダッシュボード プロバイダーが登録され、いくつかの設定が含まれているはずです。

3. IRVDataSourceProvider の実装を修正します。視覚化またはフィルタリングに関する以前の 2 つのメソッドの区別は、1.1 では使用できません。これで、置き換える必要のあるデータ ソース アイテムを取得できます。したがって、ChangeDashboardFilterDataSourceItemAsync を移動して調整し、ChangeDataSourceItemAsync にする必要があります。
4. 文字列 dashboardId の代わりに IRVUserContext を受け入れるように、IRVAuthenticationProvider の実装を修正します。
5. RVBaseUserContextProvider 実装を使用していた場合、この基本クラスが使用できなくなったというエラーが表示されます。したがって、基本クラスの代わりに IRVUserContextProvider インターフェイスを実装する必要があります。これは、IRVUserContext 実装の作成を担当します。使用できるユーザー コンテキスト インターフェイスのデフォルトの実装があります。これは Reveal.Sdk.RVUserContext クラスです。

6. Reveal ビューで onLinkedDashboardProviderAsync イベントを使用して、onVisualizationLinkingDashboard の使用を置き換えます。例として、次を:
```javascript
revealView.onVisualizationLinkingDashboard = function (title, url, callback) {
      callback(url);
};
```
次に変更する必要があります:
```javascript
revealView.onLinkedDashboardProviderAsync = (dashboardId => {
   return $.ig.RVDashboard.loadDashboardAsync(dashboardId);
})
```
