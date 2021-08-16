# UpMedia サンプルの実行

GitHub から <a href="https://github.com/RevealBi/sdk-samples-java" target="_blank" rel="noopener"> UpMedia サンプル</a>を取得した後、実行に役立つ詳細情報を以下に示します。


## Tomcat の UpMedia サンプル アプリケーション

### 要件

- <a href="https://www.oracle.com/java/technologies/javase-downloads.html" target="_blank" rel="noopener"> Java SDK (英語) </a> 11.0.10 以降を推奨します。
- <a href="https://tomcat.apache.org/download-90.cgi" target="_blank" rel="noopener"> Tomcat (英語) </a> 9.0.41 以降を推奨します。
- <a href=" https://www.eclipse.org/downloads/packages/" target="_blank" rel="noopener"> Eclipse for Enterprise Java Developers (英語) </a> バージョン 2020-12 以降を推奨します。
- Maven リポジトリと依存関係を追加する必要があります。詳細については、[セットアップと構成](setup-configuration.html#maven-dependency)を参照してください。
 
### 手順

1. **プロジェクトを読み込みます。**
   1. Eclipse で、*File > Import > Existing Projects into Workspace* に移動します。
   2. *Select root directory* で、Reveal の SDK パスを選択し、*UpMedia* プロジェクトも選択します。
   3. *Copy projects into workspace* オプションをチェックします。
   4. [Finish] をクリックします。

    プロジェクトが読み込まれ、検査する準備ができました。

2. **Tomcat でプロジェクトを実行する**
   1. UpMedia プロジェクトで *Run on Server* を右クリックします。
   2. Tomcat 9 を選択し、Tomcat のインストール パスへのルート パスを設定します。
   3. デフォルト設定でプロジェクトを実行します。  

3. **サンプルをブラウザーで可視化します。**
   - Eclipse の内部ブラウザーには Windows に関する既知の問題があります。代わりに Google Chrome または別のブラウザーを使用してください (デフォルトの URL は http://localhost:8080/upmedia です)。


WAR ファイルを使用する代替手順:
1. *Run As -> Maven build* に移動します。
2. *package* ゴールを使用します。
3. 作成した WAR ファイルを手動で Tomcat に配備します。


## Spring Backend を使用した UpMedia React のサンプル

### 要件

- <a href="https://www.oracle.com/java/technologies/javase-downloads.html" target="_blank" rel="noopener"> Java SDK (英語) </a> 11.0.10 以降を推奨します。
- <a href="https://nodejs.org/en/download/" target="_blank" rel="noopener"> NodeJS (英語) </a> 14.15.4 以降を推奨します。NPM バージョン 6.14.10 を推奨します。
- Maven リポジトリと依存関係を追加する必要があります。詳細については、[セットアップと構成](setup-configuration.html#maven-dependency)を参照してください。

### 手順

1. **Spring アプリケーションを実行します。**
   1. *upmedia-backend-spring* フォルダーで Spring Boot アプリケーションを特定します。
   2. 以下のコマンドを実行してサンプル アプリケーションを実行します。 
   
    ```bash
    mvn spring-boot:run
    npm start
   ```
   3. http://localhost:8080/upmediabackend/reveal-api/DashboardFile/Sales にアクセスしてサーバーを確認します。その結果、Sales サンプル ダッシュボードの JSONド キュメントを取得します。
   Reveal サービス */upmediabackend/reveal-api/* にあります。

2. **React アプリケーションを実行します。**
   1. *upmedia-react* フォルダーで React アプリケーションを特定します。
   2. React アプリケーションを通常通りに実行します。

    ```bash
    npm install
    npm start
   ```
   3. http://localhost:3000 で React アプリケーションにアクセスします。

以下のコンポーネントをお試しください。
- **Filters**: 既存のダッシュボードを開き、フィルタリング エクスペリエンスをカスタマイズする方法を示します。
- **Linking**: 別のダッシュボードへのリンクを持つ既存のダッシュボードを開く方法、およびリンクを正しく構成する方法を示します。
- **CreateDashboard**: ダッシュボード エディターを開いて新しいダッシュボードをゼロから作成する方法を示します。また、新しい表示形式を作成するときにユーザーに表示されるデータ ソースのリストを設定する方法も示します。

Reveal の Web クライアント SDK の詳細については、[こちら](~/jp/developer/web-sdk/overview.md)を参照してください。

## Tomcat Backend を使用した UpMedia React のサンプル

### 要件

- <a href="https://www.oracle.com/java/technologies/javase-downloads.html" target="_blank" rel="noopener"> Java SDK (英語) </a> 11.0.10 以降を推奨します。
- <a href="https://tomcat.apache.org/download-90.cgi" target="_blank" rel="noopener"> Tomcat (英語) </a> 9.0.41 以降を推奨します。
- <a href="https://www.eclipse.org/downloads/packages/" target="_blank" rel="noopener"> Eclipse for Enterprise Java Developers (英語) </a> バージョン 2020-12 以降を推奨します。
- Maven リポジトリと依存関係を追加する必要があります。詳細については、[セットアップと構成](setup-configuration.html#maven-dependency)を参照してください。
 
### 手順

1. **プロジェクトを読み込みます。**
   1. Eclipse で、*File > Import > Existing Projects into Workspace* に移動します。
   2. *Select root directory* で、Reveal の SDK パスを選択し、*upmedia-backend-tomcat* プロジェクトも選択します。
   3. *Copy projects into workspace* オプションをチェックします。
   4. [Finish] をクリックします。

    プロジェクトが読み込まれ、検査する準備ができました。

2. **Tomcat でプロジェクトを実行する**
   1. upmedia-backend-tomcat プロジェクトで *Run on Server* を右クリックします。
   2. Tomcat 9 を選択し、Tomcat のインストール パスへのルート パスを設定します。
   3. デフォルト設定でプロジェクトを実行します。 
   4. http://localhost:8080/upmediabackend/reveal-api/DashboardFile/Sales にアクセスしてサーバーを確認します。その結果、Sales サンプル ダッシュボードの JSONド キュメントを取得します。

3. **React アプリケーションを実行します。**
   1. *upmedia-react* フォルダーで React アプリケーションを特定します。
   2. React アプリケーションを通常通りに実行します。

    ```bash
    npm install
    npm start
   ```
   3. http://localhost:3000 で React アプリケーションにアクセスします。

以下のコンポーネントをお試しください。
- **Filters**: 既存のダッシュボードを開き、フィルタリング エクスペリエンスをカスタマイズする方法を示します。
- **Linking**: 別のダッシュボードへのリンクを持つ既存のダッシュボードを開く方法、およびリンクを正しく構成する方法を示します。
- **CreateDashboard**: ダッシュボード エディターを開いて新しいダッシュボードをゼロから作成する方法を示します。また、新しい表示形式を作成するときにユーザーに表示されるデータ ソースのリストを設定する方法も示します。

Reveal の Web クライアント SDK の詳細については、[こちら](~/jp/developer/java-sdk/overview.md)を参照してください。

