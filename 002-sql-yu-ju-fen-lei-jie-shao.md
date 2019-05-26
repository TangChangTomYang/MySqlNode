#### SQL 
 
 > Structure Query Language
 结构化查询语言
 
 在数据库中进行操作的语言, 称为sql, 结构化查询语言, 当前的关系型数据库都支持sql 语言进行操作, 也就是说可以通过sql 操作 **Oracle、mySql、ms sql server、 sqlite** 等等的关系型数据库
 
 - **sql 语言主要分为: **
  - **DQL:** 数据查询语言, 用于对数据进行查询, eg: select
  - **DML:** 数据操作语言, 对数据进行增 删 改, eg: insert、delete、 update
  - **TPL:** 事物处理语言,对事物进行处理,包括begin 、transaction、commit、rollback
  - **DCL:** 数据控制语言, 进行授权与权限回收,如 : grant、revoke
  - **DDL:** 数据定义语句,进行数据库、表的管理等,如: create、drop
  - **CCL:** 指针控制语句, 通过控制指针完成表的操作,如: declare cursor
  
 对于测试工程师而言, 重点是数据的查询,需要熟练掌握DQL的编写, 其他的语言l了解即可
 SQL 是一门特殊的语言,专门用于访问操作数据库, 不区分大小写