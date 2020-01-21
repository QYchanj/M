Show databases (查看数据库名单)
Use 数据库名字  (调用某个数据库)


增 Insert:
  Insert into 表名<需要输入的记录对应的字段<1，2，3>  values<对应字段的内容 >
  不能默认数值的或者不能为空的 字段内容插入不能省略
  省略前方字段直接values必须全部内容都输入<null也要输入>

删 delete:   drop
   Delete from 表名 where 筛选条件(比如:列名=XXX 或 列名between A and B)
   Delete from 表名  （删所有行不删表）
   Delete top 数字或百分数 from 表名
   Delete from 表名 where
查 select：
  Select count(*) from 表名    (查询多少条记录)
  Select * from 表名 where 字段名 like XXX  （匹配like后面的文本进行筛选）
  Select * from 表名   (正序显示所有)
  Select  字段名，字段名 from 表名  (显示特定几个字段) 
  Select  top 数字或者数字加百分号 * from 表名   (显示top几的所有字段内容)
  Select * from 表名 where 字段名 (not)between A and B
  Select * from 表名 where 筛选条件（可多个） 
  Select * from 表名 where 字段名=xxx and/or字段名=xxx （and要两个都存在才返回数据，or则只要存在就返回）
  select * from 表名 where 字段名 in(字段名1,字段名2)

改:update 表名 set 字段=修改后的内容（可以用逗号隔开修改多个内容） where 筛选条件或者叫记录（id=1或name=XXX）


子语句：
Order by：select 字段1，字段2 from 表名 order by 字段1   （按字段1的排序显示字段1和2）
group by：在语句后面加个 group by 字段 ，所生成结果就按该字段的顺序排列

▲通配符_和%一般配合 like 使用 _占一个字格 %表示占一堆字格；
▲like‘%3’表示最后一个字是3的记录 like‘%3_’表示倒二是3的记录

