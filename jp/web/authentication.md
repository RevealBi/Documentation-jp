# 認証

The Reveal SDK allows you to provide various methods of authentication such as Username/Password and Bearer Token authentication credentials to your data sources by using an authentication provider and registering that provider with the Reveal SDK.

The authentication provider is used to check which data source is requesting authentication credentials, and then return the correct authentication credentials for that specific data source.

**Step 1** - Create the authentication provider.

# [ASP.NET](#tab/aspnet)

```cs
public class AuthenticationProvider: IRVAuthenticationProvider
{
    public Task<IRVDataSourceCredential> ResolveCredentialsAsync(IRVUserContext userContext, RVDashboardDataSource dataSource)
    {
        ...
    }
}
```

# [Java](#tab/java)

```java
public class AuthenticationProvider implements IRVAuthenticationProvider {
	@Override
	public IRVDataSourceCredential resolveCredentials(IRVUserContext userContext, RVDashboardDataSource dataSource) {
        ...	
	}
}
```

# [Node.js](#tab/node)

```javascript
const authenticationProvider = async (userContext: IRVUserContext, dataSource: RVDashboardDataSource) => {
    ...
}
```

***

**Step 2** - Register the authentication provider with the Reveal SDK.

# [ASP.NET](#tab/aspnet)

```cs
builder.Services.AddControllers().AddReveal( builder =>
{
    builder.AddAuthenticationProvider<AuthenticationProvider>();
});
```

# [Java](#tab/java)

```java
RevealEngineInitializer.initialize(new InitializeParameterBuilder().
    setAuthProvider(new AuthenticationProvider()).
    build());
```

# [Node.js](#tab/node)

```javascript
const revealOptions: RevealOptions {
	authenticationProvider: authenticationProvider
};

app.use('/', reveal(revealOptions));
```

***

## ユーザー名/パスワード認証

データ ソースがユーザー名とパスワードの使用を要求する場合、`RVUsernamePasswordDataSourceCredential` クラスのインスタンスを返す必要があります。`RVUsernamePasswordDataSourceCredential` クラスは、**ユーザー名**、**パスワード**、およびオプションで**ドメイン**を定義するコンストラクターのオーバーロードを提供します。

# [ASP.NET](#tab/aspnet)

```cs
public class AuthenticationProvider: IRVAuthenticationProvider
{
    public Task<IRVDataSourceCredential> ResolveCredentialsAsync(IRVUserContext userContext, RVDashboardDataSource dataSource)
    {
        IRVDataSourceCredential userCredential = null;
        if (dataSource is RVPostgresDataSource)
        {
            userCredential = new RVUsernamePasswordDataSourceCredential("postgresuser", "password");
        }
        else if (dataSource is RVSqlServerDataSource)
        {
            userCredential = new RVUsernamePasswordDataSourceCredential("sqlserveruser", "password", "domain");
        }
        return Task.FromResult<IRVDataSourceCredential>(userCredential);
    }
}
```

# [Java](#tab/java)

```java
public class AuthenticationProvider implements IRVAuthenticationProvider {
	@Override
	public IRVDataSourceCredential resolveCredentials(IRVUserContext userContext, RVDashboardDataSource dataSource) {
		if (dataSource instanceof RVPostgresDataSource) {
			return new RVUsernamePasswordDataSourceCredential("postgresuser", "password");
		} 
        else if (dataSource instanceof RVSqlServerDataSource) {
			return new RVUsernamePasswordDataSourceCredential("sqlserveruser", "password", "domain");
		} 
		return null;
	}
}
```

# [Node.js](#tab/node)

```javascript
const authenticationProvider = async (userContext:IRVUserContext, dataSource: RVDashboardDataSource) => {
	if (dataSource instanceof RVPostgresDataSource) {
		return new RVUsernamePasswordDataSourceCredential("postgresuser", "password");
	} else if (dataSource instanceof RVSqlServerDataSource) {
		return new RVUsernamePasswordDataSourceCredential("sqlserveruser", "password", "domain");
	}
	return null;
}
```

***

データ ソースが認証なしで匿名ログインを使用している場合、空のコンストラクターで `RVUsernamePasswordDataSourceCredential` を使用できます。

# [ASP.NET](#tab/aspnet)

```cs
if (dataSource is RVSqlServerDataSource)
{
    userCredential = new RVUsernamePasswordDataSourceCredential();
}
```

# [Java](#tab/java)

```java
if (dataSource instanceof RVSqlServerDataSource) {
    return new RVUsernamePasswordDataSourceCredential();
}
```

# [Node.js](#tab/node)

```javascript
if (dataSource instanceof RVSqlServerDataSource) {
	return new RVUsernamePasswordDataSourceCredential();
}
```

***

`RVUsernamePasswordDataSourceCredential` は、以下のデータ ソースでサポートされます。
- Microsoft Analysis Services サーバー
- Microsoft Dynamics CRM (オンプレミスおよびオンライン)
- Microsoft SQL サーバー
- MySQL
- OData サービス
- Oracle
- PostgreSQL
- REST サービス
- Sybase
- ウェブ リソース

## ベアラー トークン認証

データ ソースがユーザー名とパスワードの使用を要求する場合、`RVBearerTokenDataSourceCredential` クラスのインスタンスを返す必要があります。`RVBearerTokenDataSourceCredential` クラスは、**トークン**と**ユーザー ID** を定義するコンストラクターのオーバーロードを提供します。

# [ASP.NET](#tab/aspnet)

```cs
public class AuthenticationProvider: IRVAuthenticationProvider
{
    public Task<IRVDataSourceCredential> ResolveCredentialsAsync(IRVUserContext userContext, RVDashboardDataSource dataSource)
    {
        IRVDataSourceCredential userCredential = null;
        if (dataSource is RVGoogleDriveDataSource)
        {
            userCredential = new RVBearerTokenDataSourceCredential("fhJhbUci0mJSUzi1nIiSint....", "user@company.com");
        }
        return Task.FromResult<IRVDataSourceCredential>(userCredential);
    }
}
```

# [Java](#tab/java)

```java
public class AuthenticationProvider implements IRVAuthenticationProvider {
	@Override
	public IRVDataSourceCredential resolveCredentials(IRVUserContext userContext, RVDashboardDataSource dataSource) {
        if (dataSource instanceof RVGoogleDriveDataSource) {
            return new RVBearerTokenDataSourceCredential("fhJhbUci0mJSUzi1nIiSint....", "user@company.com");
        }
		return null;
	}
}
```

# [Node.js](#tab/node)

```javascript
const authenticationProvider = async (userContext:IRVUserContext, dataSource: RVDashboardDataSource) => {
    if (dataSource instanceof RVGoogleDriveDataSource) {
        return new RVBearerTokenDataSourceCredential("fhJhbUci0mJSUzi1nIiSint....", "user@company.com");
    }
	return null;
}
```

***

`RVBearerTokenDataSourceCredential` は、以下のデータ ソースでサポートされます。
- Box
- Dropbox
- Google アナリティクス
- Google Drive
- OData サービス
- OneDrive
- REST サービス
- SharePoint オンライン
- ウェブ リソース