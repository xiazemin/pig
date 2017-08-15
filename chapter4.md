# Pig 运行脚本



## Pig脚本中的注释

在将脚本写入文件时，我们可以在其中包含注释，如下所示。

### 多行注释

我们将用'/\*'开始多行注释，以'\*/'结束。

```
/* These are the multi-line comments 
  In the pig script */ 

```

### 单行注释

我们将用“--"开始单行注释。

```
--we can write single line comments like this.

```

## 在批处理模式下执行Pig脚本

在以批处理方式执行Apache Pig语句时，请按照以下步骤操作。

### 步骤1

将所有需要的Pig Latin语句写在单个文件中。我们可以将所有Pig Latin语句和命令写入单个文件，并将其另存为**.pig**文件。

### 步骤2

执行Apache Pig脚本。你可以从shell（Linux）执行Pig脚本，如下所示。

| Local模式 | MapReduce模式 |
| :--- | :--- |
| $ pig -x local **Sample\_script.pig** | $ pig -x mapreduce **Sample\_script.pig** |

你可以使用exec命令从Grunt shell执行它，如下所示。

```
grunt
>
 exec /sample_script.pig

```

### 从HDFS执行Pig脚本

我们还可以执行驻留在HDFS中的Pig脚本。假设在名为**/pig\_data/**的HDFS目录中有名为**Sample\_script.pig**的Pig脚本。我们可以执行它如下所示。

```
$ pig -x mapreduce hdfs://localhost:9000/pig_data/Sample_script.pig 

```

### 例

假设在HDFS中有一个具有以下内容的文件**student\_details.txt**。

**student\_details.txt**

```
001,Rajiv,Reddy,21,9848022337,Hyderabad 
002,siddarth,Battacharya,22,9848022338,Kolkata
003,Rajesh,Khanna,22,9848022339,Delhi 
004,Preethi,Agarwal,21,9848022330,Pune 
005,Trupthi,Mohanthy,23,9848022336,Bhuwaneshwar 
006,Archana,Mishra,23,9848022335,Chennai 
007,Komal,Nayak,24,9848022334,trivendram 
008,Bharathi,Nambiayar,24,9848022333,Chennai

```

我们还在同一个HDFS目录中有一个名为**sample\_script.pig**的示例脚本。此文件包含对**student**关系执行操作和转换的语句，如下所示。

```
student = LOAD 'hdfs://localhost:9000/pig_data/student_details.txt' USING PigStorage(',')
   as (id:int, firstname:chararray, lastname:chararray, phone:chararray, city:chararray);
	
student_order = ORDER student BY age DESC;
  
student_limit = LIMIT student_order 4;
  
Dump student_limit;

```

* 脚本的第一个语句会将名为**student\_details.txt**的文件中的数据加载为名为**student**的关系。

* 脚本的第二个语句将根据年龄以降序排列关系的元组，并将其存储为**student\_order**。

* 脚本的第三个语句会将**student\_order**的前4个元组存储为**student\_limit**。

* 最后，第四个语句将转储关系**student\_limit**的内容。

现在，执行**sample\_script.pig**，如下所示。

```
$./pig -x mapreduce hdfs://localhost:9000/pig_data/sample_script.pig

```

Apache Pig被执行，并提供具有以下内容的输出。

```
(7,Komal,Nayak,24,9848022334,trivendram)
(8,Bharathi,Nambiayar,24,9848022333,Chennai) 
(5,Trupthi,Mohanthy,23,9848022336,Bhuwaneshwar) 
(6,Archana,Mishra,23,9848022335,Chennai)
2015-10-19 10:31:27,446 [main] INFO  org.apache.pig.Main - Pig script completed in 12
minutes, 32 seconds and 751 milliseconds (752751 ms)

```

  


