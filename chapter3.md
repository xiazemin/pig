# Union运算符

Pig Latin的 UNION 运算符用于合并两个关系的内容。要对两个关系执行UNION操作，它们的列和域必须相同。

语法

下面给出了 UNION 运算符的语法。

grunt&gt; Relation\_name3 = UNION Relation\_name1, Relation\_name2;

$ hdfs dfs -put student1.txt /input

$ hdfs dfs -put student2.txt /input

$ hdfs dfs -cat /input/student2.txt

17/08/15 10:00:19 WARN util.NativeCodeLoader: Unable to load native-hadoop library for your platform... using builtin-java classes where applicable

7,Komal,Nayak,9848022334,trivendram.

8,Bharathi,Nambiayar,9848022333,Chennai.

grunt&gt;   student1 = load 'hdfs://localhost:8020/input/student1.txt' using PigStorage\(','\) as \(id:int, firstname:chararray, lastname:chararray, phone:chararray, city:chararray\);  student2 = load 'hdfs://localhost:8020/input/student2.txt' using PigStorage\(','\) as \(id:int, firstname:chararray, lastname:chararray, phone:chararray, city:chararray\); student = union student1 , student2 ; dump student ;

\(1,Rajiv,Reddy,9848022337,Hyderabad\)

\(2,siddarth,Battacharya,9848022338,Kolkata\)

\(3,Rajesh,Khanna,9848022339,Delhi\)

\(4,Preethi,Agarwal,9848022330,Pune\)

\(5,Trupthi,Mohanthy,9848022336,Bhuwaneshwar\)

\(6,Archana,Mishra,9848022335,Chennai.\)

\(7,Komal,Nayak,9848022334,trivendram.\)

\(8,Bharathi,Nambiayar,9848022333,Chennai.\)



