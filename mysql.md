# mysql 相关技巧


## mysql 优化空间（能减少很多空间）

```mysql

mysql -u root -p

select TABLE_SCHEMA,TABLE_NAME,INDEX_LENGTH/1024/1024 as index_M,DATA_LENGTH/1024/1024 as data_M from  TABLES   order by (INDEX_LENGTH+DATA_LENGTH) desc limit 10;  

flush logs;
reset master;
```

## 复制表结构
```mysql
drop table if exists stock_profit_D_2020;

CREATE TABLE stock_price_D_2017 LIKE stock_price_D_2021 ;
```


## 多主键
```mysql
create table indexData_D 
( 
code varchar(10),
 date date,
 name varchar(10),
   primary key (code,date) 
) 
```
