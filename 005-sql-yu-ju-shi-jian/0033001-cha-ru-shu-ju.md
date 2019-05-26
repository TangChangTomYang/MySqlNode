#### 插入数据

|id (int 主键 自增长)|name (varchar)|age (int)|height (decimal)|
|-|-|-|-|



格式1:

```
insert into 表名 values(value1,value2, value3, value4) ;
```

**示例:**
```
value的顺序和个数不能乱, 如过时varchar类型需要 使用单引号包裹
// 因为id 是自增长的, 因此我们在插入时, 使用默认值占位即可, 系统会自动替换为正确的值. (常用占位值: 0/ default/ null)
insert into stu values(0, 'zhangsan', 18, 1.2);
insert into stu values(default, 'lisi', 29,1.9);
insert into stu values (null, 'zhaoliu', 29,2.9);
```

<br>
方式2:
```
// 插入那些字段, 字段对应的值是什么, 这种方式比较灵活
insert into stu(name, age, height) values('zhangsan', 18, 1.89);
```

<br>
方式3: 一次插入多条语句
```
insert into stu(name, age) values('lisi1', 18);
insert into stu(name, age) values('lisi2', 18);
insert into stu(name, age) values('lisi3', 18);

// 等价于
insert into stu(name, age) values('lisi1', 18),('lisi2', 18),('lisi3', 18); // 这种效率高些
```




