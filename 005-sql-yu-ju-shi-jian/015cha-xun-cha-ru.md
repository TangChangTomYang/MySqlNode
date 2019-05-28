#### 查询插入

将一个sql 语句查询到的结果可以直接插入另一个表中


**insert into 表1(列1, 列2...) select 列a, 列b from 表2 where 条件 **
```
// 将select distinct cate from goods 语句查询的的列数据直接插入一个表中
insert into goodsCate(cate_name) select distinct cate from goods
```