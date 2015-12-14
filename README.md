# app-testing-results
record the testing results of different applications.

# format
## using app name as DIR name
```
chrome DIR
```
## in each DIR
### testing-record.txt
the example of content in test-record.txt
```
测试时间:
2015-12-14

测试APP:
firefox(x86) version 48

测试硬件环境:
HASEE 战神笔记本
MEM: 16GB
CPU: i7-4710MQ

软件测试环境：
1 android-x86-5.1 with linux kernel 4.0.9
2 android-x86-5.1 with linux kernel 4.4-rc4

测试结果:
在１软件环境中，firefox能够运行
在２软件环境中，firefox不能运行

测试分析:
通过对比1,2测试环境，发现firefox在2测试环境中有如下log info:
-------
12-14 06:23:36.246  1697  1697 E lowmemorykiller: Error opening /proc/3261/oom_score_adj; errno=2
-------
说明碰到了内存不足的问题，关于为何内存不足的问题，还需进一步分析
```
###date-appname-log-kernelver
examples:
```
20151214-firefox-log-4.4.4
20151214-firefox-log-4.0.9
```
