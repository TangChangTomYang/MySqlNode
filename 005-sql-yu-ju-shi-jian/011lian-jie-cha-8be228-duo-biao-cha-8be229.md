####  连接查询(多表查询)

**当查询结果的列来源于多张表时, 需要将多张表连接成宇哥大的数据集, 再选择合适的列返回.**



#### 连接查询介绍

**1、等值连接查询:** 
查询的结果为2个表匹配到的数据.
![](/assets/Snip20190526_3.png)

<br>
**2、左连接查询:** 
查询到的结果为两个表匹配到的数据加左边表特有的数据, 对于右边表中不存在的数据使用 null填充
![](/assets/Snip20190526_4.png)


<br>
**3、右链接查询:**
查询的结果为2个表匹配到的数据加上右边表特有的数据, 对于左边表中不存在的数据使用null 值填充
![](/assets/Snip20190526_5.png)



准备数据
```
drop table if exists courses;
create table course (
    courseNo int(10) unsigned primary key auto_increment,
    name varchar(10)
);

insert into courses values
('1', '数据库'),
('2', 'qtp'),
('3', 'Linux'),
('4', '系统测试'),
('5', '单元测试'),
('6', '测试过程');

drop table if exists scores;
create table scores(
    id int(10) unsigned primary key auto_increment,
    courseNo int(0),
    stuNo varchar(10),
    score tinyint(4)
);
