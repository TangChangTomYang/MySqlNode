#### MySql 命令行客户端

**1、命令终端连接Mysql**

```
mysql -uroot -p12345  //回车
或者 (推荐)
mysql -uroot -p // 回车
password:       // 出入密码

```

<br>
**2、查看当前mysql 下所有的数据库(仓库)**
```
show databases;  // 注意, 在终端中, 输入分号 表示执行sql 语句
```

<br>
**3、使用某个仓库(重要)**

```
use 仓库名;
```

<br>
**4、查看所有的表**
```
show tables;
```

<br>
**5、查看表结构**
```
desc 表名;
或则
show create table 表名;
```


