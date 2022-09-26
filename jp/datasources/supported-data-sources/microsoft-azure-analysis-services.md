---
title: Azure Analysis Services をデータ ソースとして使用する方法
_description: Slingshot で Azure Analysis Services データ ソースを構成して使用する方法を説明します。
_language: ja
---

# Microsoft Azure Analysis Services

Azure Analysis Services は、クラウドでエンタープライズ レベルのデータ モデルを提供するサービス (PaaS) としてのフル マネージド プラットフォームです。Reveal の Azure Analysis データ モデルを使用して、ダッシュボードを作成し、データ分析を実行できるようになりました。
## Azure Analysis Services への接続

Reveal で使用される他のデータベース (Microsoft Analysis Services、MySQL、Oracle など) とは異なり、MS Azure Analysis Services は Reveal Web で使用できます。

>[!NOTE]
>**Azure Analysis Services に初めて接続するときの Web の制限**。
>セキュリティ上の制限により、Azure Analysis Services の初期設定と認証のプロセスは、Reveal Web 上では実行できません。最初に、iOS、Android、またはデスクトップ アプリでこのデータ ソースに接続できます。最初の接続後、この Azure Analysis Services のデータを使用してダッシュボードを作成または編集できます。制限はありません。

Azure Analysis Services データ ソースを設定するには、以下の手順を実行する必要があります。

1. Microsoft アカウント (Azure Analysis サーバーに関連付けられたアカウント) に資格情報を提供します。 

2. **[Azure SSAS サーバーの追加]** ダイアログで、サーバーへの **URL** を指定します。

    <img src="images/add-azure-ssas-server.png" alt="Configuring an azure analysis services connection" class="responsive-img" width="50%"/>

    要求される _URL_ は、接続するデータ モデルのデータベースを含むサーバーの完全な名前です。Azure ポータルから*サーバー名をコピー*できます。これを行うには、以下にアクセスしてください:

    *Azure portal* (Azure ポータル) ⇒ 選択したサーバー ⇒ *Overview* (概要) ⇒ *Server Name* (サーバー名)

3. Reveal に戻り、サーバー名を *URL* に貼り付けます。**[サーバーの追加]** ボタンをクリックまたはタップすると、有効になります。  

4. サーバーを追加すると、Analytics はサーバー上のデータベースを読み込んで表示します。ここには、データベースで使用可能なすべてのセマンティック モデルのリストが表示されます。モデルを選択し、**[データを選択]** をクリックまたはタップして**表示形式エディター**に進みます。

   <img src="images/azure-ssas-cubes.png" alt="List of cubes with all the models in them" class="responsive-img" width="60%"/>

## 表示形式エディターでの作業

 ここでは、モデルのデータが 2 つのカテゴリで表示されます:

- **ディメンション**には定性的データ (Country、Name、Product など) が含まれます。

- **メジャー**は数値データで構成されます。

<img src="images/azure-ssas-visualization-editor.png" alt="Using azure ssas data in the visualization editor" class="responsive-img" width="75%"/>

デフォルトでは、**柱状**表示形式が選択されます。それをクリックまたはタップして、ドロップダウン メニューから別のチャート タイプを選択できます。

表示形式の準備ができたら、右上隅のチェックマークをクリックまたはタップして、ダッシュボードとして保存できます。以下の例では、ダッシュボードを **[分析]** > **[ダッシュボード]** > **Accounting** に保存しました。

<img src="images/azure-ssas-my-analytics.png" alt="A dashboard created while using azure ssas data in the My Analytics section" class="responsive-img" width="75%"/>
