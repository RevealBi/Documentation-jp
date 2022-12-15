# ASP.NET Core Server の構成

## インストール

以下の手順では、Reveal SDK を既存の ASP.NET Core プロジェクトにインストールする方法について説明します。

1 - ソリューションまたはプロジェクトを右クリックし、**[ソリューションの NuGet パッケージの管理]** を選択します。

<img src="images/getting-started-nuget-packages-manage.jpg" alt="" width="40%"/>

2 - パッケージ マネージャー ダイアログで **[Browse] (参照)** タブを開き、[NuGet.org](https://www.nuget.org/packages/Reveal.Sdk.AspNetCore/) にある **Reveal.Sdk.AspNetCore** NuGet パッケージをプロジェクトにインストールします。

3 - `Program.cs` ファイルを開き、`using Reveal.Sdk` 名前空間を追加します。次に、既存の `builder.Services.AddControllers()` メソッドに `IMcvBuilder.AddReveal()` の呼び出しを追加します。

```
using Reveal.Sdk;

builder.Services.AddControllers().AddReveal();
```

4 - プロジェクトを右クリックし、**[追加] -> [新しいフォルダー]** を選択します。フォルダーの名前は **「Dashboards」** にしてください。

<img src="images/setting-up-server-create-dashboards-folder.jpg" alt="" width="40%"/>

デフォルトで、Reveal SDK は **Dashboards** フォルダーからすべてのダッシュボードを読み込む規則を使用します。この規則を変更するにはカスタムの `IRVDashboardProvider` を作成します。詳細については、[ダッシュボードの読み込み](loading-dashboards.md)トピックを参照してください。

## エクスポート

ダッシュボードを**画像**、**PDF**、または **PowerPoint** に (プログラムで、またはユーザーの操作を通じて) エクスポートするために、RevealSDK は [Playwright](https://playwright.dev/dotnet/) を内部で使用します。

デフォルトでは、ユーザーがダッシュボードを画像、PDF、または PowerPoint に初めてエクスポートしようとすると、Playwright は Chromium ブラウザーを現在のプラットフォームのデフォルトの場所にダウンロードしようとします。Windows の場合、デフォルトのパスは **%userprofile%/AppData/Local/ms-playwright** です。

このダウンロードには時間がかかり、ダッシュボードをエクスポートしようとする最初のエンドユーザーユーザーに遅延が発生する可能性があります。これは開発中は問題ありませんが、プロダクション環境では望ましくない場合があります。これらのシナリオでは、以下の設定を使用して、エクスポートの動作を微調整できます。

これらの設定は `RevealEmbedSettings.Export` のプロパティで公開されます。
- <a href="/api/aspnet/latest/Reveal.Sdk.ExportConfiguration.html#Reveal_Sdk_ExportConfiguration_CreateChromiumInstancesOnDemand" target="_blank" rel="noopener\">CreateChromiumInstancesOnDemand</a> - これを false に設定すると、アプリの起動時に Playwright の初期化が強制的に行われます。
- <a href="/api/aspnet/latest/Reveal.Sdk.ExportConfiguration.html#Reveal_Sdk_RevealEmbedSettings_ChromiumDownloadFolder" target="_blank" rel="noopener\">ChromiumDownloadFolder</a> - Chromium 実行可能ファイルがダウンロードされるパス。
- <a href="/api/aspnet/latest/Reveal.Sdk.ExportConfiguration.html#Reveal_Sdk_RevealEmbedSettings_ChromiumExecutablePath" target="_blank" rel="noopener\">ChromiumExecutablePath</a> - Chromium 実行可能ファイルがサーバーに前提インストールされているパス。
- <a href="/api/aspnet/latest/Reveal.Sdk.ExportConfiguration.html#Reveal_Sdk_RevealEmbedSettings_MaxConcurrentExportingThreads" target="_blank" rel="noopener\">MaxConcurrentExportingThreads</a> - エクスポートに使用される最大同時スレッド数。
- <a href="/api/aspnet/latest/Reveal.Sdk.ExportConfiguration.html#Reveal_Sdk_RevealEmbedSettings_ExportingTimeout" target="_blank" rel="noopener\">ExportingTimeout</a> - エクスポート操作のタイムアウト期間 (ミリ秒単位)。デフォルト値は 30000 ms。指定されたタイムアウト期間内にエクスポート操作が終了しない場合、エクスポート操作は失敗します。

Playwright と Chromium をサーバーに手動でインストールするには、[Playwright CLI](https://playwright.dev/dotnet/docs/cli) を使用します。

<pre style="background:#141414;color:white;display:inline-block;padding:16x;margin-top:10px;font-family:'Consolas';border-radius:5px;width:100%">
> dotnet tool install --global Microsoft.Playwright.CLI
> playwright install chromium
</pre>

## ログ
Reveal SDK のログを有効にするには、`"Reveal.Sdk": "Debug"` エントリを appsettings.json ファイルに追加します。
```json
{
  "Logging": {
    "LogLevel": {
      "Default": "Information",
      "Microsoft": "Warning",
      "Microsoft.Hosting.Lifetime": "Information",
      "Reveal.Sdk": "Debug"
    }
  },
  ...
}
```
