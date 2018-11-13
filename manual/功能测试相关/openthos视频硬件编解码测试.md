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


# 测试机器：T43U
# 测试软件：图库视频播放器和vlc
# 测试版本：0527版
# 视频一：big-buck-bunny-4k.mp4
- 1.以图库方式播放：
  - 软解：画面空白，cpu占70%～80%     
  - 硬解：有画面，但是卡顿严重，视频只占据播放器左上角很小一部分，cpu8%～15%    
- 2.以vlc播放：
  - 软解：有画面，存在卡顿现象，cpu占85%～95%
  - 硬解：有画面，卡顿严重，cpu占80%～95%

# 视频二：big-buck-bunny-480p.avi
- 1.以图库方式播放:
  - 软解:全屏播放,流畅,有杂音,CPU占8% ~ 15% 
  - 硬解:全屏播放,流畅,有杂音,CPU占8% ~ 16% 
- 2.以VLC播放崩溃
- 存在bug 1470 ：视频播放器播放时有杂音，而使用vlc播放时没有杂音。

# 视频三:big-buck-bunny-1080p
- 1.以图库方式播放:
  - 软解:视频只占据播放器左上角很小一部分,播放流畅,CPU占40% ~ 73% 
  - 硬解:全屏播放,流畅,CPU占10% ~ 24% 
- 2.以VLC播放:
  - 软解:流畅,CPU占24% ~ 57% 
  - 硬解:流畅,CPU占18% ~ 31%

# 测试版本：0606版
# 视频一：big-buck-bunny-4k.mp4
- 1.以图库方式播放：
  - 软解：画面空白，声音正常，cpu占66%～79%
  - 硬解：有画面，卡顿严重，视频只占据播放器左上角很小一部分，cpu8%～15%
- 2.以vlc播放：
  - 软解：有画面，存在卡顿现象，cpu占85%～95%
  - 硬解：有画面，卡顿严重，cpu占80%～95%

# 视频二：big-buck-bunny-480p-surround-fix.mp4(之前的预装视频存在问题，替换为该视频）
- 1.以图库方式播放:
  - 软解:全屏播放,流畅,CPU占22% ~ 35%
  - 硬解:全屏播放,流畅,CPU占11% ~ 13%
- 2.以VLC播放崩溃
  - 软解:全屏播放,流畅,CPU占16% ~ 25%
  - 硬解:全屏播放,流畅,CPU占16% ~ 25%

# 视频三:big-buck-bunny-1080p
- 1.以图库方式播放:
  - 软解:视频只占据播放器左上角一部分,流畅,CPU占50% ~ 62%
  - 硬解:视频只占据播放器左上角一部分,流畅,CPU占19% ~ 21%
- 2.以VLC播放:
  - 软解:流畅,CPU占24% ~ 57%
  - 硬解:流畅,CPU占18% ~ 31%
