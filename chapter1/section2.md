# Apache Pig 安装

$ axel -n 60 [http://mirrors.hust.edu.cn/apache/pig/pig-0.17.0/pig-0.17.0.tar.gz](http://mirrors.hust.edu.cn/apache/pig/pig-0.17.0/pig-0.17.0.tar.gz)

$ vi .bashrc

export PIG\_HOME=/Users/didi/pig/pig

export PATH=$PIG\_HOME/bin:$PATH

export CLASSPATH=$CLASSPATH:$PIG\_HOME/lib/\*

export PIG\_CLASSPATH = $PIG\_HOME/conf

