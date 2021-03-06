---
title: JVM堆内存配置导致的一次异常
tags:
  - JVM
  - tomcat
date: 2016-08-02 15:39:30
categories: 性能
---

# 问题由来
今天在压测一个接口的情况下，突然发现运行一段时间后，整体性能出现了激剧下降，响应时间出现飙升

如下图中TPS在运行11分钟后出现了一个下降，后续又出现了一个急速的下降，然后再开始恢复的过程
![tps](http://www.jeffxue.cn/img/20160729_tps.png)
对应的响应时间也出现了响应的变化
![trs](http://www.jeffxue.cn/img/20160729_trs.png)

# 查找原因
- 检查应用日志，没有异常
- 检查资源情况，没有异常
- 检查jvm的监视，发现异常
当时jvisualvm刚好是开启着监控，因此观察到了这次异常，对应是11点25分的看到堆内存从1G突增到了2G，同时CPU也飙升了上去，初步断定JVM在分配内存的时候，会导致应用的性能激剧下降。
![jvm](http://www.jeffxue.cn/img/20160729_jvm.png)


# 改进方案
将初始化的堆大小设置为最大的堆大小，在启动时即可将内存分配好，减少这种异常的情况
```
-Xms2048m -Xmx2048m
```

