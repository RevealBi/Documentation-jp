# 既知の問題

- Scatter Map / Choropleth visualizations do not show up in programmatically exported dashboards.

- NuGet パッケージを使用する際に、Reveal SDK のライセンス (SDK インストーラーに有効なキーを入力) 後もウォーターマークが表示されてしまうます。 

**回避策**: プロジェクトから NuGet パッケージをアンインストールし、NuGet のキャッシュをクリアして、パッケージを再度インストールしてください。NuGet のすべてのキャッシュをクリアしたくない場合、キャッシュした場所を検索し、Infragistics Reveal 項目のみをクリアできます。場所は NuGet のバージョンと、*packages.config* または *PackageReferece* のどちらが使用されているかによって異なります。