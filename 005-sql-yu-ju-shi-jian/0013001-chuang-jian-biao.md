#### 创建表

**格式: **
```
create table 表名 (
    字段名 类型 约束,
    字段名 类型 约束
);
```

**示例:**
```

比如: 
// id 无符号 主键 自动增长
// name 字符串 最长25个字符
// age 无符号
// height 小数,最多3位整数, 2位小数
create table stu (
    id int unsigned primary key auto_increment,
    name varchar(25),    
    age int unsigned ,
    height decimal(5,2)
)
```

