# Apache Pig 安装

$ axel -n 60 [http://mirrors.hust.edu.cn/apache/pig/pig-0.17.0/pig-0.17.0.tar.gz](http://mirrors.hust.edu.cn/apache/pig/pig-0.17.0/pig-0.17.0.tar.gz)

$ vi .bashrc

export PIG\_HOME=/Users/didi/pig/pig

export PATH=$PIG\_HOME/bin:$PATH

export CLASSPATH=$CLASSPATH:$PIG\_HOME/lib/\*

export PIG\_CLASSPATH = $PIG\_HOME/conf

$ pig -h properties

The following properties are supported:

```
Logging:

    verbose=true\|false; default is false. This property is the same as -v switch

    brief=true\|false; default is false. This property is the same as -b switch

    debug=OFF\|ERROR\|WARN\|INFO\|DEBUG; default is INFO. This property is the same as -d switch
```

$  pig –version

17/08/13 16:42:42 INFO pig.ExecTypeProvider: Trying ExecType : LOCAL

17/08/13 16:42:42 INFO pig.ExecTypeProvider: Trying ExecType : MAPREDUCE

17/08/13 16:42:42 INFO pig.ExecTypeProvider: Picked MAPREDUCE as the ExecType

2017-08-13 16:42:42,114 \[main\] INFO  org.apache.pig.Main - Apache Pig version 0.17.0 \(r1797386\) compiled Jun 02 2017, 15:41:58

2017-08-13 16:42:42,486 \[main\] WARN  org.apache.hadoop.util.NativeCodeLoader - Unable to load native-hadoop library for your platform... using builtin-java classes where applicable

2017-08-13 16:42:42,741 \[main\] ERROR org.apache.pig.Main - ERROR 2997: Encountered IOException. File –version does not exist

Details at logfile: /Users/didi/pig\_1502613762112.log

2017-08-13 16:42:42,777 \[main\] INFO  org.apache.pig.Main - Pig script completed in 894 milliseconds \(894 ms\)

