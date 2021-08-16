# 概要

Web アプリケーションに Reveal を埋め込む場合、2 つのコンポーネントが常に関係しているため、アーキテクチャはネイティブ アプリよりも少々複雑になります:

  - **Reveal クライアント SDK**: ウェブ アプリケーションに統合される必要がある JavaScript ライブラリのセット。現在サポートされているフレームワークは、jQuery、Angular、および React です。

  - **Reveal サーバー SDK**: サーバー アプリケーションに統合されるサーバー側コンポーネント。現在のライブラリは JAVA SDK 11+ を必要とし、[Maven (英語)](https://maven.apache.org/what-is-maven.html) モジュールのセットとして配布されます。

次の図では、Reveal Web SDK を埋め込んだ Web アプリケーションのアーキテクチャを可視化しています:

<img src="images/sdk_web_diagram_web.png" alt="Reveal Web Architecture diagram" class="responsive-img"/>

上記の示したように、SDK はネイティブ アプリケーションとほとんど同じように機能します。違いは、一部のコールバックはクライアント側で呼び出され (データポイントがクリックされたときに送信されるイベントなど)、その他はサーバー側で呼び出される (ダッシュボードのロードまたはメモリ内データの提供のためのコールバックなど) 点です。

<a name='host-client-server-separate'></a>
## クライアント側とサーバー側の部分のホスト (異なるサーバーを利用)

クライアント側とサーバー側のパーツを個別に、たとえば異なる URL でホストできます。

これには、以下のようにウィンドウ オブジェクトのプロパティを設定します:

``` js
$.ig.RevealSdkSettings.setBaseUrl("http://localhost:8080/upmedia/reveal-api");
```

使用される形式は **http://**[server]**:**[port]**/**[application]**/reveal-api** であることに注意してください。プロパティを正しく設定するには、**/reveal-api** を含める必要があります。

このプロパティは、[$.ig.RevealView のインスタンス化](~/jp/developer/web-sdk/setup-configuration.html#instantiating-the-web-client-sdk)**の前に**設定します。
