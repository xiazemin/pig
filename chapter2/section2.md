# Diagnostic运算符

Pig Latin提供四种不同类型的诊断运算符:

Dump运算符

Describe运算符

Explanation运算符

Illustration运算符

Dump运算符

Dump 运算符用于运行Pig Latin语句，并在屏幕上显示结果，它通常用于调试目的。

语法

下面给出了 Dump 运算符的语法。

grunt&gt; Dump Relation\_Name

describe 运算符用于查看关系的模式。

语法

describe 运算符的语法如下

grunt&gt; Describe Relation\_name

grunt&gt;     describe student;

student: {id: int,name: chararray,sex: chararray,age: int,class: chararray}

explain 运算符用于显示关系的逻辑，物理和MapReduce执行计划。

语法

下面给出了 explain 运算符的语法。

grunt&gt; explain Relation\_name;

grunt&gt; explain student;

2017-08-14 15:24:06,426 \[main\] WARN  org.apache.pig.data.SchemaTupleBackend - SchemaTupleBackend has already been initialized

2017-08-14 15:24:06,426 \[main\] INFO  org.apache.pig.newplan.logical.optimizer.LogicalPlanOptimizer - {RULES\_ENABLED=\[AddForEach, ColumnMapKeyPrune, ConstantCalculator, GroupByConstParallelSetter, LimitOptimizer, LoadTypeCastInserter, MergeFilter, MergeForEach, NestedLimitOptimizer, PartitionFilterOptimizer, PredicatePushdownOptimizer, PushDownForEachFlatten, PushUpFilter, SplitFilter, StreamTypeCastInserter\]}

\#-----------------------------------------------

\# New Logical Plan:

\#-----------------------------------------------

student: \(Name: LOStore Schema: id\#145:int,name\#146:chararray,sex\#147:chararray,age\#148:int,class\#149:chararray\)

\|

\|---student: \(Name: LOForEach Schema: id\#145:int,name\#146:chararray,sex\#147:chararray,age\#148:int,class\#149:chararray\)

```
\|   \|

\|   \(Name: LOGenerate\[false,false,false,false,false\] Schema: id\#145:int,name\#146:chararray,sex\#147:chararray,age\#148:int,class\#149:chararray\)ColumnPrune:OutputUids=\[145, 146, 147, 148, 149\]ColumnPrune:InputUids=\[145, 146, 147, 148, 149\]

\|   \|   \|

\|   \|   \(Name: Cast Type: int Uid: 145\)

\|   \|   \|

\|   \|   \|---id:\(Name: Project Type: bytearray Uid: 145 Input: 0 Column: \(\*\)\)

\|   \|   \|

\|   \|   \(Name: Cast Type: chararray Uid: 146\)

\|   \|   \|

\|   \|   \|---name:\(Name: Project Type: bytearray Uid: 146 Input: 1 Column: \(\*\)\)

\|   \|   \|

\|   \|   \(Name: Cast Type: chararray Uid: 147\)

\|   \|   \|

\|   \|   \|---sex:\(Name: Project Type: bytearray Uid: 147 Input: 2 Column: \(\*\)\)

\|   \|   \|

\|   \|   \(Name: Cast Type: int Uid: 148\)

\|   \|   \|

\|   \|   \|---age:\(Name: Project Type: bytearray Uid: 148 Input: 3 Column: \(\*\)\)

\|   \|   \|

\|   \|   \(Name: Cast Type: chararray Uid: 149\)

\|   \|   \|

\|   \|   \|---class:\(Name: Project Type: bytearray Uid: 149 Input: 4 Column: \(\*\)\)

\|   \|

\|   \|---\(Name: LOInnerLoad\[0\] Schema: id\#145:bytearray\)

\|   \|

\|   \|---\(Name: LOInnerLoad\[1\] Schema: name\#146:bytearray\)

\|   \|

\|   \|---\(Name: LOInnerLoad\[2\] Schema: sex\#147:bytearray\)

\|   \|

\|   \|---\(Name: LOInnerLoad\[3\] Schema: age\#148:bytearray\)

\|   \|

\|   \|---\(Name: LOInnerLoad\[4\] Schema: class\#149:bytearray\)

\|

\|---student: \(Name: LOLoad Schema: id\#145:bytearray,name\#146:bytearray,sex\#147:bytearray,age\#148:bytearray,class\#149:bytearray\)RequiredFields:null
```

\#-----------------------------------------------

\# Physical Plan:

\#-----------------------------------------------

\#--------------------------------------------------

\# Map Reduce Plan

\#--------------------------------------------------

MapReduce node scope-56

Map Plan

illustrate 运算符为你提供了一系列语句的逐步执行。

语法

下面给出了illustrate运算符的语法。

grunt&gt; illustrate Relation\_name;

grunt&gt;  illustrate student;

---------------------------------------------------------------------------------------------------------

\| student     \| id:int     \| name:chararray     \| sex:chararray     \| age:int     \| class:chararray     \|

---------------------------------------------------------------------------------------------------------

\|             \| 201000103  \| 刘花                 \| 女                 \| 18          \| 计算机应用技术             \|

---------------------------------------------------------------------------------------------------------

