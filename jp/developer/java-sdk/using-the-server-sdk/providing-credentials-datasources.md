## データ ソースへの資格情報の提供

### 概要

Server SDK では、データ ソースにアクセスするときに使用される一連の資格情報を渡すことができます。

最初の手順は __IRVAuthenticationProvider__ を実装することであり、次に __RevealEngineInitializer.initialize__ メソッドを使用して Reveal を初期化するときにカスタム クラスを設定する必要があります。詳細については、Java セットアップと構成での [Reveal の初期化](https://help.revealbi.io/jp/developer/java-sdk/setup-configuration.html#手順-3---reveal-を初期化します)を参照してください。実際の実装を確認するには、Spring サンプルの __RevealJerseyConfig__ クラス、または [GitHub](https://github.com/RevealBi/sdk-samples-java) の Tomcat に基づくサンプルの __WebAppListener__ を参照してください。

### コード

__UpmediaAuthenticationProvider__ (upmedia、upmedia-backend-tomcat、upmedia-backend-spring のサンプル) を参照として使用する場合、現在のユーザーと資格情報が要求されているデータ ソースの _userId_ を受け取る実装された単一のメソッドを見つけることができます。 

``` java
public class UpmediaAuthenticationProvider implements IRVAuthenticationProvider {
    @Override
    public IRVDataSourceCredential resolveCredentials(String userId, RVDashboardDataSource dataSource) {
        // Returning credentials for a SqlServer data source example:
        if (dataSource instanceof RVSqlServerDataSource) {
            String host = ((RVSqlServerDataSource)dataSource).getHost();
            if (host != null && host.equals("10.10.10.10")) {
                return new RVUsernamePasswordDataSourceCredential("someuser", "somesecret", "somedomain");
            }
        }
        return null;
    }
}
```

上記の例と同様のコードを使用して、データ ソースが MS SQL Server データ ソースであるかどうかを確認し、サーバーのホスト名を確認して、使用する資格情報を返すことができます。

同様のコードですが、Redshift データ ソース用です。

```java
if (dataSource instanceof RVRedshiftDataSource) {
    String host = ((RVRedshiftDataSource)dataSource).getHost();
    if (host != null && host.equals("1.2.3.4")) {
        return new RVUsernamePasswordDataSourceCredential("user", "password");
    }
}
```

### 実装するクラスの選択

使用できるクラスは 3 つあり、すべて __IRVDataSourceCredential__ インターフェイスを実装しています。以下に詳述するように、データ ソースに応じてクラスを選択する必要があります。

| クラス | 例 |
|:-|:-|
| __RVBearerTokenDataSourceCredential__ <br> Oauth 認証に関連付けられています (通常は Oauth アクセス トークンを送信します)。 | Google アナリティクス、Box、Dropbox、Google ドライブ、OneDrive、SharePoint オンライン、OData フィード、ウェブ リソース、REST API。|
| __RVUsernamePasswordDataSourceCredential__ <br> ユーザー/パスワード スタイルの認証 (オプションのドメインを使用) で機能します。 | Microsoft Dynamics CRM オンプレミスおよびオンライン、Microsoft SQL Server、Microsoft Analysis Services Server、MySQL、PostgreSQL、Oracle、Sybase、OData フィード、ウェブ リソース、REST API。
| __RVAmazonWebServicesCredentials__ <br> AWS (Amazon Web Services) と動作します。 | Athena、S3。

### 認証なし

認証なしで匿名のリソースで作業することがあります。この場合、空のコンストラクターを持つ __RVUsernamePasswordDataSourceCredential__ を使用できます。これは、そのクラスで機能するすべてのデータ ソースに対して実行できます。
