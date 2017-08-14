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

## Inner Join（内部连接）

**Inner Join**使用较为频繁；它也被称为**等值连接**。当两个表中都存在匹配时，内部连接将返回行。基于连接谓词（join-predicate），通过组合两个关系（例如A和B）的列值来创建新关系。查询将A的每一行与B的每一行进行比较，以查找满足连接谓词的所有行对。当连接谓词被满足时，A和B的每个匹配的行对的列值被组合成结果行。

### 语法

以下是使用**JOIN**运算符执行**inner join**操作的语法。

```
grunt>result = JOIN relation1 BY columnname, relation2 BY columnname;
```

grunt&gt; coustomer\_orders = JOIN customers BY id, orders BY customer\_id; dump coustomer\_orders ;

\(2,Khilan,25,Delhi,1500,101,2009-11-20 00:00:00,2,1560\)

\(3,kaushik,23,Kota,2000,100,2009-10-08 00:00:00,3,1500\)

\(3,kaushik,23,Kota,2000,102,2009-10-08 00:00:00,3,3000\)

\(4,Chaitali,25,Mumbai,6500,103,2008-05-20 00:00:00,4,2060\)

**注意**：

Outer Join：与inner join不同，**outer join**返回至少一个关系中的所有行。outer join操作以三种方式执行：

* Left outer join
* Right outer join
* Full outer join

## Left Outer Join（左外连接）

**left outer join**操作返回左表中的所有行，即使右边的关系中没有匹配项。

### 语法

下面给出使用**JOIN**运算符执行**left outer join**操作的语法。

grunt&gt; Relation3\_name = JOIN Relation1\_name BY id LEFT OUTER, Relation2\_name BY customer\_id;

grunt&gt; outer\_left = JOIN customers BY id LEFT OUTER, orders BY customer\_id; dump outer\_left ;

\(1,Ramesh,32,Ahmedabad,2000,,,,\)

\(2,Khilan,25,Delhi,1500,101,2009-11-20 00:00:00,2,1560\)

\(3,kaushik,23,Kota,2000,100,2009-10-08 00:00:00,3,1500\)

\(3,kaushik,23,Kota,2000,102,2009-10-08 00:00:00,3,3000\)

\(4,Chaitali,25,Mumbai,6500,103,2008-05-20 00:00:00,4,2060\)

\(5,Hardik,27,Bhopal,8500,,,,\)

\(6,Komal,22,MP,4500,,,,\)

\(7,Muffy,24,Indore,10000,,,,\)

## Right Outer Join（右外连接）

**right outer join**操作将返回右表中的所有行，即使左表中没有匹配项。

### 语法

下面给出使用**JOIN**运算符执行**right outer join**操作的语法。

grunt&gt; outer\_right = JOIN customers BY id RIGHT, orders BY customer\_id;

grunt&gt;  outer\_right = JOIN customers BY id RIGHT, orders BY customer\_id; dump outer\_right ;

\(2,Khilan,25,Delhi,1500,101,2009-11-20 00:00:00,2,1560\)

\(3,kaushik,23,Kota,2000,100,2009-10-08 00:00:00,3,1500\)

\(3,kaushik,23,Kota,2000,102,2009-10-08 00:00:00,3,3000\)

\(4,Chaitali,25,Mumbai,6500,103,2008-05-20 00:00:00,4,2060\)

## Full Outer Join（全外连接）

当一个关系中存在匹配时，**full outer join**操作将返回行。

### 语法

下面给出使用**JOIN**运算符执行**full outer join**的语法。

```
grunt>outer_full = JOIN customers BY id FULL OUTER, orders BY customer_id;
```

grunt&gt;  outer\_full = JOIN customers BY id FULL OUTER, orders BY customer\_id; dump outer\_full ;

\(1,Ramesh,32,Ahmedabad,2000,,,,\)

\(2,Khilan,25,Delhi,1500,101,2009-11-20 00:00:00,2,1560\)

\(3,kaushik,23,Kota,2000,100,2009-10-08 00:00:00,3,1500\)

\(3,kaushik,23,Kota,2000,102,2009-10-08 00:00:00,3,3000\)

\(4,Chaitali,25,Mumbai,6500,103,2008-05-20 00:00:00,4,2060\)

\(5,Hardik,27,Bhopal,8500,,,,\)

\(6,Komal,22,MP,4500,,,,\)

\(7,Muffy,24,Indore,10000,,,,\)

使用多个Key

我们可以使用多个key执行JOIN操作。

语法

下面是如何使用多个key对两个表执行JOIN操作。

grunt&gt; Relation3\_name = JOIN Relation2\_name BY \(key1, key2\), Relation3\_name BY \(key1, key2\);

$ hdfs dfs -put ./employee\_contact.txt /input

grunt&gt;  employee\_contact = LOAD 'hdfs://localhost:8020/input/employee\_contact.txt' USING PigStorage\(','\)   as \(id:int, phone:chararray, email:chararray, city:chararray, jobid:int\); dump employee\_contact ;

\(1,9848022337,Rajiv@gmail.com,Hyderabad,3\)

\(2,9848022338,siddarth@gmail.com,Kolkata,3\)

\(3,9848022339,Rajesh@gmail.com,Delhi,3\)

\(4,9848022330,Preethi@gmail.com,Pune,3\)

\(5,9848022336,Trupthi@gmail.com,Bhuwaneshwar,3\)

\(6,9848022335,Archana@gmail.com,Chennai,3\)

\(7,9848022334,Komal@gmail.com,trivendram,2\)

\(8,9848022333,Bharathi@gmail.com,Chennai,1\)

$ hdfs dfs -put ./employer.txt /input

grunt&gt; employer = load 'hdfs://localhost:8020/input/employer.txt' using PigStorage\(','\) as  \(id:int, firstname:chararray, lastname:chararray, age:int, designation:chararray, jobid:int\); dump employer ;

\(1,Rajiv,Reddy,21,programmer,3\)

\(2,siddarth,Battacharya,22,programmer,3\)

\(3,Rajesh,Khanna,22,programmer,3\)

\(4,Preethi,Agarwal,21,programmer,3\)

\(5,Trupthi,Mohanthy,23,programmer,3\)

\(6,Archana,Mishra,23,programmer,3\)

\(7,Komal,Nayak,24,teamlead,2\)

\(8,Bharathi,Nambiayar,24,manager,1\)

grunt&gt;  emp = JOIN employer BY \(id,jobid\), employee\_contact BY \(id,jobid\); dump emp ;

\(1,Rajiv,Reddy,21,programmer,3,1,9848022337,Rajiv@gmail.com,Hyderabad,3\)

\(2,siddarth,Battacharya,22,programmer,3,2,9848022338,siddarth@gmail.com,Kolkata,3\)

\(3,Rajesh,Khanna,22,programmer,3,3,9848022339,Rajesh@gmail.com,Delhi,3\)

\(4,Preethi,Agarwal,21,programmer,3,4,9848022330,Preethi@gmail.com,Pune,3\)

\(5,Trupthi,Mohanthy,23,programmer,3,5,9848022336,Trupthi@gmail.com,Bhuwaneshwar,3\)

\(6,Archana,Mishra,23,programmer,3,6,9848022335,Archana@gmail.com,Chennai,3\)

\(7,Komal,Nayak,24,teamlead,2,7,9848022334,Komal@gmail.com,trivendram,2\)

\(8,Bharathi,Nambiayar,24,manager,1,8,9848022333,Bharathi@gmail.com,Chennai,1\)



