#### jps

> **jps主要用来输出JVM中进程状态信息**   

jps -l 输出完全的包名，应用主类名，jar的完全路径名 

jps -v 显示JVM参数

#### jstat

> jstat主要用来输出JVM统计监测信息

jstat -gcutil pid  3s 60 

分析进程的gc情况,每隔3秒打印一次，打印60次停止

| 年轻代中第一个survivor（幸存区）的容量 (字节)     | S0C  |
| -------------------------------- | ---- |
| 年轻代中第二个survivor（幸存区）的容量 (字节)     | S1C  |
| 年轻代中第一个survivor（幸存区）目前已使用空间 (字节) | S0U  |
| 年轻代中第二个survivor（幸存区）目前已使用空间 (字节) | S1U  |
| 年轻代中Eden（伊甸园）的容量 (字节)            | EC   |
| 年轻代中Eden（伊甸园）目前已使用空间 (字节)        | EU   |
| Old代的容量 (字节)                     | OC   |
| Old代目前已使用空间 (字节)                 | OU   |
| Perm(持久代)的容量 (字节)                | PC   |
| Perm(持久代)目前已使用空间 (字节)            | PU   |
| 从应用程序启动到采样时年轻代中gc次数              | YGC  |
| 从应用程序启动到采样时年轻代中gc所用时间(s)         | YGCT |
| 从应用程序启动到采样时old代(全gc)gc次数         | FGC  |
| 从应用程序启动到采样时old代(全gc)gc所用时间(s)    | FGCT |
| 从应用程序启动到采样时gc用的总时间(s)            | GCT  |

#### JVM参数
-Xms:指定JVM初始化内存
-Xmx:指定JVM堆的最大内存，在JVM启动以后，会分配-Xmx参数指定大小的内存给JVM，但是不一定全部使用，JVM会根据-Xms参数来调节真正用于JVM的内存
-Xmn：参数设置了新生代的大小；老年代等于-Xmx减去-Xmn
-XX:PermSize :设置永久代初始大小
-XX:MaxPermSize :设置永久代最大大小
-XX:+UseParallelGC:       使用并行垃圾收集
-XX:+UseConcMarkSweepGC: 使用并发标志扫描收集 (Introduced in 1.4.1)
-XX:+UseSerialGC : 使用串行垃圾收集 (Introduced in 5.0.)