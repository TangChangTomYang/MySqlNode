#### mysql 自定义函数


**创建:**
- 语法如下: 

```
delimiter  ##  // delimiter 是定界符的意思, 此处delimiter  ##表示的是 将命令终端默认的定界符 ; 替换为 ##
create function 函数名(参数列表) returns 返回类型
begin
sql 语句
end
##    // 此处的## 表示的就是 执行以上语句
delimiter ; // 此处表示执行完后再改回来
```

> 说明: 
delimiter 用于设置定界符, 我们在终端上使用命令行执行mysql 语句时, 默认遇到分号就执行, 但是我们在定义函数时函数中间有分号, 因此我们要在定义函数前将 终端默认的 ; 定界符改为其他的符号(此处为##), 然后在编写 sql 函数, 函数编写完后使用 (##) 执行命令生成函数, 完了后再将定界符 修改了 ; , 这样就可以正常使用了



<br>
例如: 

```
delimiter ##  // 修改定界符
ceate function myTrim(str varchar(100)) returns varchar(100)
begin
return ltrim(rtrim(str));
end
##        // 使用定界符指定命令
delimiter ;  // 恢复默认的定界符
```


**注意:**
> 只有在命令终端时, 才需要修改默认的定界符, 在navicat 中创建函数是不需要修改定界符的