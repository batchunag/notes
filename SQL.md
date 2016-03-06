#INSERT BULK ITEMS in one row
INSERT INTO beautiful (name, age) VALUES
    ('Helen', 24),
    ('Katrina', 21),
    ('Samia', 22),
    ('Hui Ling', 25),
    ('Yumie', 29)
ON DUPLICATE KEY UPDATE
    age = VALUES(age)


#UPDATE items in bulk
You can use code above

#mysql innodb table size, memory

https://www.pythian.com/blog/difference-between-innodb_data_file_path-and-innodb_file_per_table/

Generally, use `innodb_file_per_table ` as it creates file for each table.
`innodb_data_file_path` uses one big table. 

#Directory where table is saved
/etc/my.cnf

> illegal datetime entry saved as  0000-00-00 00:00:00

> Date type and DateTime type are different

#get column names
select Column_name 
from Information_schema.columns 
where Table_name like 'table name'