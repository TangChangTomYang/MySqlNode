#### 流程控制

- case语法: 等值判断

- 说明: 当值等于某个比较值的时候, 对应的结果会被返回, 如果所有的比较值都不相等则返回else的结果; 如果没有else并且所有比较值都不相等则返回null

```
select 
case 1 
when 1 then 'one'
when 2 then 'two'
else 'zero'
end as result;
```   


例1:

```
select name ,sex from stu;
//
select name, sex
case sex
when '男' then concat(left(name,1), '帅哥')
when '女' then concat(left(name,1), '美女')
else concat(left(name,1), 'xx')  end as result // 注意; 条件语句最后必须加 end as 把结果生成出来
from stu;

```