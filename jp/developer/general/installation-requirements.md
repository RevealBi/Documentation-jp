## インストールと要件

### デスクトップ SDK 要件

Reveal SDK は、.NET バージョン 4.6.2 以降および Visual Studio 2015 以降が必要です。

### ウェブ SDK 要件

Reveal Server SDK は、.NET Framework 4.6.2 以降をターゲットとする .NET Core 2.2 以降のサーバーサイド プロジェクトが必要です。

### Reveal SDK のインストール

ウェブとデスクトップの両方のプラットフォーム用の Reveal SDK
は、[こちら](https://www.revealbi.io/jp)からダウンロードしてください。準備ができたら、インストーラーの手順に従います。

<img src="images/installScreen_desktop.png" alt="installScreen_desktop" width="100%"/>

インストール完了後、`[SDK サンプルを開く]` リンクをクリックしてサンプルを表示できます。

<img src="images/afterInstallScreen_desktop.png" alt="afterInstallScreen_desktop" width="100%"/>

### サンプル

サンプルは、%public%\\Documents\\Infragistics\\Reveal\\SDK\\ にあります。

ここにソリューション ファイル (Reveal.Sdk.Samples.sln) があります。このプロジェクトは、すべての Web、WPF、および WinForms サンプルを組み合わせたものです。

Web の場合、IIS でサンプルを実行し、StartUp プロジェクトを変更するには、ノード パッケージを復元する必要があります。復元するには、ソリューション エクスプローラーでソリューションを右クリックし、\[パッケージを復元\] を選択します。
