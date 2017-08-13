# 实践

$ ./bin/pig -x local

SLF4J: Class path contains multiple SLF4J bindings.

2017-08-13 16:51:49,292 \[main\] WARN  org.apache.pig.PigServer - ATS is disabled since yarn.timeline-service.enabled set to false

grunt&gt;

grunt&gt; ls

file:/Users/didi/pig/pig/bin    &lt;dir&gt;

file:/Users/didi/pig/pig/build.xml&lt;r 1&gt;    88817

file:/Users/didi/pig/pig/CHANGES.txt&lt;r 1&gt;    213092

file:/Users/didi/pig/pig/conf    &lt;dir&gt;

$ ./bin/pig -x mapreduce

17/08/13 16:53:50 INFO pig.ExecTypeProvider: Trying ExecType : LOCAL

17/08/13 16:53:50 INFO pig.ExecTypeProvider: Trying ExecType : MAPREDUCE

17/08/13 16:53:50 INFO pig.ExecTypeProvider: Picked MAPREDUCE as the ExecType

2017-08-13 16:53:50,249 \[main\] INFO  org.apache.pig.Main - Apache Pig version 0.17.0 \(r1797386\) compiled Jun 02 2017, 15:41:58

grunt&gt; ls

hdfs://localhost:8020/user/didi/output    &lt;dir&gt;

grunt&gt; ls /

hdfs://localhost:8020/hbase    &lt;dir&gt;

hdfs://localhost:8020/input    &lt;dir&gt;

hdfs://localhost:8020/output1    &lt;dir&gt;

hdfs://localhost:8020/output2    &lt;dir&gt;

hdfs://localhost:8020/output3    &lt;dir&gt;

grunt&gt; quit

2017-08-13 16:54:44,517 \[main\] INFO  org.apache.pig.Main - Pig script completed in 54 seconds and 494 milliseconds \(54494 ms\)

grunt&gt; A=load "/Users/didi/pig/pig/test" uing PigStorage\(':'\) as \(Sno:chararray,Sname:chararray,Ssex:chararray,Sage:int,Sdept:chararray\);B=foreach A generate Sname,Sage; dump B;

2017-08-13 16:59:22,324 \[main\] ERROR org.apache.pig.tools.grunt.Grunt - ERROR 1000: Error during parsing. Encountered " &lt;PATH&gt; "A=load "" at line 1, column 1.

等号前后均需要空格

&lt;line 1, column 9&gt;  Unexpected character '"'

2017-08-13 17:02:00,631 \[main\] ERROR org.apache.pig.tools.grunt.Grunt - ERROR 1200: &lt;line 1, column 9&gt;  Unexpected character '"'

双引号换为单引号





