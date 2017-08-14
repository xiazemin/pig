# Cross运算符

**CROSS**运算符计算两个或多个关系的向量积。本章将以示例说明如何在Pig Latin中使用cross运算符。

## 语法

下面给出了**CROSS**运算符的语法。

```
grunt>Relation3_name = CROSS Relation1_name, Relation2_name;
```

grunt&gt;  cross\_data = CROSS customers, orders; dump cross\_data ;

\(7,Muffy,24,Indore,10000,103,2008-05-20 00:00:00,4,2060\)

\(7,Muffy,24,Indore,10000,101,2009-11-20 00:00:00,2,1560\)

\(7,Muffy,24,Indore,10000,100,2009-10-08 00:00:00,3,1500\)

\(7,Muffy,24,Indore,10000,102,2009-10-08 00:00:00,3,3000\)

\(6,Komal,22,MP,4500,103,2008-05-20 00:00:00,4,2060\)



