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
| chmem | | **错误**。chmem: Failed to read /sys/devices/system/memory: No such file or directory |
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
| ctrlaltdel | 执行重启 | **错误**。重启无效。 |
| cut | | |
| date | | |
| dd | | |
| delpart | | |
| df | | |
| dir | | |
| dircolors | | |
| dirname | | |
| dmesg | | |
| du | *3 | |
| echo | | |
| eject | | |
| env | | |
| expand | | |
| expr | | |
| factor | | |
| fallocate | | |
| false | | |
| fdformat | | |
| fdisk | *4 | |
| fincore | | |
| findfs | | |
| findmnt | | |
| flock | | |
| fmt | | |
| fold | | |
| fsck | | |
| fsck.minix | | |
| fsfreeze | | |
| fstrim | | |
| getlimits | | |
| getopt | | |
| ginstall | | |
| groups | | |
| head | | |
| hexdump | | |
| hwclock | | |
| id | | |
| ionice | | |
| ipcmk | | |
| ipcrm | | |
| ipcs | | |
| isosize | | |
| join | | |
| kill | | |
| ldattach | | |
| link | | |
| ln | | |
| logger | | |
| logname | | |
| look | | |
| losetup | | |
| ls | | |
| lsblk | | |
| lscpu | | |
| lsipc | | |
| lslocks | | |
| lsmem | | |
| lsns | | |
| make-prime-list | | |
| mcookie | | |
| md5sum | | |
| mesg | | |
| mkdir | | |
| mkfifo | | |
| mkfs | | |
| mkfs.bfs | | |
| mkfs.minix | | |
| mknod | | |
| mkswap | | |
| mktemp | | |
| mount | | |
| mountpoint | | |
| mv | | |
| namei | | |
| nice | | |
| nl | | |
| nohup | | |
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
| printenv | | |
| printf | | |
| prlimit | | |
| ptx | | |
| pwd | | |
| raw | | |
| readlink | | |
| readprofile | | |
| realpath | | |
| rename | | |
| renice | | |
| resizepart | | |
| rev | | |
| rfkill | | |
| rm | | |
| rmdir | | |
| rtcwake | | |
| runcon | | |
| script | | |
| scriptreplay | | |
| seq | | |
| setarch | | |
| setsid | | |
| sfdisk | | |
| sha1sum | | |
| sha224sum | | |
| sha256sum | | |
| sha384sum | | |
| sha512sum | | |
| shred | | |
| shuf | | |
| sleep | | |
| sort | | |
| split | | |
| stat | | |
| stdbuf | | |
| stty | | |
| sum | | |
| swaplabel | | |
| swapoff | | |
| swapon | | |
| switch_root | | |
| sync | | |
| tac | | |
| tail | | |
| taskset | | |
| tee | | |
| test | | |
| timeout | | |
| touch | | |
| tr | | |
| true | | |
| truncate | | |
| tsort | | |
| tty | | |
| umount | | |
| uname | | |
| unexpand | | |
| uniq | | |
| unlink | | |
| unshare | | |
| uptime | | |
| users | | |
| uuidd | | |
| uuidgen | | |
| uuidparse | | |
| vdir | | |
| wc | | |
| wdctl | | |
| whereis | | |
| who | | |
| whoami | | |
| wipefs | | |
| yes | | |
| zramctl | | |
