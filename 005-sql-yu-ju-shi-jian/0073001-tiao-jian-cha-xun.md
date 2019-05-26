#### 一、条件查询介绍

使用 where 子句对表中的数据帅选, 符合条件的数据会出现在结果集中.

> where后面支持多种运算符, 进行条件的处理.
- 比较运算
- 逻辑运算
- 模糊查询
- 范围查询
- 空判断

 
<br>
语法如下: 
```
select 字段1, 字段2... from 表名 where 条件;
例如: 
select * from stu where id = 1;
```

<br>
###### 比较运算符介绍    

> 比较运算符
- 等于: =
- 大于: > 
- 大于等于: >=
- 小于: < 
- 小于等于: <=
- 不等于: != 或 <>

<br>
###### 合逻辑运算符介绍  
> 逻辑运算
- and 
- not 
- or




<br>
#### 二、简单查询示例介绍
例1: 查询机年龄小20的女生
```
select * from stu where age < 20 and sex='女';
```
例2: 查询女生或1班的学生
```
select * from stu where sex='女' or class='1班';
```
例3: 查询非天津的学生
```
select * from stu where not hometown='天津';
或
select * from stu where hometown!='天津';
```



<br>
#### 三、模糊查询,使用范围很广泛,  一般用于搜索

> 模糊查询
- like 
- % 表示任意多个任意字符
- _ 表示一个任意字符

**注意:** 
模糊查询 like 关键字必须和 % 或 _ 结合起来使用.

<br>
**示例: **
```
// 查找 '张*星' 的人
select * from stu where name like '张_星';
// 查找所有姓 张的
select * from stu where name like '张%';
```


#### 四、范围查询
范围查询,表示在一个非连续的范围内查询.

**常用的关键字:**
> - in 表示在一个非连续的范围内
- between ... and ... 表示在一个连续的范围内


<br>
** 使用in查询, 示例: **
例1: 查找家乡是北京或上海或广东的学生

```
select * from stu where hometwon in ('上海', '北京', '广东');
// 或者
select * from stu where hometwon ='上海' or hometwon ='北京' or hometwon ='广东';

```

<br>
** between ... and ... , 示例: **
例2: 查询年龄为18至20岁的学生

```
select * from stu where age between 18 and 20;
或者
select * from stu where age>=18 and age<=20;
```

**注意:** 
> between 18 and 20, 不成写成between 20 and 18, 小的在前, 大的在后



<br>

####五、空判断

**在数据库中 null 与 '' 是不同的**

> - 判断空 is null
- 判断非空 is not null

<br>
**1、判断空和非空**
例1: 查询没有填写身份证的学生
```
select * from stu where cardID is null;
```
 
例1.1 查询, 省份证号为空'' 的学生, '' 和 null 不是一回事
```
select * from stu where cardid='';
```

例2: 查询填写了身份证的学生
```
select * from stu where cardId is not null;
```



**注意:**
> 1、如果你要查询一个字段为null 的记录, 只能用具 is null 而不能用 字段名=null



<br>
**2、数据库中存入空**

    |id|name|age|height|hometown|
    |-|-|-|-|-|

- 方式1, 在插入数据时, 指定的字段什么都不写, 默认就是null
 ```
 insert into stu(name,age) values('zhangsan',19);
 这样, height honetown 就默认为null了
 ```
 
- 方式2, 在插入时,明确的指明插入的数据是null
 ```
 inert into stu(name, age, height, hometwon) values(null, null, null, null);
 ```
