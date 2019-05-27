#### 子查询

- 在一个select 语句中, 嵌入了另一个 select语句, 那么被嵌的select语句被称之为子查询语句.

#### 主查询
- 主查询的对象, 第一条select语句

#### 主查询和子查询的关系
- 子查询是嵌入到主查询中
- 子查询是辅助主查询的, 要么充当条件, 要么充当数据源
- 子查询是可以独立存在的语句, 是一条完整的select语句

#### 子查询分类
- 标量子查询: 子查询返回的结果是一个数据(一行一列)
- 列子查询: 返回的结果是一列(一列多行)
- 行子查询: 返回的结果是一行(一行多列)
- 表级子查询: 返回的结果是多行多列


<br>
#### 一、标量子查询

例1: 查询班级学生的平均年龄
```
// 查询班级学生的平均年龄
select avg(age) from stu;

// 查询大于平均年龄的学生
select * from stu where age > 20;


// 标量子查询
select * from stu where age > (select avg(age) from stu);
```

例2: 查询王昭君的成绩, 要求显示成绩
```
//学生表中查询王昭君的学号
select stuNo from stu where name = '王昭君';

// 成绩表中根据学号查询成绩
select score from scores where stuNo = 20;

select score from scores where stuNo = (select stuNo from stu where name = '王昭君');
```

**特点:**
> 子查询的结果是一行一列

<br>
**注意:**
> 
(1)虽然我们使用普通的多条查询语句, 可以实现标量子查询语句 (嵌套查询)的功能, 当是我们不推荐. 因为多条语句在执行时, 有可能语句与语句之间有其它的变化, 数据有风险. 
(2)  但是我们如果使用的是, 嵌套查询就不会有这样的数据安全风险了.




<br>
#### 二、列量子查询

例1: 查询18岁的学生的成绩, 要求显示成绩
```
select * from scores where scores.stuNo in (select  stuNo from stu where age = 18);
```
**特点:**
> 子查询返回的结果是1列多行




<br>
#### 三、行子查询

例1: 查询男生中年龄最大的学生信息
```
select * from stu where sex='男' and age = 26;

// 也可以这样写
select * from stu where (sex,age) = ('男',26);

// 也可以这样写(行子查询)
select * from stu where (sex,age) = (select sex, age from stu order by age desc limit 1);
``` 


**特点:**
> 子查询返回的结果是一行多列







<br>
#### 四、表级子查询

前面讲的 标量子查询/ 列子查询/ 行子查询, 其查询结构都是作为 where 的条件的.



例:查询数据库和系统测试的课程成绩
```
方式1: 
select * from scorse
inner join courses on scores.courseNo=courses.courseNo
where courses.name in ('数据库' , '系统测试');

// 方式1的缺点是, 先查询生成一个大的表, 在将表数据过滤
// 相当于在一大堆数据中在去过滤

select
    * 
from
    scores as sc
inner join (select * from courses where name in ('数据库', '系统测试')) as cs on sc.courseNo = cs.courseNo;

// 方式2的有点, 数据量小, 效率高些
```



**注意: **
> 
(1) select * from 表名, 这个表名代表的是一个数据源.
(2) select * from 表名1 inner join 表名2 on where xxx,  表名1 和 表名2 都是代表的是数据源
(3) 在sql 语句中除了表名可以代表数据源, 查询到的记录也可以作为数据源.



