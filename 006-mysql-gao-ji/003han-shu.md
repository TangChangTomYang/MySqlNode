#### 函数


#### 内置函数


#### 字符串函数

**1、拼接字符串 concat(str1, str2 ...)**

**格式: **

> select concat(12,34,'ab');

例1: 将查询的姓名和年龄拼接
```
// 这样, 就可以直接返回查询后拼接的数据了
select name,age, concat(name ,'的年龄是: ', age ) from stu where age < 30;
```



<br>
**2、字符个数 length(str)**

**格式:**
> select length('abc');
注意: 返回的是字符的字节长度

例2: 查询名字为2个自的学生
```
select * from stu where length(name)=6;
```


<br>
**3、截取字符串**
 - left(str, len) 返回字符串str左端len个字符
 - right(str, len) 返回字符串右端len个字符
 - substring(str,pos, len) 返回字符串str 的位置pos开始len个字符
    
**格式:**
> select substring('abc123',2,3);
 
例: 网站上很多,名字不显示全, 都显示的是 张xxx 等
```
select name, sex, concat(substring(name,0,3), sex) from stu ;
```


<br>
**4、去除空格**
- ltrim(str) 返回删除了左空格的字符串str
- rtrim(str) 返回删除了右空格的字符串str
 
    
       
 

     