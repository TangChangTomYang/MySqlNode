


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

10、查询学生'张三'的基本信息
```
select * from stu where name='张三';
```

11、查询学生'张三' 或 '李四' 的基本信息
```
select * from student where name='张三' or name='李四';
```

12、 查询姓 '张' 学生的姓名, 年龄, 班级
```
select name, age, class from student where name like '张%';
```

13、查询姓名中包含有 '约' 的学生
```
select * from student where name like '%约%`;
```

14、查询姓名长度为3个字, 姓'孙' 的学生的学号, 姓名, 年龄, 班级, 身份证号
```
select studentNo as 学号, name as 姓名, age as 年龄, class as 班级, card as 身份证号 from student where name like '孙__';
```

15、 查询姓 '孙' 或者 姓 '百' 的学生基本信息
```
select * from student where name like '孙%' or name like '百%';
```

16、查询姓 '百' 且 家乡是 '山西' 的学生基本信息
```
select * from student where name like '百%' and hometown='山西';
```

17、查询家乡是 '北京' '新疆' '山东' 或者 '上海' 的学生信息
```
select * from student where hometown in ('北京','新疆','山东', '上海');
```

18、查询姓 '孙' , 但是家乡不是 '河北' 的学生信息
```
select * from student where name like '孙%' and hometown!='河北'
```

19、查询家乡不在 '北京' '上海' '成都' 的学生信息
```
select * from student where hometown not in ('北京','上海','成都');
```

20、查询学生信息, 并以性别排序
```
select * from student order by sex;
```