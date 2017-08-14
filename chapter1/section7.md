# Pig Latin

Pig Latin是用于使用Apache Pig分析Hadoop中数据的语言。在本章中，我们将讨论Pig Latin的基础知识，如Pig Latin语句，数据类型，通用运算符，关系运算符和Pig Latin UDF。

## Pig Latin - 数据模型

如前面章节所讨论的，Pig的数据模型是完全嵌套的。**Relation**是Pig Latin数据模型的最外层结构。它是一个**包**其中:

* 包是元组的集合。
* 元组是有序的字段集。
* 字段是一段数据。

## Pig Latin - 语句

在使用Pig Latin处理数据时，**语句**是基本结构。

* 这些语句使用**关系（relation）**，它们包括**表达式（expression）**和**模式（schema）**。

* 每个语句以分号（;）结尾。

* 我们将使用Pig Latin提供的运算符通过语句执行各种操作。

* 除了LOAD和STORE，在执行所有其他操作时，Pig Latin语句采用关系作为输入，并产生另一个关系作为输出。

* 只要在Grunt shell中输入**Load**语句，就会执行语义检查。要查看模式的内容，需要使用**Dump**运算符。只有在执行**dump**操作后，才会执行将数据加载到文件系统的MapReduce作业。

### 例子

下面给出一个Pig Latin语句，它将数据加载到Apache Pig中。

```
grunt
>
 Student_data = LOAD 'student_data.txt' USING PigStorage(',')as 
   ( id:int, firstname:chararray, lastname:chararray, phone:chararray, city:chararray );
```

## Pig Latin - 数据类型

下面给出的表描述了Pig Latin数据类型。

| 序号 | 数据类型 | 说明＆示例 |
| :--- | :--- | :--- |
| 1 | int | 表示有符号的32位整数。**示例**:8 |
| 2 | long | 表示有符号的64位整数。**示例**:5L |
| 3 | float | 表示有符号的32位浮点。**示例**:5.5F |
| 4 | double | 表示64位浮点。**示例**:10.5 |
| 5 | chararray | 表示Unicode UTF-8格式的字符数组（字符串）。**示例**:‘w3cschool’ |
| 6 | Bytearray | 表示字节数组（blob）。 |
| 7 | Boolean | 表示布尔值。**示例**:true / false。 |
| 8 | Datetime | 表示日期时间。**示例**:1970-01-01T00:00:00.000 + 00:00 |
| 9 | Biginteger | 表示Java BigInteger。**示例**:60708090709 |
| 10 | Bigdecimal | 表示Java BigDecimal**示例**:185.98376256272893883 |
|  |  | 复杂类型 |
| 11 | Tuple | 元组是有序的字段集。**示例**:（raja,30） |
| 12 | Bag | 包是元组的集合。**示例**:{（raju,30）,（Mohhammad,45）} |
| 13 | Map | 地图是一组键值对。**示例**:\['name'＃'Raju','age'＃30\] |

## Null值

所有上述数据类型的值可以为NULL。Apache Pig以与SQL类似的方式处理空值。null可以是未知值或不存在值，它用作可选值的占位符。这些空值可以自然出现或者可以是操作的结果。

## Pig Latin - 算术运算符

下表描述了Pig Latin的算术运算符。假设a = 10和b = 20。

| 运算符 | 描述 | 示例 |
| :--- | :--- | :--- |
| + | **加** - 运算符的两侧的值相加 | a+b将得出30 |
| − | **减** - 从运算符左边的数中减去右边的数 | a-b将得出-10 |
| \* | **乘** - 运算符两侧的值相乘 | a\*b将得出200 |
| / | **除**- 用运算符左边的数除右边的数 | b / a将得出2 |
| % | **系数**- 用运算符右边的数除左边的数并返回余数 | b％a将得出0 |
| ？: | **Bincond**- 评估布尔运算符。它有三个操作数，如下所示。变量**x**=（expression）？**value1**（如果为true）:**value2**（如果为false）。 | b =（a == 1）？20:30;如果a = 1，则b的值为20。如果a！= 1，则b的值为30。 |
| CASEWHENTHENELSEEND | **Case**- case运算符等效于嵌套的bincond运算符。 | CASE f2 ％ 2WHEN  0THEN'even' WHEN  1THEN'odd'END |

## Pig Latin - 比较运算符

下表描述了Pig Latin的比较运算符。

| 运算符 | 描述 | 示例 |
| :--- | :--- | :--- |
| == | **等于**- 检查两个数的值是否相等；如果是，则条件变为true。 | （a = b）不为true。 |
| != | **不等于**- 检查两个数的值是否相等。如果值不相等，则条件为true。 | （a！= b）为true。 |
| &gt; | **大于**- 检查左边数的值是否大于右边数的值。如果是，则条件变为true。 | （a&gt; b）不为true。 |
| &lt; | **小于**- 检查左边数的值是否小于右边数的值。如果是，则条件变为true。 | （a&lt;b）为true。 |
| &gt;= | **大于或等于**- 检查左边数的值是否大于或等于右边数的值。如果是，则条件变为true。 | （a&gt;=b）不为true。 |
| &lt;= | **小于或等于**- 检查左边数的值是否小于或等于右边数的值。如果是，则条件变为true。 | （a&lt;=b）为true。 |
| matches | **模式匹配**- 检查左侧的字符串是否与右侧的常量匹配。 | f1 matches '.\* tutorial.\*' |

## Pig Latin - 类型结构运算符

下表描述了Pig Latin的类型结构运算符。

| 运算符 | 描述 | 示例 |
| :--- | :--- | :--- |
| \(\) | **元组构造函数运算符**- 此运算符用于构建元组。 | （Raju,30） |
| {} | **包构造函数运算符**- 此运算符用于构造包。 | {（Raju,30）,（Mohammad,45）} |
| \[\] | **映射构造函数运算符**- 此运算符用于构造一个映射。 | \[name＃Raja,age＃30\] |

## Pig Latin - 关系运算符

下表描述了Pig Latin的关系运算符。

| 运算符 | 描述 |
| :--- | :--- |
|  | **加载和存储** |
| LOAD | 将数据从文件系统（local/ HDFS）加载到关系中。 |
| STORE | 将数据从文件系统（local/ HDFS）存储到关系中。 |
|  | 过滤 |
| FILTER | 从关系中删除不需要的行。 |
| DISTINCT | 从关系中删除重复行。 |
| FOREACH，GENERATE | 基于数据列生成数据转换。 |
| STREAM | 使用外部程序转换关系。 |
|  | 分组和连接 |
| JOIN | 连接两个或多个关系。 |
| COGROUP | 将数据分组为两个或多个关系。 |
| GROUP | 在单个关系中对数据进行分组。 |
| CROSS | 创建两个或多个关系的向量积。 |
|  | 排序 |
| ORDER | 基于一个或多个字段（升序或降序）按排序排列关系。 |
| LIMIT | 从关系中获取有限数量的元组。 |
|  | 合并和拆分 |
| UNION | 将两个或多个关系合并为单个关系。 |
| SPLIT | 将单个关系拆分为两个或多个关系。 |
|  | 诊断运算符 |
| DUMP | 在控制台上打印关系的内容。 |
| DESCRIBE | 描述关系的模式。 |
| EXPLAIN | 查看逻辑，物理或MapReduce执行计划以计算关系。 |
| ILLUSTRATE | 查看一系列语句的分步执行。 |



