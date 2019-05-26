#### 分组
- 按照字段分组, 表示此字段相同的数据会被放到一个组中.
- 分组后, 分组的依据列会显示在结果集中, 其它列不会显示在结果集中
- 可以对分组后的数据进行统计, 做聚合运算


分组的使用场景: 分组的使用场景一般是用来对元数据进行分类统计, 并显示统计后的数据

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

#### 二、分组后的数据筛选

