# Git Messages

The following is a list of Git messages and explanation of how to respond.

## End of Line Handling

The following message may be displayed when adding files to the index, prior to committing changes:

```
$ git add -A
warning: CRLF will be replaced by LF in mkdocs-project/docs/datasets/water-rights-assets/example-sql.TSTool.
The file will have its original line endings in your working directory.

```

The message is generated because the repository is using line feed (LF) for the end-of-line character but
a working file has been added that uses CRLF (for example, using a `.gitattributes` file with `* text=auto`).
The end of line in the file can be verified by using an editor to show the end of line characters.
For example `vi -b filename` will display the following (note ^M characters at end, which indicate CR):

```
ReadTableFromDataStore(DataStore="HydroBase-HBGuest",Top=10,Sql="select * from vw_cdss_netamts where wr_name like '%peoples%' and div = 3",TableID="x")^M
ReadTableFromDataStore(DataStore="HydroBase-HBGuest",Top=10,Sql="select * from vw_cdss_netamts where order_no != 0",TableID="order_no")^M
ReadTableFromDataStore(DataStore="HydroBase-HBGuest",Top=10,Sql="select count(*) from vw_cdss_netamts",TableID="count")^M
```
