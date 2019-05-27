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
#### 标量子查询

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


**注意:**
> 
(1)虽然我们使用普通的多条查询语句, 可以实现标量子查询语句 (嵌套查询)的功能, 当是我们不推荐. 因为多条语句在执行时, 有可能语句与语句之间有其它的变化, 数据有风险. 
(2)  但是我们如果使用的是, 嵌套查询就不会有这样的数据安全风险了.




<br>
#### 列量子查询

例1: 查询18岁的学生的成绩, 要求显示成绩
```
select * from scores where scores.stuNo in (select  stuNo from stu where age = 18);
```