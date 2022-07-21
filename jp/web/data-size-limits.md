#Data Limits

There are size limits server-side when using Reveal Web regarding the size of files downloaded, the number of cells in a result set (after aggregation), size of pivot tables and grids (given as a number of cells).
The objective of these limits is to prevent our servers to run out of resources (memory and disk space).

Default limit Values:

-	200mb when downloading csv/json/excel
-	10 million cells
-	64 million characters (adding all the strings in all cells).

##Modifying Default Values

###Source 
[**InitializeParameterBuilder**](https://help.revealbi.io/api/java/latest/com/infragistics/reveal/engine/init/InitializeParameterBuilder.html)


| Property  |   Type| Description  |  
|---|---|---|
|  MaxDownloadSize | System.Nullable<System.Int64>  | Sets a limit on the size of a single download (e.g. a CSV file). Default us 200Mb. |
|  MaxInMemoryCells | System.Nullable<System.Int64>  | Set this property to the expected maximum size of cells to be processed from any data source (e.g. from a Sql Server table rows, from CSV rows, etc.). The engine avoids using too much disk space for its cache and this setting provides a hint for its caching management. Default is 10 million cells.  |
|  MaxStringCellSize | System.Nullable<System.Int32>  |  Sets a limit on the number of characters any string in a dataset column may have. Default is 256. |
|  MaxTotalStringsSize | System.Nullable<System.Int64>  | Set this property to the expected maximum size of pivot tables or grids, given as the total number of characters in all of its cells. The engine avoids using too much memory and this setting provides a hint for its memory management. Default is 64 million. |
