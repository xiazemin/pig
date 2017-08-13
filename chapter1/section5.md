# Grunt Shell

调用Grunt shell后，可以在shell中运行Pig脚本。除此之外，还有由Grunt shell提供的一些有用的shell和实用程序命令。本章讲解的是Grunt shell提供的shell和实用程序命令。

**注意**:在本章的某些部分中，使用了**Load**和**Store**等命令。请参阅相应章节以获取有关它们的详细信息。

## Shell 命令

Apache Pig的Grunt shell主要用于编写Pig Latin脚本。在此之前，我们可以使用**sh**和**fs**来调用任何shell命令。

### sh 命令

使用**sh**命令，我们可以从Grunt shell调用任何shell命令，但无法执行作为shell环境（**ex**- cd）一部分的命令。

**语法**

下面给出了**sh**命令的语法。

```
grunt
>
 sh shell command parameters

```

**示例**

我们可以使用**sh**选项从Grunt shell中调用Linux shell的**ls**命令，如下所示。在此示例中，它列出了**/pig/bin/**目录中的文件。

```
grunt
>
 sh ls

   
pig 
pig_1444799121955.log 
pig.cmd 
pig.py

```

### fs命令

使用**fs**命令，我们可以从Grunt shell调用任何FsShell命令。

**语法**

下面给出了**fs**命令的语法。

```
grunt
>
 sh File System command parameters

```

**示例**

我们可以使用fs命令从Grunt shell调用HDFS的ls命令。在以下示例中，它列出了HDFS根目录中的文件。

```
grunt
>
 fs –ls

  
Found 3 items
drwxrwxrwx   - Hadoop supergroup          0 2015-09-08 14:13 Hbase
drwxr-xr-x   - Hadoop supergroup          0 2015-09-09 14:52 seqgen_data
drwxr-xr-x   - Hadoop supergroup          0 2015-09-08 11:30 twitter_data

```

以同样的方式，我们可以使用**fs**命令从Grunt shell中调用所有其他文件系统的shell命令。

## 实用程序命令

Grunt shell提供了一组实用程序命令。这些包括诸如**clear，help，history，quit**和**set**等实用程序命令；以及Grunt shell中诸如**exec，kill**和**run**等命令来控制Pig。下面给出了Grunt shell提供的实用命令的描述。

### clear命令

**clear**命令用于清除Grunt shell的屏幕。

**语法**

你可以使用**clear**命令清除grunt shell的屏幕，如下所示。

```
grunt
>
 clear

```

### help命令

**help**命令提供了Pig命令或Pig属性的列表。

**使用**

你可以使用**help**命令获取Pig命令列表，如下所示。

```
grunt
>
 help


Commands: 
<
pig latin statement
>
; - See the PigLatin manual for details:
http://hadoop.apache.org/pig
  
File system commands:fs 
<
fs arguments
>
 - Equivalent to Hadoop dfs  command:
http://hadoop.apache.org/common/docs/current/hdfs_shell.html
	 
Diagnostic Commands:describe 
<
alias
>
[::
<
alias] - Show the schema for the alias.
Inner aliases can be described as A::B.
    explain [-script 
<
pigscript
>
] [-out 
<
path
>
] [-brief] [-dot|-xml] 
       [-param 
<
param_name
>
=
<
pCram_value
>
]
       [-param_file 
<
file_name
>
] [
<
alias
>
] - 
       Show the execution plan to compute the alias or for entire script.
       -script - Explain the entire script.
       -out - Store the output into directory rather than print to stdout.
       -brief - Don't expand nested plans (presenting a smaller graph for overview).
       -dot - Generate the output in .dot format. Default is text format.
       -xml - Generate the output in .xml format. Default is text format.
       -param 
<
param_name - See parameter substitution for details.
       -param_file 
<
file_name
>
 - See parameter substitution for details.
       alias - Alias to explain.
       dump 
<
alias
>
 - Compute the alias and writes the results to stdout.

Utility Commands: exec [-param 
<
param_name
>
=param_value] [-param_file 
<
file_name
>
] 
<
script
>
 -
       Execute the script with access to grunt environment including aliases.
       -param 
<
param_name - See parameter substitution for details.
       -param_file 
<
file_name
>
 - See parameter substitution for details.
       script - Script to be executed.
    run [-param 
<
param_name
>
=param_value] [-param_file 
<
file_name
>
] 
<
script
>
 -
       Execute the script with access to grunt environment.
		 -param 
<
param_name - See parameter substitution for details.         
       -param_file 
<
file_name
>
 - See parameter substitution for details.
       script - Script to be executed.
    sh  
<
shell command
>
 - Invoke a shell command.
    kill 
<
job_id
>
 - Kill the hadoop job specified by the hadoop job id.
    set 
<
key
>
<
value
>
 - Provide execution parameters to Pig. Keys and values are case sensitive.
       The following keys are supported:
       default_parallel - Script-level reduce parallelism. Basic input size heuristics used 
       by default.
       debug - Set debug on or off. Default is off.
       job.name - Single-quoted name for jobs. Default is PigLatin:
<
script name
>
     
       job.priority - Priority for jobs. Values: very_low, low, normal, high, very_high.
       Default is normal stream.skippath - String that contains the path.
       This is used by streaming any hadoop property.
    help - Display this message.
    history [-n] - Display the list statements in cache.
       -n Hide line numbers.
    quit - Quit the grunt shell. 

```

### history命令

此命令显示自Grunt shell被调用以来执行/使用的语句的列表。

**使用**

假设我们自打开Grunt shell之后执行了三个语句。

```
grunt
>
 customers = LOAD 'hdfs://localhost:9000/pig_data/customers.txt' USING PigStorage(',');
 
grunt
>
 orders = LOAD 'hdfs://localhost:9000/pig_data/orders.txt' USING PigStorage(',');
 
grunt
>
 student = LOAD 'hdfs://localhost:9000/pig_data/student.txt' USING PigStorage(',');
 

```

然后，使用**history**命令将产生以下输出。

```
grunt
>
 history


customers = LOAD 'hdfs://localhost:9000/pig_data/customers.txt' USING PigStorage(','); 
  
orders = LOAD 'hdfs://localhost:9000/pig_data/orders.txt' USING PigStorage(',');
   
student = LOAD 'hdfs://localhost:9000/pig_data/student.txt' USING PigStorage(',');
 

```

### set命令

**set**命令用于向Pig中使用的key显示/分配值。

**使用**

使用此命令，可以将值设置到以下key。

| Key | 说明和值 |
| :--- | :--- |
| **default\_parallel** | 通过将任何整数作为值传递给此key来设置映射作业的reducer数。 |
| **debug** | 关闭或打开Pig中的调试功能通过传递on/off到这个key。 |
| **job.name** | 通过将字符串值传递给此key来将作业名称设置为所需的作业。 |
| **job.priority** | 通过将以下值之一传递给此key来设置作业的优先级:very\_lowlownormalhighvery\_high |
| **stream.skippath** | 对于流式传输，可以通过将所需的路径以字符串形式传递到此key，来设置不传输数据的路径。 |

### quit命令

你可以使用此命令从Grunt shell退出。

**使用**

从Grunt shell中退出，如下所示。

```
grunt
>
 quit

```

现在让我们看看从Grunt shell控制Apache Pig的命令。

### exec命令

使用**exec**命令，我们可以从Grunt shell执行Pig脚本。

**语法**

下面给出了实用程序命令**exec**的语法。

```
grunt
>
 exec [–param param_name = param_value] [–param_file file_name] [script]

```

**示例**

我们假设在HDFS的**/pig\_data/**目录中有一个名为**student.txt**的文件，其中包含以下内容。

**Student.txt**

```
001,Rajiv,Hyderabad
002,siddarth,Kolkata
003,Rajesh,Delhi

```

并且，假设我们在HDFS的**/pig\_data/**目录中有一个名为**sample\_script.pig**的脚本文件，并具有以下内容。

**Sample\_script.pig**

```
student = LOAD 'hdfs://localhost:9000/pig_data/student.txt' USING PigStorage(',') 
   as (id:int,name:chararray,city:chararray);
  
Dump student;

```

现在，让我们使用**exec**命令从Grunt shell中执行上面的脚本，如下所示。

```
grunt
>
 exec /sample_script.pig

```

**输出**

**exec**命令执行**sample\_script.pig**中的脚本。按照脚本中的指示，它会将**student.txt**文件加载到Pig中，并显示Dump操作符的结果，显示以下内容。

```
(1,Rajiv,Hyderabad)
(2,siddarth,Kolkata)
(3,Rajesh,Delhi) 

```

### kill命令

你可以使用此命令从Grunt shell中终止一个作业。

**语法**

下面给出了**kill**命令的语法。

```
grunt
>
 kill JobId

```

**示例**

假设有一个具有id**Id\_0055**的正在运行的Pig作业，使用**kill**命令从Grunt shell中终止它，如下所示。

```
grunt
>
 kill Id_0055

```

### run命令

你可以使用**run**命令从Grunt shell运行Pig脚本

**语法**

下面给出了**run**命令的语法。

```
grunt
>
 run [–param param_name = param_value] [–param_file file_name] script

```

**示例**

假设在HDFS的**/pig\_data/**目录中有一个名为**student.txt**的文件，其中包含以下内容。

**Student.txt**

```
001,Rajiv,Hyderabad
002,siddarth,Kolkata
003,Rajesh,Delhi

```

并且，假设我们在本地文件系统中有一个名为**sample\_script.pig**的脚本文件，并具有以下内容。

**Sample\_script.pig**

```
student = LOAD 'hdfs://localhost:9000/pig_data/student.txt' USING
   PigStorage(',') as (id:int,name:chararray,city:chararray);

```

现在，让我们使用run命令从Grunt shell运行上面的脚本，如下所示。

```
grunt
>
 run /sample_script.pig

```

你可以使用**Dump操作符**查看脚本的输出，如下所示。

```
grunt
>
 Dump;


(1,Rajiv,Hyderabad)
(2,siddarth,Kolkata)
(3,Rajesh,Delhi)

```

**注意**:**exec**和**run**命令之间的区别是，如果使用**run**，则脚本中的语句在history命令中可用。



