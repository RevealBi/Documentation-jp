---
title: Slingshot Ad-hoc Hierarchies – Add, Create and Analyze Faster
_description: Create new hierarchies in Slingshot and analyze your data in charts, gauges, and grid views.
_language: ja
---

# アドホック階層

Reveal は年月日の日付フィールドの階層を自動的に作成しますが、他のタイプのフィールドでは発生しません。アドホック階層により、ユーザーはチャート、ゲージ、およびグリッドビューでデータを分析でき、データエディターの [行] プレースホルダーにあるフィールドを使用して新しい階層を作成できます。

<img src="images/ad-hoc-hierarchies_All.png" alt="Ad Hoc Hierarchies example in the Visualization editor" class="responsive-img"/>

この機能は、Analysis Services などの多次元データ ソースではなく、プレーン データ ソース (SQLテーブル、Excel スプレッドシート、CSVファイルなど) に適用されます。
これらの場合、階層はサーバー側で定義され、Reveal は展開およびドリル操作をサポートします。

>[!NOTE]
>アドホック階層は、テキストとラジアル ゲージ、および Web、グリッド チャート、テキスト ビューを**サポートされません**。

## アドホック階層の有効化

アドホック階層を有効にするには、データ エディターのプレースホルダーの **[階層の追加]** セクションにフィールドをドラッグアンドドロップします。これを設定するとデータ テーブルの構成および動作が変わります。

<img src="images/reveal-adhoc-hierarchies_all.png" alt="Reveal Ad-hoc Hierarchies table" class="responsive-img"/>

上記のスクリーンショットのように、単一の列が複数の列を置き換えます。
スクリーンショットに示されている例では、ドリル アップおよびドリル ダウンできるだけでなく、Department を展開して Office を表示することもできます。

## サポートされている表示形式

アドホック階層は、以下のものを除くすべての表示形式に追加できます。

  - 円型ゲージ

  - グリッド チャート

  - テキスト ゲージ

  - テキスト ビュー

  - 画像チャート
