#### 函数


#### 内置函数


#### 字符串函数
- 拼接字符串 concat(str1, str2 ...)

```
select concat(12,34,'ab');
```

- 包含字符个数 length(str)
```
select length('abc');
```
> 注意: select length(str) 返回的是字节数长度

- 截取字符串
    - left(str, len) 返回字符串str左端len个字符
    - right(str, len) 返回字符串右端len个字符
    - substring(str,pos, len) 返回字符串str 的位置pos开始len个字符
```
select substring('abc123',2,3);
```

- 去除空格
    - ltrim(str) 返回删除了左空格的字符串str
    - rtrim(str) 返回删除了右空格的字符串str
 
    
       
          
#### 综合示例

```
// 这样, 就可以直接返回查询后拼接的数据了
select name,age, concat(name ,'的年龄是: ', age ) from stu where age < 30;
```
     