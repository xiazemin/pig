# Cogroup运算符

COGROUP 运算符的运作方式与 GROUP 运算符相同。两个运算符之间的唯一区别是 group 运算符通常用于一个关系，而 cogroup 运算符用于涉及两个或多个关系的语句。

$ hdfs dfs -put ./employee.txt /input

$ hdfs dfs -cat /input/employee.txt

17/08/14 15:41:39 WARN util.NativeCodeLoader: Unable to load native-hadoop library for your platform... using builtin-java classes where applicable

001,Robin,22,newyork

002,BOB,23,Kolkata

003,Maya,23,Tokyo

004,Sara,25,London

005,David,23,Bhuwaneshwar

006,Maggy,22,Chennai

grunt&gt;     employee = load 'hdfs://localhost:8020/input/employee.txt' using PigStorage\(','\) as \(id:int,name:chararray,age:int,address:chararray\) ; dump employee ;

\(1,Robin,22,newyork \)

\(2,BOB,23,Kolkata \)

grunt&gt; cogroup\_data = cogroup student by age , employee by age ; dump cogroup\_data ;

\(18,{\(201000103,刘花,女,18,计算机应用技术\)},{}\)

\(19,{\(201000106,滑可,男,19,计算机系统结构\),\(201000105,吴达,男,19,计算机系统结构\),\(201000104,李肖,男,19,计算机系统结构\),\(201000102,王丽,女,19,计算机软件与理论\)},{}\)

\(20,{\(201000101,李勇,男,20,计算机软件与理论\)},{}\)

\(22,{},{\(6,Maggy,22,Chennai\),\(1,Robin,22,newyork \)}\)

\(23,{},{\(5,David,23,Bhuwaneshwar \),\(3,Maya,23,Tokyo \),\(2,BOB,23,Kolkata \)}\)

\(25,{},{\(4,Sara,25,London \)}\)

cogroup 运算符根据年龄对来自每个关系的元组进行分组，其中每个组描述特定的年龄值。

例如，如果我们考虑结果的第一个元组，它按照年龄21分组，那它包含两个包

第一个包保存了具有21岁的第一关系（在这种情况下是 student\_details ）的所有元组；

第二个包具有第二关系（在这种情况下为 employee\_details ）的所有元组，其年龄为21岁。

