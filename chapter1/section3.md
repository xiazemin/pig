# Apache Pig 执行



## Apache Pig执行模式

你可以以两种模式运行Apache Pig，即**Local（本地）模式**和**HDFS模式**。

### Local模式

在此模式下，所有文件都从本地主机和本地文件系统安装和运行，不需要Hadoop或HDFS。此模式通常用于测试目的。

### MapReduce模式

MapReduce模式是我们使用Apache Pig加载或处理Hadoop文件系统（HDFS）中存在的数据的地方。在这种模式下，每当我们执行Pig Latin语句来处理数据时，会在后端调用一个MapReduce作业，以对HDFS中存在的数据执行特定的操作。

## Apache Pig执行机制

Apache Pig脚本可以通过三种方式执行，即交互模式，批处理模式和嵌入式模式。

* **交互模式**（Grunt shell） - 你可以使用Grunt shell以交互模式运行Apache Pig。在此shell中，你可以输入Pig Latin语句并获取输出（使用Dump运算符）。

* **批处理模式**（脚本） - 你可以通过将Pig Latin脚本写入具有**.pig**扩展名的单个文件中，以批处理模式运行Apache Pig。

* **嵌入式模式**（UDF） - Apache Pig允许在Java等编程语言中定义我们自己的函数（**UDF**用户定义函数），并在我们的脚本中使用它们。

## 调用Grunt Shell

你可以使用“**-x**"选项以所需的模式（local/MapReduce）调用Grunt shell，如下所示。

| Local模式 | MapReduce模式 |
| :--- | :--- |
| **Command（命令） -**$ ./pig -x local | **Command（命令）**-$ ./pig -x mapreduce |
| **Output（输出）**-![](https://www.w3cschool.cn/attachments/tuploads/apache_pig/local_mode_output.jpg "Local Mode Output") | **Output（输出）**-![](https://www.w3cschool.cn/attachments/tuploads/apache_pig/mapreduce_mode_output.jpg "MapReduce Mode Output") |

这两个命令都给出了Grunt shell提示符，如下所示。

```
grunt
>
```

你可以使用“**ctrl+d**"退出Grunt shell。

在调用Grunt shell之后，可以通过直接输入Pig中的Pig Latin语句来执行Pig脚本。

```
grunt
>
 customers = LOAD 'customers.txt' USING PigStorage(',');

```

## 在批处理模式下执行Apache Pig

你可以在文件中编写整个Pig Latin脚本，并使用**-x command **执行它。我们假设在一个名为**sample\_script.pig**的文件中有一个Pig脚本，如下所示。

### Sample\_script.pig

```
student = LOAD 'hdfs://localhost:9000/pig_data/student.txt' USING
   PigStorage(',') as (id:int,name:chararray,city:chararray);
  
Dump student;

```

现在，你可以在上面的文件中执行脚本，如下所示。

| Local模式 | MapReduce模式 |
| :--- | :--- |
| $ pig -x local**Sample\_script.pig** | $ pig -x mapreduce**Sample\_script.pig** |

**注意**:我们将详细讨论如何在**批处理模式**和**嵌入模式**中运行Pig脚本。

