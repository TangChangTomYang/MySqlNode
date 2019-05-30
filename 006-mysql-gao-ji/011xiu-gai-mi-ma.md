#### 修改密码

- 使用root 登录, 修改Mysql 数据库的 user 表
    - 使用password() 函数进行密码加密
    - 注意修改完成后要刷新权限
    
    
    
```
use mysql;

update user set password=password('新密码') where user='用户名';
```

例:
```
update user set password=password('123') where user='root';
flush privileges; // 刷新权限
```


#### 忘记root账户密码怎么办

1、配置mysql登录时不需要密码, 修改配置文件
    -centos 中: 配置文件为: /etc/my.cnf
    - Windows中为: C:\Program Files(x86)\MySQL\MySQL Server 5.1\my.ini

修改, 找到mysqlId, 在他的下一行, 添加skip-grant-tables

```
//step1: 配置未见修改为免密码登录
[mysql]
skip-grant-tables

//step2:  修改完后, 进入 mysql 修改登录密码

//step3: 将配置文件还原

```

