## ダッシュボード ファイル読み込み

### 概要

SDK でダッシュボードを開く/保存するには 2 つの方法があります。

  - **サーバー側**: Reveal のクライアント側コンポーネントは、サーバー側コンポーネントを使用してダッシュボードの定義を取得し、定義された各視覚化とフィルターのデータも取得します。

    これが最も簡単な方法であり、最初に SDK を評価するときに推奨される方法です。

  - **クライアント側**: 完全な制御と高い柔軟性が提供されます。カスタム サーバーからコンテンツを取得しながら、クライアント ページでダッシュボードのコンテンツをストリームに提供します。

    この方法を使用すると、たとえば、ユーザーのアクセス許可を確認したり、カスタムなユーザーインターフェイスを表示してダッシュボードを選択したり、ユーザーが使用する .rdash ファイルをアップロードしたりすることができます。クライアント側アプローチの詳細については、[**セットアップと構成 (クライアント)**](~/jp/developer/web-sdk/setup-configuration.html#setup-and-configuration-client)) を参照してください。

### サーバー側アプローチ

まず、クライアント側からダッシュボード ID とダッシュボードを要求しているユーザーの ID の両方を取得します。次に、サーバーで、ダッシュボードの定義を取得し、定義された各視覚化とフィルターのデータを取得します。

ダッシュボードの保存方法 (ファイル システム、データ ベースなど) とどのユーザーに対してダッシュボードへのアクセスを許可するか、 SDK の一部ではないため、ご自身で処理する必要があります。


インターフェイス IRVDashboardProvider を実装する独自のダッシュボード プロバイダーが必要です:

```java
public interface IRVDashboardProvider {
    InputStream getDashboard(String userId, String dashboardId) throws IOException;
    void saveDashboard(String userId, String dashboardId, InputStream dashboardStream) throws IOException;
}
```

ダッシュボードの保存を許可しない場合は、*saveDashboard* の実装を空のままにしておくことができます。

*getDashboard* メソッドはユーザー ID とダッシュボード ID を受け取り、それらを保存するために選択したダッシュボード (ファイル システム、データベースなど) を見つける必要があります。 
最後に、ダッシュボードの内容を含む InputStream を .rdash 形式 (基本的には JSON ドキュメントを含む ZIP ファイル) で返すことが期待されています。


詳細については、[GitHub](https://github.com/RevealBi/sdk-samples-java) の UpMedia サンプルの実装 (upmedia、upmedia-backend-tomcat、upmedia-backendspring の *UpmediaDashboardProvider*) を参照してください。