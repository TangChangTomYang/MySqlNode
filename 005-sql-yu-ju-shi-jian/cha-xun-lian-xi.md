


1、统计2班男女各有多少人?
```
select sex, count(*) from stu where class='2班' group by sex;
```


2、查询先有学生都来自于那些不同的省份
```
select hometown from stu group by hometown;
```

3、查询所有的男生, 并按年龄升序排序

```
select * from stu order by age where sex='男';
```

4、统计共有多少学生
```
select count(*) from stu;
```

5、统计年龄大于20岁的学生有多少个
```
select count(*) from stu where age>20;
```

6、统计男生的平均你年龄
```
select avg(age) from stu where sex='男';
```

7、查1班中, 最大的年龄是多少
```
select max(age) from stu where class='1班';
```
8、统计每个班级中每种性别的学生人数, 并按班级升序排序
```
select class, sex, count(*) from stu  group by class, sex order by class;
```
9、查询年龄最小的学生的全部信息
```
select * from stu order by age limit 1;
```


