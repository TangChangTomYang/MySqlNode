#### 视图

- 对于复杂的查询, 在多个地方被使用, 如果需求发生了变化, 需要修改sql 语句, 则需要在多个地方进行修改,维护起来非常的麻烦.
- 解决方案: 定义视图

什么是视图? 
视图的本质就是对查询的封装

- 定义视图: 建议以 v_开头

```
create view  视图名称 as select 语句;
```
<br>
例如:

```
create view v_stu_score_course as
select 
    stu.*, cs.courseNo, cs.name courseName, sc.score
from students as stu 
inner join scores as sc on stu.studentNo = sc.studentNo
inner join course as cs on cs.courseNo = sc.courseNo
```


- 查看视图: 
查看表时, 会将所有的视图也列出来(对外就像表一样)
```
show tables;
```