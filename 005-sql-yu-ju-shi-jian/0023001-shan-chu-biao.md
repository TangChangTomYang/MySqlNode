#### 删除表

```
格式1 (如果表不存在会报错)
drop table 表名
格式2
drop table if exists 表名
```

**示例:**

```
drop table if exists stu;
```

**官方创建表的方式**

```
// 这是官方的做法
drop table if exists stu;
create table stu(
    id int unsigned primary key auto_increment,
    name varchar(25),
    age int unsigned,
    height decimal(3,2)
);
```