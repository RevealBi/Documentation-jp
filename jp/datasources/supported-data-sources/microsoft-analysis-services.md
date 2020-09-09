## Microsoft Analysis Services

Microsoft SQL Analysis Services (SSAS) は、Microsoft SQL Server の OLAP (同時に複数のデータベース システムからの情報のオンライン分析処理) およびデータ マイニング ツールです。

>[!NOTE] Microsoft Analysis Services は Reveal の Web バージョンでサポートされていません。

### Microsoft Analysis Services データソースの構成

Microsoft Analysis Services データソースを構成するときにサーバー設定に基づいて使用できるモジュールが 2 つあります - [*Native*](#native) および [*HTTP*](#http)。

Native および HTTP モードの詳細については、[Microsoft Instance Management ヘルプ](https://docs.microsoft.com/en-us/sql/analysis-services/instances/connect-to-analysis-services?view=sql-server-2017)をご覧ください。

<a name='native'></a>
#### Native の使用

Microsoft Analysis Services データソースを *Native* モード用に構成するため、以下の情報が必要です。

![Configure Microsoft Analysis Services connection](images/microsoft-analysis-native-configuration.png)

1. データ ソースの*デフォルト名*: データ ソース名は前のダイアログのアカウントのリストに表示されます。デフォルトでは、Reveal は *Microsoft Analysis Services* という名前を付けます。好みに合わせて変更できます。

2.  **サーバー**: サーバーが実行されているコンピューターのホスト名または IP アドレスです。

    以下の手順で*ホスト名*情報も確認できます。コマンドはサーバー マシンで実行する必要があることに注意してください。

    | WINDOWS                                                                                                         | LINUX                                                                                                         | MAC                                                                  |
    | --------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------- |
    | 1\. ファイル エクスプローラーを開きます。                                                                                     | 1\. ターミナルを開きます。                                                                                          | 1\. システム環境設定を開きます。                                         |
    | 2\. [マイ コンピューター] \> [プロパティ] を右クリックします。                                                                   | 2\. **$hostname** を入力します。                                                                                     | 2\. 共有セクションへ移動します。                                 |
    | ホスト名は、*コンピューター名、ドメインおよびワークグループの設定* セクションの下に 「コンピューター名」 として表示されます。 | ホスト名と DNS ドメイン名が表示されます。Reveal には **ホスト名** のみを含めるようにしてください。 | ホスト名は、上部のコンピューター名の下に表示されます。 |



  以下の手順で *IP アドレス*も確認できます。コマンドはサーバー マシンで実行する必要があることに注意してください。

  | WINDOWS                              | LINUX                             | MAC                                                           |
  | ------------------------------------ | --------------------------------- | ------------------------------------------------------------- |
  | 1. コマンド プロンプトを開きます。            | 1. ターミナルを開きます。               | 1. ネットワーク アプリケーションを起動します。                                   |
  | 2. **ipconfig** を入力します。              | 2. **$ /bin/ifconfig** を入力します。    | 2. 接続を選択します。                                    |
  | **IPv4 Address** は IP アドレスです。 | **Inet addr** は IP アドレスです。 | **IP アドレス** フィールドに必要な情報が含まれます。 |


3.  (オプション) の**ポート**: サーバー ポートの詳細。情報が入力されない場合、Reveal はデフォルトでヒント テキスト (2383) のポートに接続します。

4.  **資格情報**: *資格情報*を選択した後、Microsoft Analysis Services の資格情報を入力するか、既存の資格情報 (適用可能な場合) を選択できます。

<a name='http'></a>
#### HTTP の使用

Microsoft Analysis Services データソースを *HTTP* モード用に構成するため、以下の情報が必要です。

![Configure Microsoft Analysis HTTP mode connection](images/miscrosoft-analysis-http-config.png)

1.  **データ ソース名**: このフィールドはデータソース リストに表示されます。デフォルト名: *Microsoft Analysis Services*。

2.  **URL**: サーバーの HTTP eService URL。例: *10.1.0.15/olap/msmdpump.dll*。

3.  **資格情報**: Analysis Services サーバーのユーザーアカウントの資格情報。

### データベースの構成

Analysis Services サーバーの資格情報が確認されたら、Reveal はサーバー上のデータベースを読み込んで表示します。

![MSAnalysisDatabases\_All](images/MSAnalysisDatabases_All.png)

データベースを選択し、*続行*をクリックして設定します。

![MSAnalysisCubes\_All](images/MSAnalysisCubes_All.png)

*データベースの設定*ダイアログでデータベース*キューブ*を選択します。

#### データ キューブの概要

データ キューブは、多次元データを保存および表現するために使用されます。データの表示、分析、および計算に 2 つの次元が使用される (行と列の形式で配置される) 2 次元のデータ モデルとは異なり、データ キューブには 3 つ以上の次元があります。

データ キューブの概念は、ユーザーが利用できるデータの次元表すために使用されます。
たとえば、「売上」 は製品カテゴリ、地理、日付、顧客などの**次元**で測定できます。この場合、「売上」 はデータ キューブの**測定**属性です。

Microsoft Analysis データ ソースの操作方法の詳細については、[このトピック](working-with-microsoft-analysis-services.md) を参照してください。
