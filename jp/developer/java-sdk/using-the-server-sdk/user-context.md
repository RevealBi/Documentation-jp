# ユーザー コンテキスト

ユーザー コンテキストは、アプリケーションの認証済みユーザーの ID を表します。ユーザー コンテキストは、`IRVDashboardProvider`、`IRVAuthenticationProvider`、`IRVDataProvider` などの Reveal SDK プロバイダーで使用して、ユーザーが持つアクセス許可を制限できます。ユーザー コンテキストを Reveal SDK に提供するには、`RVContainerRequestAwareUserContextProvider` を拡張し、JAX-RS 仕様から ContainerRequestContext のインスタンスを受け取る抽象メソッドを実装します。

## サンプル ユーザー コンテキスト プロバイダー

**手順 1** - `SampleUserContextProvider` は `RVContainerRequestAwareUserContextProvider` クラスを拡張し、`userId` と一連のプロパティの両方を含む [**RVUserContext**](https://help.revealbi.io/api/java/latest/com/infragistics/reveal/sdk/base/RVUserContext.html) オブジェクトを返す `getUserContext` メソッドを定義します。このプロパティのリストを使用して sessionId を保存しています。これにより、後でデータ ソースの資格情報が要求されたときに取得できます。

```java
public class SampleUserContextProvider extends RVContainerRequestAwareUserContextProvider {

	@Override
	protected RVUserContext getUserContext(ContainerRequestContext context) {
		//look for the session id cookie, this cookie should be automatically added by Tomcat, so it should be always present
		Cookie sessionCookie = context.getCookies().get("JSESSIONID");		

		//when using standard auth mechanisms, the userId can be obtained using: context.getSecurityContext().getUserPrincipal().getName()
		String userPrincipalName = context.getSecurityContext().getUserPrincipal().getName();
		String userId = (userPrincipalName != null) ? userPrincipalName : "guest";

		//RVUserContext allows to store properties in addition to the userId, these properties can be used later
		//for example in the authentication provider, in this case we're including the session id cookie so we 
		//can forward it to the REST data source, see SampleAuthenticationProvider.
		Map<String, Object> properties = new HashMap<String, Object>();
		if (sessionCookie != null) {
			properties.put(sessionCookie.getName(), sessionCookie.getValue());
		}
		return new RVUserContext(userId,properties);
	}
}
```
**手順 2** - `WebAppListener.java` ファイルの `contextInitialized` 関数を更新して、`setUserContextProvider(new SampleUserContextProvider())` メソッドを使用して、作成したばかりの `RVContainerRequestAwareUserContextProvider` を `RevealEngineInitializer` に追加します。

```java
	public void contextInitialized(ServletContextEvent ctx) {
		RevealEngineInitializer.initialize(new InitializeParameterBuilder().
				setUserContextProvider(new SampleUserContextProvider()).
				.build());

		ctx.getServletContext().setAttribute("revealSdkVersion", RevealEngineInitializer.getRevealSdkVersion());
	}
```

[**RevealBI Java SDK を使用して、Tomcat サンプル アプリケーション**](https://github.com/RevealBi/sdk-samples-java/tree/f76481b3578ee95b3949d87e693e2228809daa3e/cookies-auth)で実装を見つけることができます。
