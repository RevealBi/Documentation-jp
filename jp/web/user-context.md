# ユーザー コンテキスト

ユーザー コンテキストは、アプリケーションの認証済みユーザーの ID を表します。ユーザー コンテキストは、`IRVDashboardProvider`、`IRVAuthenticationProvider`、`IRVDataProvider` などの Reveal SDK プロバイダーで使用して、ユーザーが持つアクセス許可を制限できます。ユーザー コンテキストを Reveal SDK に提供するには、[**IRVUserContextProvider**](https://help.revealbi.io/api/aspnet/latest/Reveal.Sdk.IRVUserContextProvider.html) インターフェイスを実装するクラスを作成する必要があります。

## サンプル ユーザー コンテキスト プロバイダー

**Step 1** - `SampleUserContextProvider` は [**IRVUserContextProvider**](https://help.revealbi.io/api/aspnet/latest/Reveal.Sdk.IRVUserContextProvider.html) インターフェイスを実装し、`userId` と一連のプロパティの両方を含む [**RVUserContext**](https://help.revealbi.io/api/aspnet/latest/Reveal.Sdk.RVUserContext.html) オブジェクトを返す `GetUserContext` メソッドを定義します。このプロパティのリストを使用して `someCookieName` の値を保存しています。これにより、後でデータ ソースの資格情報が要求されたときに値を取得できます。

```csharp
    internal class SampleUserContextProvider : IRVUserContextProvider
    {
        public IRVUserContext GetUserContext(HttpContext aspnetContext)       
            {
                //when using standard auth mechanisms, the userId can be obtained using aspnetContext.User.Identity.Name.

                string userIdentityName = aspnetContext.User.Identity.Name;
                string userId = (userIdentityName != null) ? userIdentityName : "guest";

                //RVUserContext is a default implementation of IRVUserContext, which allows to store properties in addition to the userId, these properties can be used later
                //for example in the authentication provider. You could store data related to the current request this way. In this case, we are storing the value of "someCookieName".

                return new RVUserContext(
                    userId,
                    new Dictionary<string, object>() { { "someKey", aspnetContext.Current.Request.Cookies["someCookieName"].Value } });
			}       
    }
```

**手順 2** - `Program.cs` ファイルの `AddReveal` メソッドを更新して、作成した `IRVUserContextProvider` を `RevealSetupBuilder.AddUserContextProvider` メソッドを使用して `RevealSetupBuilder` に追加します。

```csharp
builder.Services.AddControllers().AddReveal( builder =>
{
    builder..AddUserContextProvider<SampleUserContextProvider>();
});
```

[**RevealBI AspNetCore SDK を使用した Web サンプル アプリケーション**](https://github.com/RevealBi/sdk-samples-aspnetcore/blob/590f79ce822755002bf2ccbbdb6e455ab7f1f3c3/Cookies-Auth/README.md)で実装を見つけることができます。
