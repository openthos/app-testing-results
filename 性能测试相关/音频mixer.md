#### 20191219

##### Music.apk

- 描述：此apk修改原生music player，当其它音频已启动的情况下用此apk播放音频，会使原音频音量降低但继续播放。
- 测试平台：S1笔记本，oto8 user版
- 测试结果：
  1. 其它视频启动的情况下，启动此apk，会使其它视频音量消失但继续播放。
  2. 焦点切换回视频，依然会播放Music.apk的声音。即当Music.apk播放的时候始终不能播放视频的声音。

##### 测试镜像

- 描述：此镜像通过修改request focus的标志为AUDIOFOCUS_GAIN_TRANSIENT_MAY_DUCK的方法，使不同的音频app可以同时播放。
- 测试平台：S1笔记本，测试镜像(oto8 userdebug)
- 测试结果：
  1. 开启一个视频，再开启一个音频，可以同时听到两者的声音。
  2. 但不能分别控制两者的音量，音量会同时增大或同时减小。