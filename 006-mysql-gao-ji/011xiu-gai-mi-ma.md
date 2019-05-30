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