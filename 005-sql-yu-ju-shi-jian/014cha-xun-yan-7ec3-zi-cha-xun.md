#### 查询演练-子查询



准备数据:

```
delete table if exists goods;
create table goods(
    id int unsigned primary key auto_increment,
    name varchar(10),
    cate varchar(40),
    brand_name varchar(40),
    price decimal(10,3),
    is_show bit default 1,
    is_saleoff bit default 0
);


insert into goods values
(0, 'r510vc 15.6 英寸笔记本', '笔记本', '华硕','3399',default, default ),
(0, 'y400n 14.0英寸笔记本电脑', '笔记本', '联想','4999',default, default ),
(0, 'q150th 15.6英寸游戏本', '游戏本', '雷神','8499',default, default ),
(0, 'x550cc 15.6英寸笔记本', '笔记本', '华硕','2799',default, default ),
(0, 'x240 超级本', '超极本', '联想','4999',default, default ),
(0, 'u330p 13.3英寸超级本', '超级本', '联想','4299',default, default ),
(0, 'svp13226scb 触控超级本', '超级本', '索尼','7999',default, default ),
(0, 'ipad mini 7.9英寸平板电脑', '平板电脑', '苹果','1998',default, default ),
(0, 'ipad air 9.7英寸平板电脑', '平板电脑', '苹果','2788',default, default ),
(0, ' ', ' ', ' ',' ',default, default ),
(0, ' ', ' ', ' ',' ',default, default ),
(0, ' ', ' ', ' ',' ',default, default ),
(0, ' ', ' ', ' ',' ',default, default ),
(0, ' ', ' ', ' ',' ',default, default ),
(0, ' ', ' ', ' ',' ',default, default ),
(0, ' ', ' ', ' ',' ',default, default ),
(0, ' ', ' ', ' ',' ',default, default ),
(0, ' ', ' ', ' ',' ',default, default ),
(0, ' ', ' ', ' ',' ',default, default ),
(0, ' ', ' ', ' ',' ',default, default ),
(0, ' ', ' ', ' ',' ',default, default ),
(0, ' ', ' ', ' ',' ',default, default ),
(0, ' ', ' ', ' ',' ',default, default ),
(0, ' ', ' ', ' ',' ',default, default ),
(0, ' ', ' ', ' ',' ',default, default ),
(0, ' ', ' ', ' ',' ',default, default ),
(0, ' ', ' ', ' ',' ',default, default ),
(0, ' ', ' ', ' ',' ',default, default ),
(0, ' ', ' ', ' ',' ',default, default ),
(0, ' ', ' ', ' ',' ',default, default ),
(0, ' ', ' ', ' ',' ',default, default ),


