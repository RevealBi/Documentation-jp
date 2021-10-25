# ダッシュボード ファイルの読み込み

## 概要

SDK でダッシュボードを開く/保存するには 2 つの方法があります

  - **サーバー側**: はじめにクライアント ページでダッシュボード ID を指定します。次に、サーバーで、以下に詳述するコールバック メソッドを使用して、Reveal.Sdk.Dashboard クラスのインスタンスを返します。対応する dashboardId のダッシュボード ストリームを Dashboard クラスのコンストラクターに渡すことにより、そのクラスをインスタンス化します。


    これが最も簡単な方法であり、最初に SDK を評価するときに推奨される方法です。

  - **クライアント側**: 完全な制御と高い柔軟性が提供されます。カスタム サーバーからコンテンツを取得しながら、クライアント ページでダッシュボードのコンテンツをストリームに提供します。

  この方法を使用すると、たとえばユーザーのアクセス許可を確認したり、カスタムなユーザーインターフェイスを表示してダッシュボードを選択したり、ユーザーが使用する .rdash ファイルをアップロードしたりすることができます。クライアント側での方法の詳細については、[**セットアップと構成 (クライアント)**](~/jp/developer/web-sdk/setup-configuration.html#セットアップと構成-クライアント)を参照してください。

## サーバー側の作業

ダッシュボードを視覚化するために、SDK に Dashboard クラスのインスタンスを提供できます。これにより、ストリームを rdash または rdash の json 文字列表現にインスタンス化できます。

以下のコードスニペットは、プロジェクトに組み込みリソースとして追加された Rdash ファイルを読み込む方法を示しています。このメソッドは、__IRVDashboardProvider.GetDashboardAsync__ メソッドのための実装です。

## コード

``` csharp
public override Task<Dashboard> GetDashboardAsync(IRVUserContext userContext, string dashboardId)
{
    var dashboardFileName = dashboardId + ".rdash";
    var resourceName = $"Demo1.Dashboards.{dashboardFileName}";
    var assembly = Assembly.GetExecutingAssembly();
    var rdashStream = assembly.GetManifestResourceStream(resourceName)
    var dashboard = new Dashboard(rdashStream);

    return Task.FromResult(dashboard);
}
```

__IRVDashboardProvider.GetDashboardAsync__ のこのコードは、クライアントで **RVDashboard.loadDashboard** 関数を使用するとサーバー上で呼び出されます。そして最初のパラメーターとしてクライアント側で指定された dashboardId を取得します。

