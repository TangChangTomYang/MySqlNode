#### 分页

#### 一、获取部分分行


**当数据量过大时, 在一页中查看数据是一件非常麻烦的事情.**

**语法:**
```
select * from 表名 limit start, count;

// 从start开始, 获取count条数据
// start 索引从 0 开始
```


例1: 查询前3条学生信息
```
select * from stu limit 0,3;
```

例2: 查询第4到第6条学生信息
```
select * from stu start 3 , 3;
```
例3: 先排序,在显示部分和直接显示部分是不一样的
```
select * from stu group by sex limit 0,3;
```


> 如果分页, 从第0条开始获取, start 参数也可以省略
```
// 表示的是查询最前面5条数据
select * from stu limit 5;
```

<br>
#### 二、分页

- 已知: 每页显示m条数据, 求显示第n页的数据
```
pageCount = 10;
page = 1;
select * from stu limit pageCount*page, pageCount;
```
