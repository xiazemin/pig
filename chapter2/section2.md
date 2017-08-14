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

