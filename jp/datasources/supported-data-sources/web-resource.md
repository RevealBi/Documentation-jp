---
title: How to use Web Resource as a data source in Slingshot 
_description: Learn how to use any virtual file in the web as a data source in Slingshot to advance your work.
_language: ja
---

# ウェブ リソース

ウェブ リソースは、ウェブの任意の仮想ファイルで一意の URL アドレスを使用して取得できます。たとえば、Excel スプレッドシート ([サンプル](https://download.infragistics.com/reveal/help/samples/Reveal_Dashboard_Tutorials.xlsx)など) または画像 ([サンプル](http://www.infragistics.com/media/442175/home-header-shots.png)など) です。

ウェブ リソース データ ソースを構成するには、以下の情報が必要です。

<img src="images/web-resource.png" alt="Configure Web resource connection" class="responsive-img"/>

1.  **[URL]**: サービスの URL (ダッシュボード チュートリアルの場合は <https://download.infragistics.com/reveal/help/samples/Reveal_Dashboard_Tutorials.xlsx> など)。

3. **[結果タイプ]**:  サービスから取得する予定のファイル タイプを指定できます。たとえば、*.csv* を選択し、サービス が *json* で応答した場合、Reveal はファイルを *.csv* として解析しようとします。

    [自動検出] を選択した場合、Reveal は サービス からのファイル (コンテンツ) タイプに関する情報を使用してファイルを解析します。

4.  **Credentials**: You can click on the drop-down menu and select **+Credential**. After that you can enter the following:

      - **Credential Type**: two options - **Generic Credentials** or **OAuth 2 / OIDC**.

      - **Username or domain**: the user account for the Web Resource or the name of the domain.

      - **Password**: the password to access the Web Resource.

  If you want to make some changes to your credentials, you can select **Manage Credentials** from the drop-down menu.

Once ready, select **Load and Continue**.

保護されたウェブ リソースの **OAuth 2 / OIDC アカウント**を設定するには、[このトピック](~/jp/datasources/oauth-2-oidc-user-authentication.html)をお読みください。
