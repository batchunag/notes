Basic learning of Hadoop

#Partial Delete
> Rows are deleted only partially by time column, or all together. Time must multiple of 3600

```bash
td table:partial_delete db_name table_name --from '2016-02-03 00:00:00 JST' --to '2016-02-17 00:00:00 JST' -w
```

> --time-format "%Y-%m-%d %H:%M:%S" file-аас импортлож байгаа бол гэж сонгож болох юм шиг байна.
mysql table бол datetime төрлийн column -ийг сонгож өгнө.

#Import from mysql
>Make sure you to convert column types into STRING and INT 
>
td import:auto --auto-create $db.$table --format mysql --db-url jdbc:mysql://$path --db-user $dbusername --db-password $dbpassword --time-column $time_col_name $table_name

#DateTime error (Java)
> SQL automatically sets datetime entry to 0000-00-00 00:00:00 if it is illegal datetime value. And that causes Java representation error when importing to TD.
Remove null values from sql, then import is OK.
OR set column type string to import all.

#default --time-column
--time-value epoch_time[,10]
make empty for default value(time now)

#Bulk import
https://docs.treasuredata.com/articles/bulk-import-internal

#column names
Schemas currently support column names consisting of lowercase alphabets, numbers, and "_" only.