# 内置函数

Apache Pig提供了各种内置函数，即**eval，load，store，math，string，bag**和**tuple**函数。

## Eval函数

下面给出了Apache Pig提供的**eval**函数列表。

| S.N. | 函数 ＆  | 描述 |
| :--- | :--- | :--- |
|  | 1 | [AVG\(\)](https://www.w3cschool.cn/apache_pig/apache_pig_avg.html)计算包内数值的平均值。 |
|  | 2 | [BagToString\(\)](https://www.w3cschool.cn/apache_pig/apache_pig_bagtostring.html)将包的元素连接成字符串。在连接时，我们可以在这些值之间放置分隔符（可选）。 |
|  | 3 | [CONCAT\(\)](https://www.w3cschool.cn/apache_pig/apache_pig_concat.html)连接两个或多个相同类型的表达式。 |
|  | 4 | [COUNT\(\)](https://www.w3cschool.cn/apache_pig/apache_pig_count.html)获取包中元素的数量，同时计算包中元组的数量。 |
|  | 5 | [COUNT\_STAR\(\)](https://www.w3cschool.cn/apache_pig/apache_pig_count_star.html)它类似于**COUNT\(\) **函数。它用于获取包中的元素数量。 |
|  | 6 | [DIFF\(\)](https://www.w3cschool.cn/apache_pig/apache_pig_diff.html)比较元组中的两个包（字段）。 |
|  | 7 | [IsEmpty\(\)](https://www.w3cschool.cn/apache_pig/apache_pig_isempty.html)检查包或映射是否为空。 |
|  | 8 | [MAX\(\)](https://www.w3cschool.cn/apache_pig/apache_pig_max.html)计算单列包中的列（数值或字符）的最大值。 |
|  | 9 | [MIN\(\)](https://www.w3cschool.cn/apache_pig/apache_pig_min.html)要获取单列包中特定列的最小（最低）值（数字或字符）。 |
|  | 10 | [PluckTuple\(\)](https://www.w3cschool.cn/apache_pig/apache_pig_plucktuple.html)使用Pig Latin的 **PluckTuple\(\) **函数，可以定义字符串Prefix，并过滤以给定prefix开头的关系中的列。 |
|  | 11 | [SIZE\(\)](https://www.w3cschool.cn/apache_pig/apache_pig_size.html)基于任何Pig数据类型计算元素的数量。 |
|  | 12 | [SUBTRACT\(\)](https://www.w3cschool.cn/apache_pig/apache_pig_subtract.html)两个包相减，它需要两个包作为输入，并返回包含第一个包中不在第二个包中的元组的包。 |
|  | 13 | [SUM\(\)](https://www.w3cschool.cn/apache_pig/apache_pig_sum.html)要获取单列包中某列的数值总和。 |
|  | 14 | [TOKENIZE\(\)](https://www.w3cschool.cn/apache_pig/apache_pig_tokenize.html)要在单个元组中拆分字符串（其中包含一组字），并返回包含拆分操作的输出的包。 |

  




