## カスタム表示形式

Reveal は、グリッド ビュー、ゲージ ビュー、マップ ビュー、複数のチャート タイプなど、複数のデータ可視化コンポーネントを提供します。既成またはサポートされる方法以外の可視化を使用したい場合があります。そのような場合に Reveal ではカスタムに可視化するコンポーネントがサポートされており、Reveal ダッシュボードの一部として表示形式に表示します。

### サンプル DIY 表示形式

<style type="text/css">
.tg  {border-collapse:collapse;border-spacing:0;}
.tg td{border-color:black;border-style:solid;border-width:1px;font-family:Arial, sans-serif;font-size:14px;
  overflow:hidden;padding:10px 5px;word-break:normal;}
.tg th{border-color:black;border-style:solid;border-width:1px;font-family:Arial, sans-serif;font-size:14px;
  font-weight:normal;overflow:hidden;padding:10px 5px;word-break:normal;}
.tg .tg-2ovq{background-color:rgb(255, 255, 255);color:rgb(0, 0, 0);text-align:left;vertical-align:top}
.tg .tg-spkm{background-color:rgb(255, 255, 255);color:rgb(73, 85, 85);text-align:left;vertical-align:top}
.tg .tg-x3gl{background-color:rgb(249, 249, 249);color:rgb(73, 85, 85);text-align:left;vertical-align:top}
</style>
<table class="tg">
<thead>
  <tr>
    <th class="tg-x3gl"><br>カスタム フォント、タイトル、および幅のテーブル<br><img src="images/HRDashboardEmployeesDIY_All.png" alt="Image" width="343" height="275"></th>
    <th class="tg-x3gl"><br>州別の米国の人口の Cloropleth マップ<br><img src="images/StatePopulation_all.png" alt="Image" width="400" height="275"></th>
  </tr>
</thead>
<tbody>
  <tr>
    <td class="tg-spkm"><br>州別のブラジルの人口の Cloropleth マップ<br><img src="images/BrazilStatePopulation_all.png" alt="Image" width="343" height="275"></td>
    <td class="tg-2ovq"><br>世界の GDP の Cloropleth マップ<br><img src="images/WorldPopulationGDP_All.png" alt="Image" width="400" height="275"></td>
  </tr>
</tbody>
</table>

### カスタム表示形式の使用方法

1. **[カスタム] 表示形式選択する**。 
このオプションを見つけるには、ウィジェット エディター内の表示形式セクションを開きます。

   <img src="images/custom-visualization-access.png" alt="Selecting the Custom Visualization in Reveal" width="80%"/>

2. **実装をポイントする**。  
必要なカスタム表示形式を生成する Web ページの URL を追加します。

   <img src="images/custom-visualization-config.png" alt="Showing the Custom Visualization configuration screen within Reveal" width="80%"/>

   URL はパブリック アクセス可能であり、HTTPS:// プロトコルを使用する必要があることに注意してください。さらに、カスタム HTML で参照される各リソースは同じプロトコルを使用する必要があります。


### カスタム Web ページと Reveal
これらのカスタム Web ページは、サポートされるデータソースから Reveal で取得したデータにアクセスできます。カスタム表示形式は、それを目的に Javascript API とインタラクティブに動作します。

カスタム Web ページは、パブリック URL アドレスまたはイントラネットの内部共有場所として参照できます。

>[!NOTE]
>**Reveal Web の制限/要件**
>Reveal Web は、コンポーネントがパブリック URL でホストされているカスタム表示形式のみを描画できます。

ここに、カスタム HTML 表示形式に関する[**ステップバイステップのチュートリアル**](diy-visualization-step-by-step.md)があります。この基本的な HelloWorld サンプルは、Reveal から取得したデータセットを使用してテーブルを生成します。
