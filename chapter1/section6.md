# Grunt Shell 实践

Linux 终端下输入如下命令进入 Grunt Shell 的 MapReduce 模式：

$pig –x mapreduce

可以使用 sh 选项从Grunt shell中调用Linux shell的 ls 命令，如下所示。在此示例中，它列出了 /pig/bin/ 目录中的文件。

grunt&gt; sh ls

CHANGES.txt

LICENSE.txt

NOTICE.txt

README.txt

RELEASE\_NOTES.txt

bin

grunt&gt; fs -ls

Found 1 items

drwxr-xr-x   - didi supergroup          0 2017-08-08 10:21 output



