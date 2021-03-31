## インストールと要件

### デスクトップ SDK 要件

- Reveal SDK は、.NET バージョン 4.6.2 以降および Visual Studio 2015 以降が必要です。

### ウェブ SDK .NET 要件

- Reveal Server SDK は、.NET Framework 4.6.2 以降をターゲットとする .NET Core 2.2 以降のサーバーサイド プロジェクトが必要です。

### Reveal デスクトップとウェブ .NET SDK のインストール

ウェブとデスクトップの両方のプラットフォーム用の Reveal SDK
は、[こちら](https://www.revealbi.io/jp)からダウンロードしてください。準備ができたら、インストーラーの手順に従います。

<img src="images/installScreen_desktop.png" alt="installScreen_desktop" width="50%"/>

インストール完了後、`[SDK サンプルを開く]` リンクをクリックしてサンプルを表示できます。

<img src="images/afterInstallScreen_desktop.png" alt="afterInstallScreen_desktop" width="50%"/>

#### サンプル

サンプルは、%public%\\Documents\\Infragistics\\Reveal\\SDK\\ にあります。

ここにソリューション ファイル (Reveal.Sdk.Samples.sln) があります。このプロジェクトは、すべての Web、WPF、および WinForms サンプルを組み合わせたものです。

Web の場合、IIS でサンプルを実行し、StartUp プロジェクトを変更するには、ノード パッケージを復元する必要があります。復元するには、ソリューション エクスプローラーでソリューションを右クリックし、\[パッケージを復元\] を選択します。


### Web SDK JAVA Requirements
- [Java SDK](https://www.oracle.com/java/technologies/javase-downloads.html) 11.0.10 and up recommended.
- [Maven](https://maven.apache.org/download.cgi) 3.6.3 and up recommended
 
### Installing JAVA SDK

Reveal Java SDK is distributed as a set of [Maven](https://maven.apache.org/what-is-maven.html) modules. To work with the SDK libraries, you need to add a reference to Reveal's Maven Repository and also a dependency in your Maven pom.xml file.

#### Samples
The **UpMedia samples** illustrate how to use the JAVA SDK, you can get them from GitHub [here](https://github.com/RevealBi/sdk-samples-java).

For details about how to run the UpMedia samples, please follow this [link](~/jp/developer/java-sdk/running-upmedia-samples.md).

