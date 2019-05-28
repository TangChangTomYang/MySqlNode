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

```
//一条语句, 直接将查询的数据插入新建的表中
create table goods_brand(
    id int unsigned primary key auto_increment,
    brand_name varchar(10)
)
select distinct brand_name from goods;
```
