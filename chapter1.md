# Apache Pig 概述

## 什么是Apache Pig？

Apache Pig是MapReduce的一个抽象。它是一个工具/平台，用于分析较大的数据集，并将它们表示为数据流。Pig通常与**Hadoop**一起使用；我们可以使用Apache Pig在Hadoop中执行所有的数据处理操作。

要编写数据分析程序，Pig提供了一种称为**Pig Latin**的高级语言。该语言提供了各种操作符，程序员可以利用它们开发自己的用于读取，写入和处理数据的功能。

要使用**Apache Pig**分析数据，程序员需要使用Pig Latin语言编写脚本。所有这些脚本都在内部转换为Map和Reduce任务。Apache Pig有一个名为**Pig Engine**的组件，它接受Pig Latin脚本作为输入，并将这些脚本转换为MapReduce作业。

## 为什么我们需要Apache Pig？

不太擅长Java的程序员通常习惯于使用Hadoop，特别是在执行任一MapReduce作业时。Apache Pig是所有这样的程序员的福音。

* 使用**Pig Latin**，程序员可以轻松地执行MapReduce作业，而无需在Java中键入复杂的代码。

* Apache Pig使用**多查询方法**，从而减少代码长度。例如，需要在Java中输入200行代码（LoC）的操作在Apache Pig中输入少到10个LoC就能轻松完成。最终，Apache Pig将开发时间减少了近16倍。

* Pig Latin是**类似SQL的语言**，当你熟悉SQL后，很容易学习Apache Pig。

* Apache Pig提供了许多内置操作符来支持数据操作，如join，filter，ordering等。此外，它还提供嵌套数据类型，例如tuple（元组），bag（包）和MapReduce缺少的map（映射）。

## Apache Pig的特点

Apache Pig具有以下特点:

* **丰富的运算符集**- 它提供了许多运算符来执行诸如join，sort，filer等操作。

* **易于编程**- Pig Latin与SQL类似，如果你善于使用SQL，则很容易编写Pig脚本。

* **优化机会**- Apache Pig中的任务自动优化其执行，因此程序员只需要关注语言的语义。

* **可扩展性**- 使用现有的操作符，用户可以开发自己的功能来读取、处理和写入数据。

* **用户定义函数 **- Pig提供了在其他编程语言（如Java）中创建**用户定义函数**的功能，并且可以调用或嵌入到Pig脚本中。

* **处理各种数据**- Apache Pig分析各种数据，无论是结构化还是非结构化，它将结果存储在HDFS中。

## Apache Pig与MapReduce

下面列出的是Apache Pig和MapReduce之间的主要区别。

| Apache Pig | MapReduce |
| :--- | :--- |
| Apache Pig是一种数据流语言。 | MapReduce是一种数据处理模式。 |
| 它是一种高级语言。 | MapReduce是低级和刚性的。 |
| 在Apache Pig中执行Join操作非常简单。 | 在MapReduce中执行数据集之间的Join操作是非常困难的。 |
| 任何具备SQL基础知识的新手程序员都可以方便地使用Apache Pig工作。 | 向Java公开是必须使用MapReduce。 |
| Apache Pig使用多查询方法，从而在很大程度上减少代码的长度。 | MapReduce将需要几乎20倍的行数来执行相同的任务。 |
| 没有必要编译。执行时，每个Apache Pig操作符都在内部转换为MapReduce作业。 | MapReduce作业具有很长的编译过程。 |

## Apache Pig Vs SQL

下面列出了Apache Pig和SQL之间的主要区别。

| **Pig** | **SQL** |
| :--- | :--- |
| Pig Latin是一种**程序**语言。 | SQL是一种**声明式**语言。 |
| 在Apache Pig中，**模式**是可选的。我们可以存储数据而无需设计模式（值存储为$ 01，$ 02等） | 模式在SQL中是必需的。 |
| Apache Pig中的数据模型是**嵌套关系**。 | SQL 中使用的数据模型是**平面关系**。 |
| Apache Pig为**查询优化**提供有限的机会。 | 在SQL中有更多的机会进行查询优化。 |

除了上面的区别，Apache Pig Latin:

* 允许在pipeline（流水线）中拆分。
* 允许开发人员在pipeline中的任何位置存储数据。
* 声明执行计划。
* 提供运算符来执行ETL（Extract提取，Transform转换和Load加载）功能。

## Apache Pig VS Hive

Apache Pig和Hive都用于创建MapReduce作业。在某些情况下，Hive以与Apache Pig类似的方式在HDFS上运行。在下表中，我们列出了几个重要的点区分Apache Pig与Hive。

| Apache Pig | Hive |
| :--- | :--- |
| Apache Pig使用一种名为**Pig Latin**的语言（最初创建于**Yahoo**）。 | Hive使用一种名为**HiveQL**的语言（最初创建于**Facebook**）。 |
| Pig Latin是一种数据流语言。 | HiveQL是一种查询处理语言。 |
| Pig Latin是一个过程语言，它适合流水线范式。 | HiveQL是一种声明性语言。 |
| Apache Pig可以处理结构化，非结构化和半结构化数据。 | Hive主要用于结构化数据。 |

## Apache Pig的应用程序

Apache Pig通常被数据科学家用于执行涉及特定处理和快速原型设计的任务。使用Apache Pig:

* 处理巨大的数据源，如Web日志。
* 为搜索平台执行数据处理。
* 处理时间敏感数据的加载。



