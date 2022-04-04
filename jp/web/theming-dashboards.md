# ダッシュボードのテーマ設定

## 定義済みのテーマ

Reveal SDK には、適用できる 4 つの定義済みテーマが付属しています。

| テーマ              | RevealView                                                   |
| -----              | :--------:                                                   |
| **Mountain Light** | <img src="images/theming-mountain-light.jpg" width="640" />  |
| **Mountain Dark**  | <img src="images/theming-mountain-dark.jpg" width="640" />   |
| **Ocean Light**    | <img src="images/theming-ocean-light.jpg" width="640" />     |
| **Ocean Dark**     | <img src="images/theming-ocean-dark.jpg" width="640" />      |

## テーマの適用

定義済みのテーマを適用するには、`RevealSdkSetting.theme` プロパティを優先テーマのインスタンスに割り当てる必要があります。

##### Mountain Light

```javascript
$.ig.RevealSdkSettings.theme = new $.ig.MountainLightTheme();
```

##### Mountain Dark

```javascript
$.ig.RevealSdkSettings.theme = new $.ig.MountainDarkTheme();
```

##### Ocean Light

```javascript
$.ig.RevealSdkSettings.theme = new $.ig.OceanLightTheme();
```

##### Ocean Dark

```javascript
$.ig.RevealSdkSettings.theme = new $.ig.OceanDarkTheme();
```

> [!NOTE]
> `RevealSdkSetting.theme` プロパティは静的プロパティであり、アプリケーション内の `RevealView` のすべてのインスタンスに適用されます。

## カスタム テーマ

Reveal SDK を既存のアプリケーションに埋め込む場合、ダッシュボードがアプリケーションのルックアンドフィールと一致していることが重要です。定義済みの Reveal SDK テーマのいずれかがアプリケーションのテーマと一致しない場合は、アプリケーションのルックアンドフィールにより近いカスタム テーマを作成できます。

テーマは、`RevealTheme` タイプのクラスです。これにより、Reveal SDK UI コントロールのさまざまな要素の色とフォントを定義できます。

`RevealTheme` には次のプロパティがあります:

| 名前                                              | 説明                                                                                                    |
| ----                                              | -----------                                                                                                    |
| **chartColors**                                   | 表示形式でシリーズを示すために使用される色。色の数に制限はありません。すべての色が表示形式で使用されると、Reveal はこれらの色の新しい色合いを自動生成します。これにより、色が重複せず、各値に独自の色が設定されます。           |
| **accentColor**                                   | Reveal のデフォルトのアクセント色は、[+ ダッシュボード] ボタンやその他のインタラクティブなアクションで確認することができる青の色合いです。アプリケーションで使用するのと同じアクセント色に一致するように色を変更できます。                                       |
| **dashboardBackgroundColor**                      | ダッシュボードの背景色を設定します。これはメインの背景色です。                                |
| **visualizationBackgroundColor**                  | 表示形式の背景色を設定します。これは二番目のな背景色です。                         |
| **conditionalFormatting**                         | 条件付き書式を使用するときに設定できる境界のデフォルトの色を変更します。                        |
| **regularFont**                                   | 通常のフォント スタイルを設定します。                                                                                   |
| **boldFont**                                      | 太字のフォント スタイルを設定します。                                                                                      |
| **mediumFont**                                    | 中のフォント スタイルを設定します。                                                                                    |
| **fontColor**                                     | フォントの色を設定します。                                                                                    |
| **highlightColor**                                | 特定のダッシュボード シナリオ (予測および外れ値の統計関数) の強調色を設定します。     |
| **useRoundedCorners**                             | ボタン、ツールチップ、コンテナ、表示形式などの隅が丸められています。false に設定すると、コーナーは四角になります。                                                                                                                                                                        |

> [!NOTE]
> テーマのプロパティを更新するとき、または実行時に新しいテーマを適用するときは、テーマの変更を `RevealView` に適用するために、`RevealView.refreshTheme` メソッドを呼び出す必要があります。

### 既存のテーマのクローン

既存のテーマの値に基づいてテーマを作成する場合は、変更を加える前に現在の `RevealTheme` のクローンを作成できます。  テーマのクローンを作成するには、`RevealTheme.clone()` メソッドを使用するだけです。テーマのクローンを作成したら、テーマのプロパティを設定して、新しいテーマとして使用できます。

```javascript
function cloneCurrentTheme() {
    var theme = $.ig.RevealSdkSettings.theme.clone();

    theme.fontColor = "#0000cc";
    theme.accentColor = "#009900";
    theme.dashboardBackgroundColor = "#ffff66";
    theme.visualizationBackgroundColor = "#cccccc";

    theme.chartColors = ["rgb(192, 80, 77)", "rgb(101, 197, 235)", "rgb(232, 77, 137)"];

    return theme;
}
```

テーマのクローンを作成して変更し、既存のテーマを変更したら、テーマを適用できます。

```javascript
$.ig.RevealSdkSettings.theme = this.cloneCurrentTheme();
```

> [!NOTE]
> `rgb(255, 255, 255)` (RGB) または `#000000` (HEX) 色のいずれかを使用して、色の値を指定できます。

### カスタム テーマの作成

より保守しやすく、再利用と共有が容易なテーマが必要な場合は、カスタム テーマを作成することをお勧めします。カスタム テーマの作成は、`RevealTheme` の新しいクラス インスタンスを作成し、そのプロパティを変更することで実現できます。

カスタム テーマの例を次に示します:

```javascript
function createCustomTheme(){
    var theme = new $.ig.RevealTheme();

    theme.fontColor = "#ff0000";
    theme.accentColor = "rgb(192, 80, 77)";
    theme.dashboardBackgroundColor = "#000000";
    theme.visualizationBackgroundColor = "rgb(153, 255, 255)";

    theme.chartColors = ["rgb(192, 80, 77)", "rgb(101, 197, 235)", "rgb(232, 77, 137)"]

    theme.mediumFont = "Gabriola";
    theme.boldFont = "Wingdings";

    return theme;
};
```

カスタム テーマを作成したら、テーマを適用できます。

```javascript
$.ig.RevealSdkSettings.theme = this.createCustomTheme();
```

> [!NOTE]
> このサンプルのソース コードは [GitHub](https://github.com/RevealBi/sdk-samples-javascript/tree/main/ThemingDashboards) にあります。