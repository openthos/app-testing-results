使用的测试笔记本为S1，处理器为i7-8550U(八代)

#### 4.18内核

##### /proc/cpuinfo

开SMT和关SMT不同之处如下表所示

| 开SMT | 关SMT | 全关 | 不同之处          |
| ----- | ----- | ---- | ----------------- |
| 8     | 8     | 1    | CPU个数           |
| 3400  | 2300  | 1688 | per CPU:频率      |
| 8     | 8     | 1    | per CPU:siblings  |
| 4     | 4     | 1    | per CPU:cpu cores |



##### /sys/devices/system/cpu

- 开SMT和关SMT的顶层目录结构是相同的，都显示出有8个CPU的目录

- SMP和SMT都关的话，仅显示有1个CPU的目录，它与开SMP的区别是：少了7个与CPU相关的目录

#### 4.19内核

##### /proc/cpuinfo

开SMT和关SMT不同之处如下表所示，可以看到开SMP时的频率**明显偏低**

| 开SMT    | 关SMT      | 全关 | 不同之处          |
| -------- | ---------- | ---- | ----------------- |
| 8        | 4          | 1    | CPU个数           |
| 794～954 | 1730～2089 | 1762 | per CPU:频率      |
| 8        | 4          | 1    | per CPU:siblings  |
| 4        | 4          | 1    | per CPU:cpu cores |

##### /sys/devices/system/cpu

使用`du`命令列出cpu目录下的所有文件，以比较在开SMT和关SMT两种情况下的目录差异

| 开SMT | 关SMT                                                        | 不同之处      |
| ----- | ------------------------------------------------------------ | ------------- |
|       | 无cache,cpuidle目录，无microcode,thermal_throthle,topology文件 | cpu4~cpu7目录 |
|       | 无policy4~policy7文件                                        | cpufreq目录   |

