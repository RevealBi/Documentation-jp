## Google ドライブ

Googleアカウントでログインしている場合は、Googleドライブがデータ ソースに自動的に追加されます。

![Google Drive account in your data sources list](images/google-drive-data-source-automatic.png)

Googleドライブのデータを使用するには、以下の手順に従ってください。

1.  Google Drive (またはその中のフォルダー) を選択すると、以下のログイン プロンプトが表示されます。

    ![Google Drive Login](images/google-drive-login.png)

    **ログイン情報**を入力し *[次]* を選択します。

2.  **For first-time users only**, you will see an *Authorize* dialog, prompting you to give Reveal **appropriate permissions** so that it can use your Google Drive data.

    ![Reveal notification for giving permissions to the app](images/notification-limited-permissions.png)

    *[続行]*をクリックすると、**承認プロンプト**にリダイレクトされます。

    ![Limited permissions request google dialog](images/limited-permissions-google-drive.png)

3.  *[許可]*を選択して、Reveal が Google ドライブ ファイルを使用 (表示およびダウンロード) することを承認します。

これで、Googleドライブのデータを使用して表示形式を構築できるようになり、これらの権限を再度求められることはありません。

### サポートされるファイル

Reveal では、広範な種類のファイルを使用できます。

  - **スプレッドシート**: Excel (.xlsls, .xlsx) または CSV (Reveal 内で動的に使用できます)。

  - **その他のファイル**: プレビューモードのみで表示されます (画像および PDF やテキストなどのドキュメント ファイルを含む)。