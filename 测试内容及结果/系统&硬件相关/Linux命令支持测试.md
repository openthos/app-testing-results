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
|            |                            |



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
| cal | | |
| cat | | |
| chcon | | |
| chcpu | | |
| chgrp | | |
| chmem | | |
| chmod | | |
| choom | | |
| chown | | |
| chroot | | |
| chrt | | |
| cksum | | |
| col | | |
| colcrt | | |
| colrm | | |
| column | | |
| comm | | |
| cp | | |
| csplit | | |
| ctrlaltdel | | |
| cut | | |
| date | | |
| dd | | |
| delpart | | |
| df | | |
| dir | | |
| dircolors | | |
| dirname | | |
| dmesg | | |
| du | | |
| echo | | |
| eject | | |
| env | | |
| expand | | |
| expr | | |
| factor | | |
| fallocate | | |
| false | | |
| fdformat | | |
| fdisk | | |
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
