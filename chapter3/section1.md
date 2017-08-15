# Split运算符

**SPLIT**运算符用于将关系拆分为两个或多个关系。

## 语法

下面给出了**SPLIT**运算符的语法。

```
grunt>SPLIT Relation1_name INTO Relation2_name IF (condition1), Relation2_name (condition2),
```

grunt&gt; split student into student1 if id &lt;3 , student2 if id &gt;=3 and id &lt;5 ; dump student1 ; dump student2 ;

\(3,Rajesh,Khanna,9848022339,Delhi\)

\(4,Preethi,Agarwal,9848022330,Pune\)

