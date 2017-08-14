# 存储数据

## 语法

下面给出了Store语句的语法。

```
STORE Relation_name INTO ' required_directory_path ' [USING function];
```

grunt&gt;    STORE student INTO ' hdfs://localhost:8020/pig\_Output/ ' USING PigStorage \(','\);

HadoopVersion	PigVersion	UserId	StartedAt	FinishedAt	Features

2.6.4	0.17.0	didi	2017-08-14 15:17:36	2017-08-14 15:17:42	UNKNOWN



Success!



Job Stats \(time in seconds\):

JobId	Maps	Reduces	MaxMapTime	MinMapTime	AvgMapTime	MedianMapTime	MaxReduceTime	MinReduceTime	AvgReduceTime	MedianReducetime	Alias	Feature	Outputs

job\_local594670236\_0002	1	0	n/a	n/a	n/a	n/a	0	0	0	0student	MAP\_ONLY	hdfs://localhost:8020/pig\_Output,



Input\(s\):

Successfully read 6 records \(11512434 bytes\) from: "hdfs://localhost:8020/input/test.txt"



Output\(s\):

Successfully stored 6 records \(11512152 bytes\) in: "hdfs://localhost:8020/pig\_Output"



Counters:

Total records written : 6

Total bytes written : 11512152

Spillable Memory Manager spill count : 0

Total bags proactively spilled: 0

Total records proactively spilled: 0



Job DAG:

job\_local594670236\_0002

