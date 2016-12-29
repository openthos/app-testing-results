
#VLC使用说明书

##VLC效果图
- ![](https://github.com/openthos/app-testing-results/blob/master/IMGview/VLC.png)

## VLC使用方法
- 点击VLC打开（出现视频窗口）  

##选择视频音频播放  

![image](../IMGview/openvideo_from_FM.png)  
直接在文件管理器中选择多媒体文件,右击->打开,就可以选择使用VLC播放  
当存在多个多媒体播放软件时,您可以自由选择播放器  

##添加到播放列表

![image](../IMGview/list.png)
1.VLC在启动时会自动扫描本地的多媒体文件  
2.在"设置"->"选择要收录与媒体库的目录"添加新的目录,下面就会扫描所选的目录  

##本地网络  

VLC会自动扫描局域网上的smb共享文件夹,你可以选择相应的多媒体文件播放;
** 还没有深入测试 **

## 流播放

  ![image](../IMGview/stream-ok.png)
可以添加远程的多媒体链接,VLC会利用http或rtsp协议来获取多媒体文件.  
**具体的链接协议还没有深入测试**  

##音频播放功能  

 音频播放中支持按照"艺术家","专辑","歌曲","流派","播放列表"进行排序分类功能  
 **其中各个列表的"追加"功能不正常.**

##视频格式
目前视频格式支持：
```
mpg，mp4,vob,avi,swf 3gp,mpeg4  
```
待确认格式： 
```
rmvb,wmv,mkv,flv  
```
