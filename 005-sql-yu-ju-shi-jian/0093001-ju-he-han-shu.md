#### 聚合函数

为了快速得到统计数据, 经常会用到如下5个聚合函数.**(聚合函数不能在 where 中使用)**

> - count(*) 表示计算总行数, 括号中写星 与 列名, 结果是相同的.
- max(列) 表示求此列中的最大值.
- min(列) 表示求此列中的最小值
- sum(列)表示求此列的和
- avg(列), 表示求平均值



- 例1: 查询学生总数
```
select count(*) from stu;
```


- 例2: 查询女生的最大年龄
```
select max(age) from stu where sex='女';
```

- 例3: 查询1班的最小年龄
```
select min(age) from stu where class='1班'
```

- 例4: 查询北京学生年龄总和.
```
select sum(age) from stu where hometwon='北京'
```

- 例5: 查询平均年龄
```
select avg(age) from stu where hometwon='北京'
```




<br>
**说明:**
> 聚合函数也可以同时查几个值


- 示例:
```
select max(age), min(age), avg(age) from stu;
// 去别名
select max(age) as maxAge, min(age) as minAge, avg(age) as avgAge from stu;
```




