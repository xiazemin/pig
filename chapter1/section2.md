# Apache Pig 安装

$ axel -n 60 [http://mirrors.hust.edu.cn/apache/pig/pig-0.17.0/pig-0.17.0.tar.gz](http://mirrors.hust.edu.cn/apache/pig/pig-0.17.0/pig-0.17.0.tar.gz)

$ vi .bashrc

export PIG\_HOME=/Users/didi/pig/pig

export PATH=$PIG\_HOME/bin:$PATH

export CLASSPATH=$CLASSPATH:$PIG\_HOME/lib/\*

export PIG\_CLASSPATH = $PIG\_HOME/conf

$ pig -h properties

The following properties are supported:

    Logging:

        verbose=true\|false; default is false. This property is the same as -v switch

        brief=true\|false; default is false. This property is the same as -b switch

        debug=OFF\|ERROR\|WARN\|INFO\|DEBUG; default is INFO. This property is the same as -d switch



