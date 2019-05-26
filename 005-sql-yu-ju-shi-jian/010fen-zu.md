#### 分组
- 按照字段分组, 表示此字段相同的数据会被放到一个组中.
- 分组后, 分组的依据列会显示在结果集中, 其它列不会显示在结果集中
- 可以对分组后的数据进行统计, 做聚合运算



<br>
分组的使用场景: 
- 分组的使用场景一般是用来对元数据进行分类统计, 并显示统计后的数据.
- 分组一般都会和我们的聚合函数一起配合使用, 统计某个字段值的信息

<br>
其实分组,也可以用于去重, 和我们之前讲的 distinct 一样

#### 一、 语法

```
select 列1, 列2, 聚合... from 表名 group by 列1, 列2...
```

例1: 查询各种性别的人数

```
select sex , count(*) from stu group by sex;
// 区别名
select sex , count (*) as 人数 from stu group by sex;
```


例2: 查询各种年龄的人数
```
select age, count(*) from stu group by age;
```

例3: 查询各个班的平均年龄、最大年龄、最小年龄、人员总数
```
select class, avy(age), min(age), max(age), count(age) from stu group by class;

// 别名
select class as 班级名称, avy(age) as 平均年龄, min(age) as 最小年龄, max(age) as 最大年龄, count(age) as 总人数 * from stu group by class;
``` 


例4: 查询各班级, 男生、女生的人数(即先按班级分组, 再按性别分组)
```
// 多个分组之间使用逗号隔开
select class , sex , count(*) from stu group by class,sex;

```







<br>

#### 二、分组后的数据筛选


语法:

```
select 列1, 列2, 聚合... from 表名
group by 列1, 列2, 列3...
having 列1,... 聚合 ...
```
> having 后面的条件运算符与where 相同


<br>
例1: 查询男生总人数
```
方案1:
select sex count(*) from stu where sex='男';

方案2: 
select sex count(*) from stu group by sex having sex='男';

// having sex='男' 表示的就是在分组后再过滤, 相当于 where sex='男', 当是在 分组后面只能使用 having 列=value 不能使用where 
```


例2: 查询1班外其他班级的平均年龄, 最大年龄, 最小年龄

```
// 先条件过滤, 在分组
select class, avg(age), max(age), min(age) from stu where class1='1班' group by class;

// 先分组, 再过滤
select class, avg(age), max(age), min(age) from stu group by class having class!='1班';
```




<br>
#### 三、对比 where 与 having

- where 是对 from 后面指定的表进行数据筛选, 属于对原始数据的筛选
- having 是对group by 的结果进行筛选
