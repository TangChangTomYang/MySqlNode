#### 查询数据

#### 一、简单的查询记录

```
select 字段名1, 字段名2 ... from 表名 where 条件;
select * from 表名 where 条件; // * 表示的是字段的通配符
```

<br>
#### 二、 给查询的字段取别名(2种方式)

方式1:(推荐写法)

```
select name as 姓名, age as 年龄, height as 身高 from stu where age < 18;
```

方式2: 省略as 效果一样
```
select name 姓名, age 年龄, height 身高 from stu where age < 18;
```


<br>
#### 三、给查询的表取别名(一般用于多表查询)

```
select name, age from stu as s; // 给表取别名, 一般在多张表一起查询时取别名好记

// 表示查询别名为s这张表里面的name 和 age
select s.name , s.age from stu as s;
```

<br>
#### 四、查询记录,并对查询到的结果去重
```
// 表示查询小于18 的学生有几个性别
select distinct sex from stu where age < 18; // 单个字段取重

// 多个字段去重
select distinct sex,class from stu where age < 20;
如: 没去重前的数据为
性别  班级
女    1班
男    1班
女    2班
男    2班
女    1班
男    1班
女    2班
男    2班

去重后: (表示的是去除相同的记录)
女    1班
男    1班
女    2班
男    2班 

select distinct * from stu where age < 20;
// distinct 表示的是去除,重复的记录
```



<br>
