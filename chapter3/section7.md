# 用户定义函数（UDF）

除了内置函数之外，Apache Pig还为**U**ser**D**efined**F**unction（UDF：用户定义函数）提供广泛的支持。使用这些UDF，可以定义我们自己的函数并使用它们。UDF支持六种编程语言，即Java，Jython，Python，JavaScript，Ruby和Groovy。

对于编写UDF，在Java中提供全面的支持，并在所有其他语言中提供有限的支持。使用Java，你可以编写涉及处理的所有部分的UDF，如数据加载/存储，列转换和聚合。由于Apache Pig是用Java编写的，因此与其他语言相比，使用Java语言编写的UDF工作效率更高。

在Apache Pig中，我们还有一个用于UDF名为**Piggybank**的Java存储库。使用Piggybank，我们可以访问由其他用户编写的Java UDF，并贡献我们自己的UDF。

## Java中的UDF的类型

在使用Java编写UDF时，我们可以创建和使用以下三种类型的函数

* **Filter函数**- Filter（过滤）函数用作过滤器语句中的条件。这些函数接受Pig值作为输入并返回布尔值。

* **Eval函数**- Eval函数在FOREACH-GENERATE语句中使用。这些函数接受Pig值作为输入并返回Pig结果。

* **Algebraic函数**- Algebraic（代数）函数对FOREACHGENERATE语句中的内包起作用。这些函数用于对内包执行完全MapReduce操作。

## 使用Java编写UDF

要使用Java编写UDF，我们必须集成jar文件**Pig-0.15.0.jar**。在本章节中，将讨论如何使用Eclipse编写示例UDF。在继续学习前，请确保你已在系统中安装了Eclipse和Maven。

按照下面给出的步骤写一个UDF函数：

* 打开Eclipse并创建一个新项目（例如**myproject**）。

* 将新创建的项目转换为Maven项目。

* 在pom.xml中复制以下内容。此文件包含Apache Pig和Hadoop-core jar文件的Maven依赖关系。

```
<
project xmlns = "http://maven.apache.org/POM/4.0.0"
   xmlns:xsi = "http://www.w3.org/2001/XMLSchema-instance"
   xsi:schemaLocation = "http://maven.apache.org/POM/4.0.0http://maven.apache .org/xsd/maven-4.0.0.xsd"
>
<
modelVersion
>
4.0.0
<
/modelVersion
>
<
groupId
>
Pig_Udf
<
/groupId
>
<
artifactId
>
Pig_Udf
<
/artifactId
>
<
version
>
0.0.1-SNAPSHOT
<
/version
>
<
build
>
<
sourceDirectory
>
src
<
/sourceDirectory
>
<
plugins
>
<
plugin
>
<
artifactId
>
maven-compiler-plugin
<
/artifactId
>
<
version
>
3.3
<
/version
>
<
configuration
>
<
source
>
1.7
<
/source
>
<
target
>
1.7
<
/target
>
<
/configuration
>
<
/plugin
>
<
/plugins
>
<
/build
>
<
dependencies
>
<
dependency
>
<
groupId
>
org.apache.pig
<
/groupId
>
<
artifactId
>
pig
<
/artifactId
>
<
version
>
0.15.0
<
/version
>
<
/dependency
>
<
dependency
>
<
groupId
>
org.apache.hadoop
<
/groupId
>
<
artifactId
>
hadoop-core
<
/artifactId
>
<
version
>
0.20.2
<
/version
>
<
/dependency
>
<
/dependencies
>
<
/project
>
```

* 保存文件并刷新它。在**Maven依赖关系**部分中，可以找到下载的jar文件。

* 创建名为**Sample\_Eval**的新的类文件，并在其中复制以下内容。

```
import java.io.IOException; 
import org.apache.pig.EvalFunc; 
import org.apache.pig.data.Tuple; 
 
import java.io.IOException; 
import org.apache.pig.EvalFunc; 
import org.apache.pig.data.Tuple;

public class Sample_Eval extends EvalFunc
<
String
>
{ 

   public String exec(Tuple input) throws IOException {   
      if (input == null || input.size() == 0)      
      return null;      
      String str = (String)input.get(0);      
      return str.toUpperCase();  
   } 
}

```

在编写UDF时，必须继承EvalFunc类并向**exec\(\) **函数提供实现。在此函数中，写入UDF所需的代码。在上面的例子中，我们返回了将给定列的内容转换为大写的代码。

* 编译完类并确认没有错误后，右键单击Sample\_Eval.java文件。它将呈现一个菜单。选择**“export”**，如以下屏幕截图所示。

![](https://www.w3cschool.cn/attachments/tuploads/apache_pig/select_export.jpg "选择export")

* 点击**“export”**，将看到以下窗口。点击**“JAR file”**。

![](https://www.w3cschool.cn/attachments/tuploads/apache_pig/click_export.jpg "点击Export")

* 点击**“Next&gt;”**按钮继续操作。将获得另一个窗口，你需要在本地文件系统中输入路径，在其中存储jar文件。

![](https://www.w3cschool.cn/attachments/tuploads/apache_pig/jar_export.jpg "jar export")

* 最后，单击**“Finish”**按钮。在指定的文件夹中，创建一个Jar文件**sample\_udf.jar**。此jar文件包含用Java编写的UDF。

## 使用UDF

在编写UDF和生成Jar文件后，请按照下面给出的步骤：

### 步骤1：注册Jar文件

在写入UDF（在Java中）后，我们必须使用Register运算符注册包含UDF的Jar文件。通过注册Jar文件，用户可以将UDF的位置绑定到Apache Pig。

**语法**

下面给出了Register运算符的语法。

```
REGISTER path; 

```

**例**

让我们注册本章前面创建的sample\_udf.jar。以本地模式启动Apache Pig并注册jar文件sample\_udf.jar，如下所示。

```
$cd PIG_HOME/bin 
$./pig –x local 

REGISTER '/$PIG_HOME/sample_udf.jar'

```

**注意**：假设路径中的Jar文件：/$PIG\_HOME/sample\_udf.jar

### 步骤2：定义别名

注册UDF后，可以使用**Define**运算符为其定义一个别名。

**语法**

下面给出了Define运算符的语法。

    DEFINE alias {function | [`command` [input] [output] [ship] [cache] [stderr] ] }; 


**例**

定义sample\_eval的别名，如下所示。

```
DEFINE sample_eval sample_eval();

```

### 步骤3：使用UDF

定义别名后，可以使用与内置函数相同的UDF。假设在HDFS**/Pig\_Data/**目录中有一个名为emp\_data的文件，其中包含以下内容。

```
001,Robin,22,newyork
002,BOB,23,Kolkata
003,Maya,23,Tokyo
004,Sara,25,London 
005,David,23,Bhuwaneshwar 
006,Maggy,22,Chennai
007,Robert,22,newyork
008,Syam,23,Kolkata
009,Mary,25,Tokyo
010,Saran,25,London 
011,Stacy,25,Bhuwaneshwar 
012,Kelly,22,Chennai

```

并假设我们已将此文件加载到Pig中，如下所示。

```
grunt
>
 emp_data = LOAD 'hdfs://localhost:9000/pig_data/emp1.txt' USING PigStorage(',')
   as (id:int, name:chararray, age:int, city:chararray);

```

现在使用UDF**sample\_eval**将员工的姓名转换为大写。

```
grunt
>
 Upper_case = FOREACH emp_data GENERATE sample_eval(name);

```

请验证关系**Upper\_case**的内容，如下所示。

```
grunt
>
 Dump Upper_case;

  
(ROBIN)
(BOB)
(MAYA)
(SARA)
(DAVID)
(MAGGY)
(ROBERT)
(SYAM)
(MARY)
(SARAN)
(STACY)
(KELLY)

```

  


