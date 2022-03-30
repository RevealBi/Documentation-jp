# 既知の問題

**1** - package.config を使用してプロジェクトの Reveal SDK をより新しいバージョンに更新後、古い NuGet バージョンのアンインストールや新しいバージョンへの更新ができません。

回避策: Reveal SDK を更新する前に、プロジェクトから NuGet パッケージをアンインストールします。次に、インストーラーを使用して Reveal SDK を更新します。最後に、更新された NuGet パッケージを再インストールできます。

回避策 2: Reveal SDK を更新する前に、既存の NuGet パッケージをバックアップします。これには、"%public%\Documents\Infragistics\Nuget" (インストーラーによって作成されたローカル NuGet パッケージストアの場所) に移動します。既存のパッケージを他のフォルダーにバックアップし、更新されたインストーラーを実行してから、バックアップしたパッケージを同じ場所にコピーします。最後に、プロジェクトで使用されている NuGetバージョン をアップグレードできます。