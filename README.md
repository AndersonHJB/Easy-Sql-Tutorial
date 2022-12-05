# Easy-Sql-Tutorial

包含四个数据库备份文件，分别为：

## 一、`pg_test.sql` 是使用 `pg_dump` 命令导出的 postgresql 的备份文件，下载后直接使用 psql 命令还原到本地数据库即可。

步骤如下:    

### 1）创建 test 数据库：   

```mysql
CREATE DATABASE "test"
WITH
  OWNER = "postgres"
  ENCODING = 'UTF8';
```

### 2）使用以下命令还原：

```mysql
psql -U postgres -f  pg_test.sql test  
```



## 二、`mysql_test.sql `  是使用 mysqldump 命令导出的 MySQL 备份文件，下载后使用以下方式恢复到本地数据库：  

### 1）连接到数据库并创建 test 数据库，使用以下命令切换到 test 库中

```mysql
use test
```

### 2） 使用以下命令还原 : 

```mysql
source mysql_test.sql  
```



## 三、`SQLServer_test.bak` 是通过 SQLServer 客户端工具 SQL Server Management Studio 导出的备份文件。

直接使用 SQL Server Management Studio 即可恢复该备份文件。

## 四、`oracle_test.dmp` 是通过 exp 命令导出的 Oracle 备份文件，可以通过 imp 命令导入本地数据库   

例如：

```mysql
imp system/password file=c:\oracle_test.dmp ignore=y FULL=Y
```


注意：专栏中的热点数据表 Pois 由于数据量较大，导出文件超过1G，暂时无法上传到本目录，所以将包含 Pois 表的 MySQL 备份文件mysqltest.sql已上传到百度网盘中，网盘链接和提取码为：

链接：https://pan.baidu.com/s/1iBwwPfaaI1ext1qZ5B-Oxg 
提取码：qg5y 

此仓库下载即可：[https://github.com/AndersonHJB/Easy-Sql-Tutorial/releases](https://github.com/AndersonHJB/Easy-Sql-Tutorial/releases)

下载文件后，按照上文第二部分的方法恢复到数据库中，也可以进入 MySQL 的 bin 目录下执行 MySQL 命令导入：

例如：  `C:\Program Files\MariaDB 10.3\bin>mysql -uroot -proot  < C:\mysqltest.sql` 

命令中 `-uroot` 表示用户名 root 

`-proot` 表示密码为 root    

`C:\mysqltest.sql` 表示备份文件的路径

这些参数请根据自己的实际情况做修改。

