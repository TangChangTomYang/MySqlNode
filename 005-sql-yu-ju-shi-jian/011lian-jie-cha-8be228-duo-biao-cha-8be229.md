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




<br>
#### 二、等值连接

**1、方式1:**
```
select * from 表1, 表2 where 表1.列=表2.列
```

**2、方式2:** (又称为内连接) **(推荐使用)**
```
select * from 表1
inner join 表2 on 表1.列=表2.列;
```

例1: 查询学生表信息及学生的成绩
```
select 
    * 
from
    Student as stu,
    Scores as sc
where 
    stu.studentNo = sc.studentNo;
-----------------------------------
select 
    * 
from 
    student as stu
inner join scores as sc on stu.studentNo=sc.studentNo;

```


例2: 查询课程信息及课程成绩
```
select 
    * 
from
    courses as cs,
    scores as sc
where 
    cs.courseNo=sc.courseNo;

-------------------------------------
select 
    *
from
    courses as cs
inner join scores as cs on cs.courseNo=cs.courseNo;
```


例3: 查询学生信息及学生的课程对应的成绩
```
select 
    *
from student, courses, scores
where
student.studentNo=courses.studentNo and courses.courseNo=scores.courseNo;

// 显示指定字段
select student.name, courses.name, courses.score
where
student.studentNo=courses.studentNo and courses.courseNo=scores.courseNo;

------------------------------------------
// 使用内连接来写,就必须要注意表之间的连接顺序
select 
    * 
from student
inner join courses on student.studentNo=courses.studentNo
inner join scores on courses.courseNo=scores.courseNo;

```



**等值连接的2种方式,是有差异的**
> 
"select * from 表1, 表2 where 表1.列=表2.列" 方式会产生笛卡尔积, 然后在过滤, 内存开销要大些
"select * from 表1 inner join 表2 on 表1.列=表2.列;" 会判断是否满足条件在链接,内存开销要小些.

<br>
> 内连接相较于where 查询, inner join 是由顺讯关系的



<br>
#### 三、连接查询 后过滤



