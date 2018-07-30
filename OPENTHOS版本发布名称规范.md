## tuna镜像站
- 链接：https://mirrors.tuna.tsinghua.edu.cn/openthos/
### IMG镜像
- 镜像放置在185服务器上提供给tuna同步：rsync@192.168.0.185:/home/rsync/rsync/oto_img/Release/
- 目录名称
   - user_stable:每个月所有版本中较稳定版本（设置中"关于设备"版本信息显示为正式版）
   - user_unstable:每个周所有版本中较稳定版本（设置中"关于设备"版本信息显示为开发版）
   - eng_forlab:每个周提供给开发人员安装升级的较稳定版本（有开发者模式，可使用Android Studio）
- 内容：
   - openthos-1.1.0.180730.img
   - openthos-1.1.0.180730.img.md5
### OTA升级
- 位置：rsync@192.168.0.185:/home/rsync/rsync/oto_img/OTA/
- 目录名称同镜像
- 内容：
   - 升级包：openthos_V1.1_stable.zip.gpg
   - 版本信息：oto_ota.ver
   - 升级内容描述：ReleaseNotes_1_8_8.md

## 百度网盘
- 
