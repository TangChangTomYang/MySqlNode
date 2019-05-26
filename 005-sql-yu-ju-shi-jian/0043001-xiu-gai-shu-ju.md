#### 修改数据

|update 表名 set 列1=值1, 列2=值2... where 条件|
|-|

```
// 修改满足条件的所有的记录
update stu set name='王二麻子' where id>=5;

// 没有where 条件, 那么表示修改所有的记录
update stu set age = 28;
```


