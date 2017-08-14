# Join运算符

JOIN 运算符用于组合来自两个或多个关系的记录。在执行连接操作时，我们从每个关系中声明一个（或一组）元组作为key。 当这些key匹配时，两个特定的元组匹配，否则记录将被丢弃。连接可以是以下类型：

Self-join

Inner-join

Outer-join − left join, right join, and full join

$ hdfs dfs -put ./customers.txt /input

$ hdfs dfs -put ./orders.txt /input

grunt&gt; customers = load 'hdfs://localhost:8020/input/customers.txt' using PigStorage\(','\) as \(id:int, name:chararray, age:int, address:chararray, salary:int\); orders = LOAD 'hdfs://localhost:8020/input/orders.txt' USING PigStorage\(','\)  as \(oid:int, date:chararray, customer\_id:int, amount:int\);

## Self-join（自连接）

**Self-join **用于将表与其自身连接，就像表是两个关系一样，临时重命名至少一个关系。通常，在Apache Pig中，为了执行self-join，我们将在不同的别名（名称）下多次加载相同的数据。那么，将文件**customers.txt**的内容加载为两个表

下面给出使用 JOIN 运算符执行self-join操作的语法。

grunt&gt; Relation3\_name = JOIN Relation1\_name BY key, Relation2\_name BY key ;

grunt&gt; self\_join\_data = join customers1 by  id , customers by id ; dump self\_join\_data ;

\(1,Ramesh,32,Ahmedabad,2000,1,Ramesh,32,Ahmedabad,2000\)

\(2,Khilan,25,Delhi,1500,2,Khilan,25,Delhi,1500\)

\(3,kaushik,23,Kota,2000,3,kaushik,23,Kota,2000\)

\(4,Chaitali,25,Mumbai,6500,4,Chaitali,25,Mumbai,6500\)

\(5,Hardik,27,Bhopal,8500,5,Hardik,27,Bhopal,8500\)

\(6,Komal,22,MP,4500,6,Komal,22,MP,4500\)

\(7,Muffy,24,Indore,10000,7,Muffy,24,Indore,10000\)

