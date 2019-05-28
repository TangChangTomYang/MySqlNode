#### 函数


#### 内置函数


<br>
#### 一、字符串函数

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
- trim(str)  返回删除了左右空格的字符串str


 **格式:** 
 > select ltrim('   abc   ');
 
 
 <br>
 **5、大小写转换**
 - lower(str)
 - upper(str)
 
 **格式:**
 > select lower('aBcD');
 
 
 
 
 
<br>
#### 二、数学函数

**1、求四舍五入值**
 
** 格式:**
> select round(n,d); // n表示的是原数, d 表示的是小数位数默认为0
这个四舍五入,会把多余的位数进行4舍五入, 
比如: round(1.61,1) ---> 1.6
round(1.65,1) ---> 1.7


**2、求 x的y次幂 pow(x,y)**       
 > pow(2,3) --> 8
 
 
 **3、获取圆周率**
 ```
 select PI();
 ```
 
 **4、随机数, rand(), 置位 0~1.0**
 ```
 select rand();
 ```
 
 例:随机取出一条记录
 ```
 select *,rand() from stu order by rand() limit 1;
 // 也可以这样写
 select * from stu order by rand() limit 1;
 
 ```
 
#### 日期时间函数

**1、当前日期: current_date()**
```
select current_date();
```


**2、当前时间: current_time()**
```
select current_time();
```

     
**3、当前日期时间 now()**   
```
select now();
```

  **4、日期格式化: date_format(date,format)**  
  
  > 参数format 可选
  ```
  %Y 获取年, 返回完整年
  %y 获取年, 返回简写年份
  %m 获取月, 返回月份
  %d 返回日, 返回天 
  %H 获取时, 返回24小时进制小时数
  %h 获取时, 返回12进制小时数
  %i 获取分钟, 返回分钟数
  %s 获取秒, 返回秒数
  ```
  
  例:将使用-拼接的日期转换为使用空格拼接
  ```
  select date_format('2016-12-21', '%Y %m %d');
  
  ```
  
  