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

* **function**- 我们必须从Apache Pig提供的一组加载函数中选择一个函数（** BinStorage，JsonLoader，PigStorage，TextLoader **）。

* **Schema**- 我们必须定义数据的模式，可以定义所需的模式如下 -

```
(column1 : data type, column2 : data type, column3 : data type);

```

**注意**:我们加载数据而不指定模式。在这种情况下，列将被寻址为$01，$02，等...（检查）。



