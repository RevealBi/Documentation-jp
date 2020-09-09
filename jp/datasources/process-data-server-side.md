## サーバーでデータを処理

基本的に、データソースに接続すると、サーバー上のすべてのデータがローカルに読み込まれ、ダウンロードされます。  このようにして、データセットをソート、フィルタリング、集計、および表示形式に使用することなど、Reveal 内で直接処理できます。 

数百万のレコードが含まれるような非常に大きなデータセットを持つデータソースの場合、ローカルで使用するためにデータをダウンロードすることは得策ではありません。その理由で、Reveal では代替アプローチとしてサーバー上で直接データを処理する機能が提供されています。 

### サポートされるデータ ソース

Reveal で利用可能なデータソースの一部では、サーバー上で直接データを処理するアプローチ**のみ**が使用可能です。以下があります: 

* Amazon Redshift
* Google BigQuery
* Microsoft Azure Synapse Analytics  

サーバーでのデータ処理は、次のデータソースに対して**有効**にできるオプションです。 

* [MS SQL Server](microsoft-sql-server.md)
* [MySQL](mysql.md)
* [PostgreSQL](postgresql.md)

### サーバー上でデータを処理を有効にする方法は?

_Process Data on Server_ 関数を有効にして、それをサポートするデータソース (上記を参照) のいずれかに接続できます。 

データソースの初期構成を行う方法の詳細については、上記の箇条書きリストで 3 つのデータソースのいずれかを選択し、設定方法に関する記事をご覧ください。

After configuring the connection, you will you will have the _Set Up the Database_ screen opened:

<img src="images/process-data-server-checkbox.png" alt="New Process data on server checkbox added in the Set Up the Database dialog in PostgreSQL" width="800"/>

Notice that the _Process Data on Server_ is enabled by default. Consider unchecking the box next to this feature in case you need to use any of the capabilities that are limited (see in _Limitations_ below), when your data is processed on the server.

### Limitations

The _Process Data on Server_ feature helps you build visualizations over very large datasets, where it would otherwise be unfeasible to download all the data locally. However, this feature introduces some limitations to the use of the data source it's enabled for.  

The following capabilities are **not supported** in the Visualization editor when _Process Data on Server_ is enabled:

* [Data Blending](data-blending.md)
* [Azure ML models integration](ml-integration/azure-machine-learning-models.md)

Restrictions are placed on the [Pre-Calculated](~/jp/data-visualizations/fields/calculated-fields/overview.html#precalculated-fields) fields feature in the Visualization editor. Unavailable functions are greyed out in the _New Calculated Field_ dialog.
In this dialog, you can click on the link to disable the _Process Data on Server_ feature.

<img src="images/pre-calculated-fields-unavailable-process-data-server.png" alt="Disable Process Data on Server prompt in the Calculated Fields dialog" width="800"/>
