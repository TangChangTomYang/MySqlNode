#### 索引 (有点类似树状结构)

- 思考: 在图书馆中是如何找到一本书?

- 一般的应用系统对比数据库的读写比例在10:1左右, 而且插入操作和更新操作很少出现性能问题, 遇到最多的, 也是最容易出问题的, 还是一些复杂的查询操作, 所以查询语句的优化显然是重中之重.
- 当数据库中数据量很大, 查询数据会变得很慢
- 优化方案: 索引 (相当于是数的目录)



    
    
- 实例: 导入测试表 test_index
```
右键点击某个数据库 -> 运行sql文件-> 选择test_index.sql -> 点击开始
```

- 查询: 
```
// 开始运行时间监测:
set profiling=1;

// 查找第10000条数据
select * from test_index where title='test10000';

// 查看执行时间
show profiles;

// 为表title_index 的title列创建索引
create index title_index on test_index(title(10));


// 执行查询语句
```





#### 一 语法: 

- 查看索引
```
show index from 表名;
```

- 创建索引 (只要数 primary key的字段和unique 字段默认会创建索引)
    - 方式一:
    ```
    create table create_index(
        id int primary key,
        name varchar(10) unique,
        age int,
        key (age)  // 给age字段创建一个索引
    );
    ```

    - 方式2:
    ```
    如果指定字段是字符串, 需要指定长度, 建议长度与定义字段长度一致
    字段类型如果不是字符串, 可以不填写长度部分
    
    create index 索引名称 on 表名 (字段名(长度))
    例如: 
    create index age_index on  create_index(age);
    create index name_index on create_index(name(10));
    ```


- 删除索引
```
drop index 索引名称 on 表名
```



#### 索引的缺点
虽然索引能大大的提高查询的速度, 同时会降低更新表的速度, 如: 对表进行 insert update 和 delete, 因为更新表时, mysql 不仅要保存数据, 还要保存索引文件

但是在互联网中, 查询的语句远远大于增删改的语句, 甚至可以占到80%~90%, 所以不要太在意, 只是在大数据导入时, 可以先删除索引, 在批量插入数据, 最后添加索引
