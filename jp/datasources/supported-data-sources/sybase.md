---
title: Slingshot で Sybase データ ソースを構成する方法
_description: Slingshot で Sybase データ ソースを構成し、取得してさまざまなダッシュボード ビューで使用する方法を説明します。
_language: ja
---

# Sybase

>[!NOTE] 
>**Web の制限**。*Reveal Web* アプリでは、公的にアクセス可能な Sybase アドレスにのみ接続できます。Sybase アドレスが一般公開 (プライベートまたは会社のイントラネットでホストされているなど) に制限されている場合は、*Reveal Desktop*、*iOS*、または *Android* を使用して接続できます。Reveal を実行しているデバイスは、Sybase アドレスにアクセスできる必要があります。この制限は、*Reveal Embedded* には適用されません。 

## Sybase への接続

Sybase サーバー データ ソースを構成するには、以下の情報が必要です。

<img src="images/add-sybase-as-data-source.png" alt="Configure Sybase database connection" width="50%" class="responsive-img"/>

1.  **[[サーバー](#サーバー情報を見つける方法)]**: コンピューター名またはサーバーを実行しているコンピューターに割り当てられた IP アドレス。

2.  **[ポート]**: 該当する場合、サーバー ポートの詳細。情報が入力されない場合、Reveal はデフォルトでヒント テキスト (5000) のポートに接続します。

3.  **[資格情報]**: [資格情報] を選択した後、Sybase サーバーの資格情報を入力するか、既存の資格情報 (適用可能な場合) を選択できます。

      - **[ユーザー名]**: Sybase サーバーのユーザー アカウントまたはドメインの名前。

      - **[パスワード]**: Sybase サーバーのパスワード。
    
    - **エイリアス**: データ ソース アカウントの名前。以前のダイアログのアカウントのリストに表示されます。

  準備ができたら、**[追加]** を選択してから **[サーバーの追加]** を選択します。

<a name='how-to-find-server'></a>
## サーバー情報を見つける方法

以下の手順でサーバーも確認できます。コマンドはサーバーで実行する必要があることに注意してください。

| WINDOWS                                                                                                         | LINUX                                                                                                         | MAC                                                                  |
| --------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------- |
| 1\. ファイル エクスプローラーを開きます。                                                                                     | 1\. ターミナルを開きます。                                                                                          | 1\. システム環境設定を開きます。                                         |
| 2\. マイコンピューターを右クリックしてプロパティを表示します。                                                                   | 2\. **$hostname** と入力します。                                                                                    | 2\. 共有セクションに移動します。                                 |
| ホスト名は、[コンピューター名、ドメイン、ワークグループ設定] の下に [コンピューター名] として表示されます。 | [ホスト名] と [DNS ドメイン名] が表示されます。Reveal では**ホスト名**のみを含めることに注意してください。| [ホスト名] は、上部の [コンピューター名] の下に表示されます。 |

以下の手順で *IP アドレス*も確認できます。コマンドはサーバーで実行する必要があることに注意してください。

| WINDOWS                              | LINUX                             | MAC                                                           |
| ------------------------------------ | --------------------------------- | ------------------------------------------------------------- |
| 1\. コマンド プロンプトを開きます。           | 1\. ターミナルを開きます。              | 1\. ネットワーク アプリケーションを起動します。                                  |
| 2\. **ipconfig** と入力します。            | 2\. **$ /bin/ifconfig** と入力します。  | 2\. 接続を選択します。                                   |
| **IPv4 アドレス** はあなたの IP アドレスです。 | **Inet addr** はあなたの IP アドレスです。 | **IP アドレス** フィールドに必要な情報が提供されます。 |

## データの設定

### ビューの作業

Reveal を使用すると、テーブル全体から Sybase データを取得できますが、代わりにテーブルまたはテーブルのセットからデータのサブセットを返す特定の[ビュー (英語)](http://infocenter.sybase.com/help/index.jsp?topic=/com.sybase.infocenter.dc32300.1570/html/sqlug/X29678.htm) を選択することもできます。

<img src="images/sybase-views-list.png" alt="Select from Sybase views dialog" class="responsive-img" width="55%"/>

たとえば、**syscacheinfo** ビューには、データベース内のテーブルの 1 つから取得したキャッシュに関する情報が含まれています。

<img src="images/sybase-view-visualization-editor.png" alt="Creating a visualization while using a sybase view" class="responsive-img" width="60%"/>

ビューおよび Sybase の詳細については、[このドキュメント Web サイト (英語)](http://infocenter.sybase.com/help/index.jsp?topic=/com.sybase.infocenter.dc32300.1570/html/sqlug/X29678.htm) を参照してください。

### 保管されたプロシージャの作業

Sybase では、保管されたプロシージャを使用すると、特定のパラメーターを使用してリレーショナル データベースで一連のクエリ ステートメントを実行できます。

たとえば、この場合、ストアド プロシージャでは、ユーザーが *@name* 範囲値を設定する必要があります。

<img src="images/stored-procedure-parameters-sybase.png" alt="Stored Procedure select name" class="responsive-img" width="55%"/>

ストアド プロシージャと Sybase の詳細については、[このドキュメント Web サイト](http://infocenter.sybase.com/help/index.jsp?topic=/com.sybase.infocenter.dc32300.1570/html/sqlug/X39397.htm)を参照してください。

## 表示形式エディターでの作業

データ ソースを追加した後、**表示形式エディター**が表示されます。ここでダッシュボードを作成できます。デフォルトでは、**柱状**表示形式が選択されます。それを選択して、別のチャート タイプを選択できます。

<img src="images/sybase-working-in-visualization-editor.png" alt="Using Sybase data to create a dashboard in the visualization editor" class="responsive-img" width="70%"/>

表示形式の準備ができたら、右上隅のチェックマークをクリックまたはタップして、ダッシュボードとして保存できます。以下の例では、ダッシュボードを **[分析]** > **[ダッシュボード]** > **Statistics** に保存しました。

<img src="images/sybase-my-analytics.png" alt="Sybase dashboard in My Analytics" class="responsive-img" width="70%"/>
