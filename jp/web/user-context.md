# ユーザー コンテキスト

ユーザー コンテキストは、アプリケーションの認証済みユーザーの ID を表します。ユーザー コンテキストは、`IRVDashboardProvider`、`IRVAuthenticationProvider`、`IRVDataProvider` などの Reveal SDK プロバイダーで使用して、ユーザーが持つアクセス許可を制限できます。

Reveal SDK 内のユーザー コンテキストは、`IRVUserContext` インターフェイスと `RVUserContext` オブジェクトによって表されます。`RVUserContext` は `IRVUserContext` のデフォルトの実装であり、現在のユーザーのユーザー ID を格納する機能を提供します。`RVUserContext` オブジェクトは、認証プロバイダーなど、Reveal SDK の他の領域で使用されるリクエストに関連する追加のプロパティを保存する機能も提供します。

**手順 1** - ユーザー コンテキスト プロバイダーを作成します。

# [ASP.NET](#tab/aspnet)

```cs
internal class UserContextProvider : IRVUserContextProvider
{
    public IRVUserContext GetUserContext(HttpContext aspnetContext)       
    {
        //when using standard auth mechanisms, the userId can be obtained using aspnetContext.User.Identity.Name.
        var userIdentityName = aspnetContext.User.Identity.Name;
        var userId = (userIdentityName != null) ? userIdentityName : "guest";
        
        var props = new Dictionary<string, object>() { { "some-property", aspnetContext.Current.Request.Cookies["some-cookie-name"].Value } };

        return new RVUserContext(userId, props);
    }    
}
```

# [Java](#tab/java)

```java
public class UserContextProvider extends RVContainerRequestAwareUserContextProvider {
	@Override
	protected IRVUserContext getUserContext(ContainerRequestContext requestContext) {
        // this can be used to store values coming from the request.
		var props = new HashMap<String, Object>();
		props.put("some-property", "some-value");

		return new RVUserContext("user identifier", props);
	}
}
```

# [Node.js](#tab/node)

```javascript
const userContextProvider = (request:IncomingMessage) => {
	// this can be used to store values coming from the request.
    var props = new Map<string, Object>();
	props.set("some-property", "some-value"); 
	
	return new RVUserContext("user identifier", props);
};
```
***

**手順 2** - ユーザー コンテキスト プロバイダーを Reveal SDK に登録します。

# [ASP.NET](#tab/aspnet)

```cs
builder.Services.AddControllers().AddReveal( builder =>
{
    builder..AddUserContextProvider<UserContextProvider>();
});
```

# [Java](#tab/java)

```java
RevealEngineInitializer.initialize(new InitializeParameterBuilder().
    setUserContextProvider(new UserContextProvider()).
    build());
```

# [Node.js](#tab/node)

```javascript
const revealOptions: RevealOptions {
	userContextProvider: userContextProvider
};
app.use('/reveal-api/', reveal(revealOptions));
```
***
