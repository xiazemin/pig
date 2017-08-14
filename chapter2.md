# 加载数据

## Load运算符

你可以使用**Pig Latin**的**LOAD**运算符，从文件系统（HDFS / Local）将数据加载到Apache Pig中。

### 语法

load语句由两部分组成，用“=”运算符分隔。在左侧，需要提到我们想要存储数据的关系的**名称**；而在右侧，我们需要定义如何存储数据。下面给出了**Load**运算符的语法。

```
Relation_name = LOAD 'Input file path' USING function as schema;
```

说明:

* **relation\_name**- 我们必须提到要存储数据的关系。

* **Input file path**- 我们必须提到存储文件的HDFS目录。（在MapReduce模式下）

* **function**- 我们必须从Apache Pig提供的一组加载函数中选择一个函数（** BinStorage，JsonLoader，PigStorage，TextLoader **）。

* **Schema**- 我们必须定义数据的模式，可以定义所需的模式如下 -

```
(column1 : data type, column2 : data type, column3 : data type);
```

**注意**:我们加载数据而不指定模式。在这种情况下，列将被寻址为$01，$02，等...（检查）。

$ hdfs dfs -cat  /input/test.txt

17/08/14 15:09:49 WARN util.NativeCodeLoader: Unable to load native-hadoop library for your platform... using builtin-java classes where applicable

201000101:李勇:男:20:计算机软件与理论

201000102:王丽:女:19:计算机软件与理论

201000103:刘花:女:18:计算机应用技术

201000104:李肖:男:19:计算机系统结构

201000105:吴达:男:19:计算机系统结构

201000106:滑可:男:19:计算机系统结构

grunt&gt; student = load 'hdfs://localhost:8020/input/test.txt' using PigStorage\(':'\) as \(id:int,name:chararray,sex:chararray,age:int,class:chararray\); dump student;

HadoopVersion    PigVersion    UserId    StartedAt    FinishedAt    Features

2.6.4    0.17.0    didi    2017-08-14 15:12:49    2017-08-14 15:12:56    UNKNOWN

Success!

Job Stats \(time in seconds\):

JobId    Maps    Reduces    MaxMapTime    MinMapTime    AvgMapTime    MedianMapTime    MaxReduceTime    MinReduceTime    AvgReduceTime    MedianReducetime    Alias    Feature    Outputs

job\_local1916643951\_0001    1    0    n/a    n/a    n/a    n/a    0    0    00    student    MAP\_ONLY    hdfs://localhost:8020/tmp/temp15605266/tmp-496689102,

Input\(s\):

Successfully read 6 records \(5756064 bytes\) from: "hdfs://localhost:8020/input/test.txt"

Output\(s\):

Successfully stored 6 records \(5756088 bytes\) in: "hdfs://localhost:8020/tmp/temp15605266/tmp-496689102"

Counters:

Total records written : 6

Total bytes written : 5756088

Spillable Memory Manager spill count : 0

Total bags proactively spilled: 0

Total records proactively spilled: 0

Job DAG:

job\_local1916643951\_0001

\(201000101,李勇,男,20,计算机软件与理论\)

\(201000102,王丽,女,19,计算机软件与理论\)

\(201000103,刘花,女,18,计算机应用技术\)

\(201000104,李肖,男,19,计算机系统结构\)

\(201000105,吴达,男,19,计算机系统结构\)

\(201000106,滑可,男,19,计算机系统结构\)

| Relation name |
| :--- |


|  | 我们已将数据存储在**学生（student）**模式中。 |
| :--- | :--- |
| Input file path | 我们从HDFS的/pig\_data/目录中的**student\_data.txt**文件读取数据。 |
| Storage function | 我们使用了**PigStorage\(\) **函数，将数据加载并存储为结构化文本文件。它采用分隔符，使用元组的每个实体作为参数分隔。默认情况下，它以“\t"作为参数。 |
| schema | 我们已经使用以下模式存储了数据。columnid名字姓氏电话号码城市datatypeintchar arraychar arraychar arraychar array |

**注意**:**Load**语句会简单地将数据加载到Pig的指定的关系中。要验证**Load**语句的执行情况，必须使用**Diagnostic运算符**

