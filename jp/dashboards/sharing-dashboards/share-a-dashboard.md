# ダッシュボードの共有

共有ダッシュボードは、チーム間のコラボレーションに最適です。Reveal での共有に関しては、非常に多くの利用シナリオが考えられます。

Here you will find more information about the permission roles and the available sharing scenarios:

  - [独自のダッシュボードを他のユーザーと共有する](#sharing-dashboards-users)

  - [ワークスペースのダッシュボードを他のユーザーと共有する](#sharing-workspace-dashboard)

  - [ワークスペース全体とダッシュボードを共有する](#sharing-dashboard-with-workspace)

> [!NOTE]
> **フォルダーを共有**。この記事のダッシュボード共有のルールは、共有フォルダーにも適用されます。

<a name='sharing-dashboards-users'></a>
## 独自のダッシュボードを他のユーザーと共有する

作成したダッシュボードを個人ユーザーと共有するには、次のことを行う必要があります。

1.  **[共有] ダイアログ**にアクセスする - オーバーフロー メニューを開き、**[共有ユーザー]** を選択します。


  <img src="images/shared-with-button.png" alt="Accessing the sharing dialog of a dashboard" class="responsive-img"/>

  Once you share a folder with other people, the files will appear under the **Shared with Me** section in the left panel. Alternatively they can find the files when they open **My Analytics** and click/tap on **Shared with Me** that is under **Filters**.

  <img src="images/shared-with-me-section.png" alt="Finding the Shared with Me option in different sections" class="responsive-img"/>

<a name='access-permissions'></a>

2.  **Choose the users** you want to share the dashboard with - Enter the e-mail addresses or the names of the people you want to invite and click/tap on **Done**.

3.  After selecting the users, click/tap **Update**. The dashboard will be shared automatically with the selected users if they are part of your [Organization](~/jp/workspaces/overview.html#organization-workspace). Other users will have the dashboard shared with them only after they accept the invitation.

  <img src="images/add-users-sharing-dashboards.png" alt="Choosing with whom to share a dashboard" class="responsive-img"/>

**You can change the access level for users at any time when you are the owner of the dashboard** by accessing
the Share menu.ダッシュボードを共有したすべてのユーザーとそのアクセス レベルのリストが表示されます。名前の横にあるドロップダウン メニューから新しいアクセス レベルを選択して、アクセス レベルを変更できます。

**When you are the owner of the dashboard, you can also unshare it at any time** by accessing the Share dialog and selecting *Remove* from the dropdown menu next to any member's name.

<img src="images/shared-with-remove-option.png" alt="Remove sharing button" class="responsive-img"/>

In general, a user can have one of the following permissions:

  - **Owner** permissions - the user can create, edit, share and delete.

  - **Contributor** permissions - the user can create, edit, share, and delete. Keep in mind that the user cannot delete the item that was shared with them (Dashboard/Dashboard List).

   <img src="images/request-to-share-button.png" alt="Sending a request to the owner in order to share a dashboard" width="50%" class="responsive-img"/>

  - **Viewer** permissions - the user can view a dashboard. They can also share it with another user after the approval of the owner.

<a name='sharing-workspace-dashboard'></a>
## Sharing a Workspace's Dashboard with Other Users

Any member of a workspace can share the workspace's dashboards with other users. To do this, go to the *Workspaces* tab and choose a dashboard from the *Dashboards* section. Then, follow the steps in [Sharing your Own Dashboard with Other Users](#sharing-dashboards-users). Keep in mind that the owner of the workspace needs to approve the request first in order for a member to share a dashboard with another member.

<a name='sharing-dashboard-with-workspace'></a>
## ワークスペース全体とダッシュボードを共有する

You can share a dashboard you have access to with a workspace instead of individually with every workspace member.

To do this, choose a dashboard from the *Dashboards* section in *My Analytics* or *Workspaces* tab.

>[!NOTE]
>ダッシュボードは、メンバーであるかどうかに関係なく、[メイン組織に属する](~/jp/workspaces/overview.html#organization-workspace)任意の公開ワークスペースと共有できます。自分がメンバーになっている非公開のワークスペースと共有することもできます。

## 関連項目

クラウド サービスにあるデータ ソース ファイルを使用してダッシュボードを作成した場合、ダッシュボードを共有するには、このファイルへのアクセスを許可する必要があります。詳細については、[クラウド ファイルをデータ ソースとするダッシュボードを共有する](sharing-dashboards-datasource-files-cloud-provider.html)トピックをご覧ください。
