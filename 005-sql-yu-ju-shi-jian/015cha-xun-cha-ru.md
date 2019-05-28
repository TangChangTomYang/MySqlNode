#### 查询插入

**1、直接将sql 语句查询到的结果直接插入另一个表中**

**语法:** 
> insert into ... select...


```
// 将select distinct cate from goods 语句查询的的列数据直接插入一个表中
insert into goodsCate(cate_name) select distinct cate from goods
```

<br>
**2、创建表, 并将插入的数据插入到创建的表中**


**语法:**
> create table ... select ...
特点: 如果查询出来的数据字段, 在新建的表中有,就直接插入
如果查出来的数据字段,在新建的表中没有, 就会新建一个字段并且插入
即: 具体插入那一列, 就看 名字是否一样, 不一样就新建字段

```
//一条语句, 直接将查询的数据插入新建的表中
create table goods_brand(
    id int unsigned primary key auto_increment,
    brand_name varchar(10)
)
select distinct brand_name from goods;
```



<br>
**3、 直接使用 sql 语句备份一张表**

**语法:**
> create table ... select ...


```
// 查询到的什么字段就创建字段, 一模一样
create table goods_bak select * from goods;
```




<br>
**4、 使用一个表的字段更新另一个标的字段**


```
// 这个是一般的查询
select 
    * 
from 
    table goods
inner join goods_cate on goods.cate=goods_cate.cate_name


// 稍作调整就可以更新了

1>把前面的select * from  改为 update
2> 在后天添加要更新的字段


update goods
inner join goods_cate on goods.cate=goods_cate.cate_name
set goods.cate=goods_cate.id; // 搞定
```