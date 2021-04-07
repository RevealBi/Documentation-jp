## サーバー側エクスポートの構成

Java SDK は、ダッシュボードをさまざまな形式 (Image、PDF、PPT、Excel) にエクスポートするためにいくつかのネイティブ コンポーネントを使用します。

- **画像のエクスポート**には [Playwright for Java (英語)](https://github.com/microsoft/playwright-java) を使用します。

- **PDF、PPT、および Excel ドキュメントのエクスポート**には、ExportTool (ネイティブ アプリケーション) を使用します。

#### エクスポートの準備

ダッシュボードを初めて開くと、**Playwright と ExportTool の両方が必要なダウンロードを自動的にトリガーします**。ただし、プラットフォームによっては、事前にインストールする必要がある依存関係があり、サーバー環境によって外部ダウンロードが制限される場合があり、これらのツールを手動でセットアップする必要があります。

### Playwright の構成
Playwright は必要なバイナリを自動的にダウンロードします。ただし、手動による構成が必要な場合や、その構成 (または調整) の詳細については、[Playwright のドキュメント (英語)](https://playwright.dev/java/docs/installation)を参照してください。

### macOS の依存関係

macOS に必要なライブラリは **libgdiplus** のみです。インストール情報は[こちら](https://docs.microsoft.com/ja-jp/dotnet/core/install/macos#libgdiplus)を参照してください。

### Linux の依存関係

Linux には複数のネイティブ ライブラリへの依存関係があります。インストールする必要がある依存関係の正確なリストは、使用するディストリビューション、バージョン、および以前にインストールしたパッケージのリストによって異なります。

以下は、基本的な Ubuntu 18.0.4 ディストリビューションに必要なライブラリのリストです。

```shell
sudo apt-get update

sudo apt-get install -y libgdiplus\
        libatk1.0-0\
        libatk-bridge2.0-0\
        libxkbcommon0\
        libxcomposite1\
        libxdamage1\
        libxfixes3\
        libxrandr2\
        libgbm1\
        libgtk-3-0\
        libpango-1.0-0\
        libcairo2\
        libgdk-pixbuf2.0-0\
        libatspi2.0-0    

sudo apt-get install -y --no-install-recommends xvfb 
```

必要に応じて、ログ ファイルに含まれるエラーから、見つからないライブラリに関する詳細情報を取得できます。

その他の環境では、以下もインストールする必要があります。

```shell
sudo apt-get install -y --allow-unauthenticated libc6-dev

sudo apt-get install -y --allow-unauthenticated libx11-dev
```

### ExportTool の手動設定

以下の手順は、以下のシナリオでのみ必要です。
- 自動ダウンロード メカニズムに問題がある場合
- すべてを事前にインストールしておく必要がある場合

#### 手順

1. ご使用のプラットフォームに必要なバイナリ ([Windows](https://download.infragistics.com/reveal/builds/sdk/java/ExportTool/1.0.0/win-x64.zip)、[Linux](https://download.infragistics.com/reveal/builds/sdk/java/ExportTool/1.0.0/linux-x64.zip)、または [macOS](https://download.infragistics.com/reveal/builds/sdk/java/ExportTool/1.0.0/osx-x64.zip)) をダウンロードします。
2. Web アプリケーションが実行されているサーバーのディレクトリにファイルを解凍します (ユーザーはそのディレクトリにアクセスできる必要があります)。
3. zip ファイルを抽出した後、**ExportTool** を以下の場所で取得できます: \<*dir*>/\<*version*>/\<*arch*>/ExportTool。例:
   ```shell
   <dir>/1.0.0/linux-x64/ExportTool.
   ```


4. Reveal の初期化時に、zip ファイルを抽出したディレクトリを設定します。以下のコード スニペットに似ています。

```java
String exportToolDir = "<dir>";
RevealEngineInitializer.initialize(
  new InitializeParameterBuilder()
    .setAuthProvider(new UpmediaAuthenticationProvider())
    .setUserContextProvider(new UpmediaUserContextProvider())
    .setDashboardProvider(new UpmediaDashboardProvider())
    .setLicense("SERIAL_KEY_TO_BE_USED")
    .setExportToolContainerPath(exportToolDir)
    .build());
```

または、以下に示すように **reveal.exportToolContainerPath** システム プロパティでディレクトリを指定できます。

```java
java -Dreveal.exportToolContainerPath=<dir> -jar target/upmedia-backend-spring.war
```
