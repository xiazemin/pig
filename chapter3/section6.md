# 内置函数

Apache Pig提供了各种内置函数，即**eval，load，store，math，string，bag**和**tuple**函数。

## Eval函数

下面给出了Apache Pig提供的**eval**函数列表。

| S.N. | 函数 ＆ | 描述 |
| :--- | :--- | :--- |
|  | 1 | [AVG\(\)](https://www.w3cschool.cn/apache_pig/apache_pig_avg.html)计算包内数值的平均值。 |
|  | 2 | [BagToString\(\)](https://www.w3cschool.cn/apache_pig/apache_pig_bagtostring.html)将包的元素连接成字符串。在连接时，我们可以在这些值之间放置分隔符（可选）。 |
|  | 3 | [CONCAT\(\)](https://www.w3cschool.cn/apache_pig/apache_pig_concat.html)连接两个或多个相同类型的表达式。 |
|  | 4 | [COUNT\(\)](https://www.w3cschool.cn/apache_pig/apache_pig_count.html)获取包中元素的数量，同时计算包中元组的数量。 |
|  | 5 | [COUNT\_STAR\(\)](https://www.w3cschool.cn/apache_pig/apache_pig_count_star.html)它类似于**COUNT\(\) **函数。它用于获取包中的元素数量。 |
|  | 6 | [DIFF\(\)](https://www.w3cschool.cn/apache_pig/apache_pig_diff.html)比较元组中的两个包（字段）。 |
|  | 7 | [IsEmpty\(\)](https://www.w3cschool.cn/apache_pig/apache_pig_isempty.html)检查包或映射是否为空。 |
|  | 8 | [MAX\(\)](https://www.w3cschool.cn/apache_pig/apache_pig_max.html)计算单列包中的列（数值或字符）的最大值。 |
|  | 9 | [MIN\(\)](https://www.w3cschool.cn/apache_pig/apache_pig_min.html)要获取单列包中特定列的最小（最低）值（数字或字符）。 |
|  | 10 | [PluckTuple\(\)](https://www.w3cschool.cn/apache_pig/apache_pig_plucktuple.html)使用Pig Latin的 **PluckTuple\(\) **函数，可以定义字符串Prefix，并过滤以给定prefix开头的关系中的列。 |
|  | 11 | [SIZE\(\)](https://www.w3cschool.cn/apache_pig/apache_pig_size.html)基于任何Pig数据类型计算元素的数量。 |
|  | 12 | [SUBTRACT\(\)](https://www.w3cschool.cn/apache_pig/apache_pig_subtract.html)两个包相减，它需要两个包作为输入，并返回包含第一个包中不在第二个包中的元组的包。 |
|  | 13 | [SUM\(\)](https://www.w3cschool.cn/apache_pig/apache_pig_sum.html)要获取单列包中某列的数值总和。 |
|  | 14 | [TOKENIZE\(\)](https://www.w3cschool.cn/apache_pig/apache_pig_tokenize.html)要在单个元组中拆分字符串（其中包含一组字），并返回包含拆分操作的输出的包。 |

Apache Pig中的**加载**和**存储**函数用于确定数据如何从Pig中弹出。这些函数与加载和存储运算符一起使用。下面给出了Pig中可用的加载和存储函数的列表。

| S.N. | 函数  | & |  描述 |
| :--- | :--- | :--- | :--- |
|  |  | 1 | [PigStorage\(\)](https://www.w3cschool.cn/apache_pig/apache_pig_pigstore.html)加载和存储结构化文件。 |
|  |  | 2 | [TextLoader\(\)](https://www.w3cschool.cn/apache_pig/apache_pig_textloader.html)将非结构化数据加载到Pig中。 |
|  |  | 3 | [BinStorage\(\)](https://www.w3cschool.cn/apache_pig/apache_pig_binstorage.html)使用机器可读格式将数据加载并存储到Pig中。 |
|  |  | 4 | [Handling Compression](https://www.w3cschool.cn/apache_pig/apache_pig_handling_compression.html)在Pig Latin中，我们可以加载和存储压缩数据。 |

下面给出了Bag和Tuple函数的列表。

| S.N. | 函数 ＆  | 描述 |
| :--- | :--- | :--- |
|  | 1 | [TOBAG\(\)](https://www.w3cschool.cn/apache_pig/apache_pig_tobag.html)将两个或多个表达式转换为包。 |
|  | 2 | [TOP\(\)](https://www.w3cschool.cn/apache_pig/apache_pig_top.html)获取关系的顶部**N**个元组。 |
|  | 3 | [TOTUPLE\(\)](https://www.w3cschool.cn/apache_pig/apache_pig_totuple.html)将一个或多个表达式转换为元组。 |
|  | 4 | [TOMAP\(\)](https://www.w3cschool.cn/apache_pig/apache_pig_tomap.html)将key-value对转换为Map。 |

在Apache Pig中有以下String函数。

| S.N. | 函数 ＆  | 描述 |
| :--- | :--- | :--- |
|  | 1 | [ENDSWITH\(string, testAgainst\)](https://www.w3cschool.cn/apache_pig/apache_pig_endswith.html)验证给定字符串是否以特定子字符串结尾。 |
|  | 2 | [STARTSWITH\(string, substring\)](https://www.w3cschool.cn/apache_pig/apache_pig_startswith.html)接受两个字符串参数，并验证第一个字符串是否以第二个字符串开头。 |
|  | 3 | [SUBSTRING\(string, startIndex, stopIndex\)](https://www.w3cschool.cn/apache_pig/apache_pig_substring.html)返回来自给定字符串的子字符串。 |
|  | 4 | [EqualsIgnoreCase\(string1, string2\)](https://www.w3cschool.cn/apache_pig/apache_pig_equalsignorecase.html)比较两个字符串，忽略大小写。 |
|  | 5 | [INDEXOF\(string, ‘character’, startIndex\)](https://www.w3cschool.cn/apache_pig/apache_pig_indexof.html)返回字符串中第一个出现的字符，从开始索引向前搜索。 |
|  | 6 | [LAST\_INDEX\_OF\(expression\)](https://www.w3cschool.cn/apache_pig/apache_pig_last_index_of.html)返回字符串中最后一次出现的字符的索引，从开始索引向后搜索。 |
|  | 7 | [LCFIRST\(expression\)](https://www.w3cschool.cn/apache_pig/apache_pig_lcfirst.html)将字符串中的第一个字符转换为小写。 |
|  | 8 | [UCFIRST\(expression\)](https://www.w3cschool.cn/apache_pig/apache_pig_ucfirst.html)返回一个字符串，其中第一个字符转换为大写。 |
|  | 9 | [UPPER\(expression\)](https://www.w3cschool.cn/apache_pig/apache_pig_upper.html)返回转换为大写的字符串。 |
|  | 10 | [LOWER\(expression\)](https://www.w3cschool.cn/apache_pig/apache_pig_lower.html)将字符串中的所有字符转换为小写。 |
|  | 11 | [REPLACE\(string, ‘oldChar’, ‘newChar’\);](https://www.w3cschool.cn/apache_pig/apache_pig_replace.html)使用新字符替换字符串中的现有字符。 |
|  | 12 | [STRSPLIT\(string, regex, limit\)](https://www.w3cschool.cn/apache_pig/apache_pig_strsplit.html)围绕给定正则表达式的匹配拆分字符串。 |
|  | 13 | [STRSPLITTOBAG\(string, regex, limit\)](https://www.w3cschool.cn/apache_pig/apache_pig_strsplittobag.html)与**STRSPLIT\(\) **函数类似，它通过给定的分隔符将字符串拆分，并将结果返回到包中。 |
|  | 14 | [TRIM\(expression\)](https://www.w3cschool.cn/apache_pig/apache_pig_trim.html)返回删除了前端和尾部空格的字符串的副本。 |
|  | 15 | [LTRIM\(expression\)](https://www.w3cschool.cn/apache_pig/apache_pig_ltrim.html)返回删除了前端空格的字符串的副本。 |
|  | 16 | [RTRIM\(expression\)](https://www.w3cschool.cn/apache_pig/apache_pig_rtrim.html)返回已删除尾部空格的字符串的副本。 |

  
Apache Pig提供以下日期和时间函数 -

| S.N. | 函数 ＆  | 描述 |
| :--- | :--- | :--- |
|  | 1 | [ToDate\(milliseconds\)](https://www.w3cschool.cn/apache_pig/apache_pig_todate.html)此函数根据给定的参数返回日期时间对象。此函数的另一个替代方法是ToDate（iosstring），ToDate（userstring,format），ToDate（userstring,format,timezone） |
|  | 2 | [CurrentTime\(\)](https://www.w3cschool.cn/apache_pig/apache_pig_currenttime.html)返回当前时间的日期时间对象。 |
|  | 3 | [GetDay\(datetime\)](https://www.w3cschool.cn/apache_pig/apache_pig_getday.html)从日期时间对象返回一个月中的某一天。 |
|  | 4 | [GetHour\(datetime\)](https://www.w3cschool.cn/apache_pig/apache_pig_gethour.html)从日期时间对象返回一天中的小时。 |
|  | 5 | [GetMilliSecond\(datetime\)](https://www.w3cschool.cn/apache_pig/apache_pig_getmillisecond.html)从日期时间对象返回秒中的毫秒。 |
|  | 6 | [GetMinute\(datetime\)](https://www.w3cschool.cn/apache_pig/apache_pig_getminute.html)从日期时间对象返回一小时中的分钟。 |
|  | 7 | [GetMonth\(datetime\)](https://www.w3cschool.cn/apache_pig/apache_pig_getmonth.html)从日期时间对象返回一年中的月份。 |
|  | 8 | [GetSecond\(datetime\)](https://www.w3cschool.cn/apache_pig/apache_pig_getsecond.html)从日期时间对象返回一分钟的秒。 |
|  | 9 | [GetWeek\(datetime\)](https://www.w3cschool.cn/apache_pig/apache_pig_getweek.html)从日期时间对象返回一年中的周。 |
|  | 10 | [GetWeekYear\(datetime\)](https://www.w3cschool.cn/apache_pig/apache_pig_getweekyear.html)从日期时间对象返回周年。 |
|  | 11 | [GetYear\(datetime\)](https://www.w3cschool.cn/apache_pig/apache_pig_getyear.html)从日期时间对象返回年份。 |
|  | 12 | [AddDuration\(datetime, duration\)](https://www.w3cschool.cn/apache_pig/apache_pig_addduration.html)返回日期时间对象的结果以及持续时间对象。 |
|  | 13 | [SubtractDuration\(datetime, duration\)](https://www.w3cschool.cn/apache_pig/apache_pig_subtractduration.html)从Date-Time对象中减去Duration对象并返回结果。 |
|  | 14 | [DaysBetween\(datetime1, datetime2\)](https://www.w3cschool.cn/apache_pig/apache_pig_daysbetween.html)返回两个日期时间对象之间的天数。 |
|  | 15 | [HoursBetween\(datetime1, datetime2\)](https://www.w3cschool.cn/apache_pig/apache_pig_hoursbetween.html)返回两个日期时间对象之间的小时数。 |
|  | 16 | [MilliSecondsBetween\(datetime1, datetime2\)](https://www.w3cschool.cn/apache_pig/apache_pig_millisecondsbetween.html)返回两个日期时间对象之间的毫秒数。 |
|  | 17 | [MinutesBetween\(datetime1, datetime2\)](https://www.w3cschool.cn/apache_pig/apache_pig_minutesbetween.html)返回两个日期时间对象之间的分钟数。 |
|  | 18 | [MonthsBetween\(datetime1, datetime2\)](https://www.w3cschool.cn/apache_pig/apache_pig_monthsbetween.html)返回两个日期时间对象之间的月数。 |
|  | 19 | [SecondsBetween\(datetime1, datetime2\)](https://www.w3cschool.cn/apache_pig/apache_pig_secondsbetween.html)返回两个日期时间对象之间的秒数。 |
|  | 20 | [WeeksBetween\(datetime1, datetime2\)](https://www.w3cschool.cn/apache_pig/apache_pig_weeksbetween.html)返回两个日期时间对象之间的周数。 |
|  | 21 | [YearsBetween\(datetime1, datetime2\)](https://www.w3cschool.cn/apache_pig/apache_pig_yearsbetween.html)返回两个日期时间对象之间的年数。 |

  
我们在Apache Pig中有以下Math（数学）函数:

| S.N. | 函数 ＆  | 描述 |
| :--- | :--- | :--- |
|  | 1 | [ABS\(expression\)](https://www.w3cschool.cn/apache_pig/apache_pig_abs.html)获取表达式的绝对值。 |
|  | 2 | [ACOS\(expression\)](https://www.w3cschool.cn/apache_pig/apache_pig_acos.html)获得表达式的反余弦值。 |
|  | 3 | [ASIN\(expression\)](https://www.w3cschool.cn/apache_pig/apache_pig_asin.html)获取表达式的反正弦值。 |
|  | 4 | [ATAN\(expression\)](https://www.w3cschool.cn/apache_pig/apache_pig_atan.html)此函数用于获取表达式的反正切值。 |
|  | 5 | [CBRT\(expression\)](https://www.w3cschool.cn/apache_pig/apache_pig_cbrt.html)此函数用于获取表达式的立方根。 |
|  | 6 | [CEIL\(expression\)](https://www.w3cschool.cn/apache_pig/apache_pig_ceil.html)此函数用于获取向上舍入到最接近的整数的表达式的值（近1取整）。 |
|  | 7 | [COS\(expression\)](https://www.w3cschool.cn/apache_pig/apache_pig_cos.html)此函数用于获取表达式的三角余弦值。 |
|  | 8 | [COSH\(expression\)](https://www.w3cschool.cn/apache_pig/apache_pig_cosh.html)此函数用于获取表达式的双曲余弦值。 |
|  | 9 | [EXP\(expression\)](https://www.w3cschool.cn/apache_pig/apache_pig_exp.html)此函数用于获得欧拉数e乘以x的幂，即指数。 |
|  | 10 | [FLOOR\(expression\)](https://www.w3cschool.cn/apache_pig/apache_pig_floor.html)要获得向下取整为最接近整数的表达式的值（四舍五入取整）。 |
|  | 11 | [LOG\(expression\)](https://www.w3cschool.cn/apache_pig/apache_pig_log.html)获得表达式的自然对数（基于e）。 |
|  | 12 | [LOG10\(expression\)](https://www.w3cschool.cn/apache_pig/apache_pig_log10.html)得到表达式的基于10的对数。 |
|  | 13 | [RANDOM\( \)](https://www.w3cschool.cn/apache_pig/apache_pig_random.html)获得大于或等于0.0且小于1.0的伪随机数（double类型）。 |
|  | 14 | [ROUND\(expression\)](https://www.w3cschool.cn/apache_pig/apache_pig_round.html)要将表达式的值四舍五入为整数（如果结果类型为float）或四舍五入为长整型（如果结果类型为double）。 |
|  | 15 | [SIN\(expression\)](https://www.w3cschool.cn/apache_pig/apache_pig_sin.html)获得表达式的正弦值。 |
|  | 16 | [SINH\(expression\)](https://www.w3cschool.cn/apache_pig/apache_pig_sinh.html)获得表达式的双曲正弦值。 |
|  | 17 | [SQRT\(expression\)](https://www.w3cschool.cn/apache_pig/apache_pig_sqrt.html)获得表达式的正平方根。 |
|  | 18 | [TAN\(expression\)](https://www.w3cschool.cn/apache_pig/apache_pig_tan.html)获得角度的三角正切。 |
|  | 19 | [TANH\(expression\)](https://www.w3cschool.cn/apache_pig/apache_pig_tanh.html)获得表达式的双曲正切。 |

  
  


