#INSERT BULK ITEMS in one row
INSERT INTO beautiful (name, age) 
VALUES  
    ('Helen', 24),  
    ('Katrina', 21),  
    ('Samia', 22),  
    ('Hui Ling', 25),  
    ('Yumie', 29)  
ON DUPLICATE KEY UPDATE  
    age = VALUES(age)  


#UPDATE items in bulk
You can use code above

#INSERT BULK data from file

$sql = "LOAD DATA LOCAL INFILE 'file.csv' INTO TABLE table FIELDS TERMINATED BY ',' ENCLOSED BY '\"'";

#mysql innodb table size, memory

https://www.pythian.com/blog/difference-between-innodb_data_file_path-and-innodb_file_per_table/

Generally, use `innodb_file_per_table ` as it creates file for each table.
`innodb_data_file_path` uses one big table. 

#Directory where table is saved
/etc/my.cnf

> illegal datetime entry saved as  0000-00-00 00:00:00

> Date type and DateTime type are different

#get column names, types
select Column_name, Column_type 
from Information_schema.columns 
where Table_name like 'table name'
 and TABLE_SCHEMA like "db name"

#COPY table in same server
INSERT INTO db1.table1 
SELECT * FROM db2.table2
