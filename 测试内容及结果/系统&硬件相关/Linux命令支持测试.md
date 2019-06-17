#### 软硬件环境描述

S1笔记本，android-desktop-oreo-generic_pc-190611.iso

#### 对常用参数的测试

执行--help和--version参数，如下命令有问题

| 命令  | 存在的问题                                                   |
| ----- | ------------------------------------------------------------ |
| chmem | chmem: Failed to read /sys/devices/system/memory: No such file or directory |
| kill  | 使用--help选项，提示unknown option                           |
| pwd   | 使用--help选项，提示unknown option                           |

#### 未测试功能的命令

| 命令       | 功能描述                   |
| ---------- | -------------------------- |
| addpart    | 告诉内核一个指定分区的存在 |
| blkdiscard | 丢弃设备上扇区的内容       |
| chcon      | 改变文件的安全上下文       |
| chcpu      | 修改CPU的状态              |
| delpart    | 告诉内核忘记一个分区       |
| eject      | 弹出设备                   |
| fdformat   | 格式化软盘                 |
| flock      | 等待，直到获得锁才执行命令 |
| fsck.minix | 检查Minix文件系统的一致性  |



#### 命令常用功能测试

| 移植的命令 | 测试内容                | 与Ubuntu下运行结果对比 |
| ---------- | ----------------------------- | ---------------------- |
| [          | 直接运行                        | 通过                   |
| b2sum      | 计算检验和 | 通过                   |
| base32 | 编码和解码 | 通过 |
| base64 | 编码和解码 | 通过 |
| basename | 删除前导目录和后缀 | 通过 |
| basenc | 解码base32和base64文件 | 通过。注：Ubuntu下无此命令 |
| blkid | 列出块设备的信息 | 通过 |
| blkzone | 报告给定设备的zone信息 | **错误**。提示：unable to determine zone size。注：Ubuntu下无此命令 |
| blockdev | 打印所有设备的报告 | **错误**。不能打印出设备的信息。 |
| cal | 打印日历 | 通过 |
| cat | 显示文件内容 | 通过 |
| chgrp | 修改文件属组 | 通过 |
| chmem | 设置一块内存在线或离线 | **错误**。chmem: Failed to read /sys/devices/system/memory: No such file or directory |
| chmod | 为一个无执行权的脚本增加执行权限 | 通过 |
| choom | 列出指定进程的OOM score | 通过。注：Ubuntu下无此命令 |
| chown | 修改文件属主 | 通过 |
| chroot | 将根目录切换到一个Linux分区 | 通过 |
| chrt | 获取init进程的实时调试属性 | 通过 |
| cksum | 打印检验和并统计字节数 | 通过 |
| col | 在标准输入中去掉backspaces | 通过 |
| colcrt | 过滤标准输入进行crt预览 | 通过 |
| colrm | 从标准输入中过滤掉指定的列 | 通过 |
| column | 将输入格式化为多个列 | 通过 |
| comm | 对两个排好序的文件进行比较 | 通过 |
| cp | 复制文件和文件夹 | 通过 |
| csplit | 使用正规表达式分割文件 | 通过 |
| ctrlaltdel | 执行soft和hard重启 | **错误**。重启无效。 |
| cut | 选取指定的字符和域 | 通过 |
| date | 打印日期 | 通过 |
| dd | 创建指定大小的文件 | 通过 |
| df | 报告硬盘占用情况 | 通过 |
| dir | 显示文件详情 | 通过 |
| dircolors | 输出默认设置 | 通过 |
| dirname | 给出pwd所在目录 | 通过 |
| dmesg | 打印出ring buffer中的内容 | 通过 |
| du | 统计文件的空间占用情况 | 通过 |
| echo | 字符串打印到标准输出 | 通过 |
| env | 在指定的环境中运行程序，列出所有环境变量 | 通过 |
| expand | 将tab转化为空格 | 通过 |
| expr | 计算表达式的值 | 通过 |
| factor | 分解素因子 | 通过 |
| fallocate | 为文件预分配10G空间 | 通过 |
| false | 返回表示错误的退出码 | 通过 |
| fdisk | 列出所有设备的分区表 | **错误**。不能正确识别分区表的位置，但能识别指定设备。 |
| fincore | 列出文件在内存中的占用情况 | 通过。注：Ubuntu中无此命令。 |
| findfs | 通过标签和UUID查找文件系统 | 通过 |
| findmnt | 列出所有已挂载的文件系统 | 通过 |
| fmt | 输出行宽为2 | 通过 |
| fold | 输出行宽为16 | 通过 |
| fsck | 检查指定文件系统 | **错误**。fsck: error 2 (m) while executing fsck.ext4 for /dev/block/nvme0n1p2 |
| fsfreeze | 挂起文件系统 | 通过 |
| fstrim | 丢弃文件系统上不用的块 | 通过 |
| getlimits | 输出与平台相关的限制条件 | 通过 |
| getopt | 分析一段参数化的字符串 | 通过 |
| ginstall | 将文件复制到目标位置 | 通过 |
| groups | 列出当前用户所在组的成员 | 通过 |
| head | 打印出前2行的内容 | 通过 |
| hexdump | hex+ASCII显示文件 | 通过 |
| hwclock | 显示硬件时钟 | 通过 |
| id | 列出当前用户的组信息 | 通过 |
| ionice | | |
| ipcmk |  | |
| ipcrm | | |
| ipcs | | |
| isosize | | |
| join | | |
| kill | 结束一个进程 | 通过 |
| ldattach | | |
| link | 创建到一个文件的链接 | 通过 |
| ln | 创建一个符号链接 | 通过 |
| logger | | |
| logname | | |
| look | | |
| losetup | | |
| ls | 列出文件的信息 | 通过 |
| lsblk | 列出块设备的信息 | 通过 |
| lscpu | 列出cpu信息 | 通过 |
| lsipc | | |
| lslocks | | |
| lsmem | 列出内存信息 | **错误**。This system does not support memory blocks |
| lsns | | |
| make-prime-list | | |
| mcookie | | |
| md5sum | 打印md5校验和 | 通过 |
| mesg | 显示或不显示其他用户的消息 | 通过 |
| mkdir | 创建目录 | 通过 |
| mkfifo | | |
| mkfs | 创建文件系统 | 通过 |
| mkfs.bfs | 创建一个SCO bfs文件系统 | 通过 |
| mkfs.minix | 创建一个minix文件系统 | 通过 |
| mknod | | |
| mkswap | 在设备或文件上创建交换区域 | 通过 |
| mktemp | | |
| mount | 挂载一个文件系统 | 通过 |
| mountpoint | 检查一个目录或文件是否是一个挂载点 | 通过 |
| mv | 重命名或移动文件 | 通过 |
| namei | 列出路径中的所有成份 | 通过 |
| nice | | |
| nl | 文件内容附加行号输出到标准输出 | 通过 |
| nohup | 运行一个不受hangups影响的命令 | **错误**。FORTIFY: umask: called with invalid mask -601 |
| nologin | | |
| nproc | | |
| nsenter | | |
| numfmt | | |
| od | | |
| partx | | |
| paste | | |
| pathchk | | |
| pinky | | |
| pivot_root | | |
| pr | | |
| printenv | 打印环境变量 | 通过 |
| printf | 打印格式化的数据 | 通过 |
| prlimit | | |
| ptx | | |
| pwd | 打印当前工作目录 | 通过 |
| raw | | |
| readlink | | |
| readprofile | | |
| realpath | | |
| rename | 重命名文件 | 通过 |
| renice | | |
| resizepart | | |
| rev | | |
| rfkill | | |
| rm | 删除文件或目录 | 通过 |
| rmdir | 删除空目录 | 通过 |
| rtcwake | | |
| runcon | | |
| script | | |
| scriptreplay | | |
| seq | 打印出一列数字 | 通过 |
| setarch | | |
| setsid | | |
| sfdisk | 显示或管理磁盘分区 | **错误**。不能正确识别分区表的位置，但能识别指定设备。 |
| sha1sum | 打印sha1校验和 | 通过 |
| sha224sum | 打印sha224校验和 | 通过 |
| sha256sum | 打印sha256校验和 | 通过 |
| sha384sum | 打印sha384校验和 | 通过 |
| sha512sum | 打印sha512校验和 | 通过 |
| shred | | |
| shuf | | |
| sleep | 暂停一段时间 | 通过 |
| sort | 对文件中的内容排序 | **错误**。cannot read: abc.txt: Invalid argument |
| split | 分割文件 | 通过 |
| stat | 显示文件或文件系统的状态 | 通过 |
| stdbuf | | |
| stty | | |
| sum | 打印校验和与块数量 | 通过 |
| swaplabel | 显示或改变交换区域的标签或UUID | 通过 |
| swapoff | 关闭交换 | **无法判断**。因为swapon不能生效。 |
| swapon | 开启交换 | **错误**。failed to parse /etc/fstab: No such file or directory |
| switch_root | | |
| sync | 内存中的缓存数据写入持久存储 | 通过 |
| tac | | |
| tail | 输出文件的最后部分 | 通过 |
| taskset | | |
| tee | 将标准输入输出到文件和标准输出 | 通过 |
| test | 检查文件类型和比较两个值 | 通过 |
| timeout | | |
| touch | 将文件的访问时间和修改时间设为当前时间 | 通过 |
| tr | | |
| true | 返回成功值 | 通过 |
| truncate | | |
| tsort | | |
| tty | 打印出连接到标准输入的终端的名称 | 通过 |
| umount | 解除对文件系统的挂载 | 通过 |
| uname | 打印出某个系统的信息 | 通过 |
| unexpand | 将空格轮换为tabs | 通过 |
| uniq | | |
| unlink | 调用unlink函数来删除指定文件 | 通过 |
| unshare | | |
| uptime | | |
| users | 显示当前登陆系统的用户列表 | **错误**。无输出 |
| uuidd | 生成UUID的守护进程 | **错误**。cannot open /usr/var/run/uuidd/uuidd.pid: No such file or directory |
| uuidgen | 创建一个UUID值 | 通过 |
| uuidparse | 解析uuid | 通过 |
| vdir | | |
| wc | 文件内容统计 | 通过 |
| wdctl | | |
| whereis | 定位二进制，源和手册的位置 | 通过 |
| who | 打印出已登陆用户的信息 | **错误**。无输出 |
| whoami | 打印出当前用户的用户名 | 通过 |
| wipefs | | |
| yes | 重复打印一串字符 | 通过 |
| zramctl | | |
