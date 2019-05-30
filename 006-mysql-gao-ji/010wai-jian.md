#### 一、外键 foreign key

- 如果一个实体(表)的某个字段指向另一个实体(表)的主键,就称为外键(forengn key) . 被指向的实体(表),称之为主实体(主表), 也叫父实体(父表), 负责指向的实体(表),称为从实体(从表), 也叫子实体(子表)


- 对关系字段进行约束, 当为从表(字表)进行填值时, 会到关联的主表查询此值是否存在. 如果存在则填写成功, 如果不存在则填写失败并报错.


#### 二、语法

- 查看外键
```
show create table 表名;
```

- 设置外键约束<br>

- **方式1:** 
创建数据表的时候设置外键约束
    
```
create table class(
    id int unsigned  primary key auto_increment,
    name varchar(10)
);


create table stu(
    name varchar(10),
    class_id int unsigned,
    foreign key(class_id) references class(id)
);

// foreign key (自己的字段) references 主表(主表字段);
    ```

<br>
- **方式2:**
    对已经存在的数据表设置外键约束
    
```
alert table 从表 add foreign key(从表字段) references 主表名(主表字段);

alter table stu add foreign key (class_id) references class(id);
```


- 删除外键

```
-- 需要先获取外键约束名称
show create table stu;
-- 获取名称之后, 就可以根据名称来删除外键约束
alter table 表名 drop foreign key 外键名;

alter table stu drop foreign key stu_idfk1;
```

> 实际开发中
1>很少会使用外键约束, 会极大的降低更新的效率
2> 要删除的外键的名称不能乱写,  (show create table stu) 可以查看到, 创建外键时, 会自动生成一个外键名

