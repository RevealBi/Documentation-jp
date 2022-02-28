# Reveal SDK for HTML/JavaScript で作業を開始

## 手順 1 - HTML ファイルの作成

1 - お気に入りのコード エディターを開き、新しい HTML ファイルを作成し、`index.html` という名前でファイルを保存します。

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Reveal Sdk - HTML/JavaScript</title>  
</head>
<body>

</body>
</html>
```

## 手順 2 - Reveal JavaScript API の追加

1 - `assets` と呼ばれる新しいフォルダーを作成し、`assets` フォルダー内に `reveal` と呼ばれる別のフォルダーを作成します。

![](images/javascript-create-reveal-folder.jpg)

2 - `%public%/Documents/Infragistics/Reveal/SDK/Web/JS/Client` にあるすべての JavaScript ファイルを以前作成した `assets/reveal` フォルダーにコピーします。

![](images/javascript-copy-reveal-files.jpg)

3 - `index.html` ファイルを変更し、ページの下部に (`</body>` 終了タグの直前) `infragistics.reveal.js` スクリプトを含めます。

```html
<script src="./assets/reveal/infragistics.reveal.js"></script>
```

4 - 残りの Reveal JavaScript API 依存関係をインストールします。

- jQuery 2.2 またはそれ以上

```html
<script src="https://cdn.jsdelivr.net/npm/jquery@3.6.0/dist/jquery.min.js"></script>
```
- Day.js 1.8.15 またはそれ以上

```html
<script src="https://unpkg.com/dayjs@1.8.21/dayjs.min.js"></script>
```

- Quill RTE 1.3.6 またはそれ以上

```html
<link href="https://cdn.quilljs.com/1.3.6/quill.snow.css" rel="stylesheet" type="text/css">    
<script src="https://cdn.quilljs.com/1.3.6/quill.min.js"></script>
```

- Spectrum v1.8.0 またはそれ以上 (オプション) - これは、エンド ユーザーが特定の可視化の背景色を設定できるように UI を有効にする場合にのみ必要です。

``` html
<link href="https://cdnjs.cloudflare.com/ajax/libs/spectrum/1.8.0/spectrum.min.css" rel="stylesheet" type="text/css" >
<script src="https://cdnjs.cloudflare.com/ajax/libs/spectrum/1.8.0/spectrum.min.js"></script>
```

最終の `index.html` ファイルは以下のようになります。

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Reveal Sdk - HTML/JavaScript</title> 
    
    <link href="https://cdn.quilljs.com/1.3.6/quill.snow.css" rel="stylesheet" type="text/css">  

</head>
<body>

    <script src="https://cdn.jsdelivr.net/npm/jquery@3.6.0/dist/jquery.min.js"></script>
    <script src="https://cdn.quilljs.com/1.3.6/quill.min.js"></script>    
    <script src="https://unpkg.com/dayjs@1.8.21/dayjs.min.js"></script>    
    <script src="./assets/reveal/infragistics.reveal.js"></script>   
</body>
</html>
```

## 手順 3 - Reveal ビューの初期化

1 - `index.html` ファイルを変更し、開始 `<body>` タグの後に新しい `<div>` タグを追加して、`id` を `revealView` に設定します。

```html
<div id="revealView" style="height: 920px; width: 100%;"></div>
```

2 - `index.html` ファイルの最後に JavaScript の `Script` タグを追加し、`revealView` を初期化します。

```html
<script type="text/javascript">
    $.ig.RevealSdkSettings.ensureFontsLoadedAsync().then(() => {
        var revealView = new $.ig.RevealView("#revealView");
    });        
</script>
}
```

この JavaScript コードは最初に `$.ig.RevealSdkSettings.ensureFontsLoadedAsync` を呼び出してすべてのフォントが正しく読み込まれたことを確認します。次に、新しい `$.ig.RevealView` を作成し、`#revealView` セレクターを渡すことで、`RevealView` の新しいインスタンスを作成します。

最終の `index.html` ファイルは以下のようになります。

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Reveal Sdk - HTML/JavaScript</title> 
    
    <link href="https://cdn.quilljs.com/1.3.6/quill.snow.css" rel="stylesheet" type="text/css">  

</head>
<body>
    <div id="revealView" style="height: 920px; width: 100%;"></div>

    <script src="https://cdn.jsdelivr.net/npm/jquery@3.6.0/dist/jquery.min.js"></script>
    <script src="https://cdn.quilljs.com/1.3.6/quill.min.js"></script>    
    <script src="https://unpkg.com/dayjs@1.8.21/dayjs.min.js"></script>    
    <script src="./assets/reveal/infragistics.reveal.js"></script>   

    <script type="text/javascript">
        $.ig.RevealSdkSettings.ensureFontsLoadedAsync().then(() => {
            var revealView = new $.ig.RevealView("#revealView");
        });
    </script>
</body>
</html>
```

> [!IMPORTANT]
> Clients apps must set the `$.ig.RevealSdkSettings.setBaseUrl("url-to-server");` to the server address hosting the dashboards if the client is being hosting on a different URL.

## 手順 4 - アプリケーションの実行

`index.html` ファイルをダブルクリックしてデフォルトのブラウザーで Web ページを起動します。

![](images/angular-app-running.jpg)

完了しました! 最初の Reveal SDK アプリケーションを作成しました。

次の手順:
- [新しいダッシュボードの作成](creating-dashboards.md)
- [現在のダッシュボードの読み込み](loading-dashboards.md)

> [!NOTE]
> このサンプルのソース コードは [GitHub](https://github.com/RevealBi/sdk-samples-javascript/tree/main/01-GettingStarted) にあります。
