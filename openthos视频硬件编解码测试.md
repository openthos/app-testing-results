# 1.同步openthos测试代码并编译之

- mkdir WORKING_DIRECTORY

- cd WORKING_DIRECTORY

- repo init -u git://192.168.0.185/lollipop-x86/manifest.git -b multiwindow-hwaccel

- repo sync

# 2.测试

- 在Intel CPU的机器中运行该openthos，并设置硬件编解码开关；运行测试视频，并注意查看视频播放是否异常中断和CPU占用情况。

## openthos命令行操作如下：

- 2.1软件编解码测试

  - setprop media.sf.hwaccel 0 （关闭硬解码，使用软解码）

  - am start -a android.intent.action.VIEW -d file:///mnt/sdcard/Jolin-Tsai_HD.mp4 -t video/*

- 2.2硬件编解码测试

  - setprop media.sf.hwaccel 1 （打开硬件编解码）

  - am start -a android.intent.action.VIEW -d file:///mnt/sdcard/Jolin-Tsai_HD.mp4 -t video/*

- 查看cpu占用情况

  - top -m 5 -d 2

