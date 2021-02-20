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
create table stockData_D 
( 
code varchar(10),
 date date,
 open float,
 high float,
 low float,
 close float,
 preclose float,
 volume float,
 amount float,
 turn float,
peTTM float,
psTTM float,
pcfNcfTTM float,
pbMRQ float,
isST int(2),
tradestatus int(2),
 openpct2 float,
 openpctmean2 float,
 openpctmax2 float,
 openpctmin2 float,
 openpctpre2 float,
 openpctstd2 float,
 closepct2 float,
 closepctmean2 float,
 closepctmax2 float,
 closepctmin2 float,
 closepctpre2 float,
 closepctstd2 float,
 openpct5 float,
 openpctmean5 float,
 openpctmax5 float,
 openpctmin5 float,
 openpctpre5 float,
 openpctstd5 float,
 closepct5 float,
 closepctmean5 float,
 closepctmax5 float,
 closepctmin5 float,
 closepctpre5 float,
 closepctstd5 float,
 openpct10 float,
 openpctmean10 float,
 openpctmax10 float,
 openpctmin10 float,
 openpctpre10 float,
 openpctstd10 float,
 closepct10 float,
 closepctmean10 float,
 closepctmax10 float,
 closepctmin10 float,
 closepctpre10 float,
 closepctstd10 float,
 openpct20 float,
 openpctmean20 float,
 openpctmax20 float,
 openpctmin20 float,
 openpctpre20 float,
 openpctstd20 float,
 closepct20 float,
 closepctmean20 float,
 closepctmax20 float,
 closepctmin20 float,
 closepctpre20 float,
 closepctstd20 float,
 openpct40 float,
 openpctmean40 float,
 openpctmax40 float,
 openpctmin40 float,
 openpctpre40 float,
 openpctstd40 float,
 closepct40 float,
 closepctmean40 float,
 closepctmax40 float,
 closepctmin40 float,
 closepctpre40 float,
 closepctstd40 float,
 upfirst2 int(2),
 upfirst5 int(2),
 upfirst10 int(2),
 upfirst20 int(2),
 upfirst40 int(2),
   primary key (code,date) 
) 


create table indexData_D 
( 
code varchar(10),
 date date,
 name varchar(10),
   primary key (code,date) 
) 
