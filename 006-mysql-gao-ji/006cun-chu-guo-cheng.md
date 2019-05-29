#### 存储过程

什么是存储过程, 什么叫存储过程? 

通常情况下, 我们的MySql 客户端和 mysql服务端(数据库), 可能不在同一个地方, 通常都是客户端和服务端建立网络连接, 当客户端想要查询什么数据时, 通过网络把查询sql 语句传送个mysql 服务端, 服务端接收到数据后,根据sql语句查询具体数据后再返回结果


```
mysql 客户端 ----> 发送sql 语句---> mysql 服务端

mysql 客户端 <----返回查询数据<-----mysql 服务端
```

所谓的存储过程, 其实就是 mysql 客户端将常用的 sql 语句提前编写好存储到服务端, 到时客户端只需要调用 存储的方法即可



**语法: 创建存储过程sql 语句**
```
delimiter ##
create procedure 存储过程名(参数1, 参数2)
begin
sql语句1
sql语句2
...
end
## 
delimiter ;
```

**调用: **
```
call 存储过程(参数列表);
```



例: 定义一个存储过程, 在调用这个存储过程获取对应的数据

``` 
// 创建
delimiter ##
create procedure queryStr()
begin
select * from stu;
end
##
delimiter ;

// 调用
call queryStu();
```

