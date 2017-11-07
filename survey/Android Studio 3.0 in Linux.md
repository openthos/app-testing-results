# 下载安装   
Android Studio 3.0可以和之前安装的稳定版共存，不会影响自动化测试。
1. 下载页面：http://www.android-studio.org/ ，选择Linux版本下载
2. 解压：```unzip android-studio-ide-171.4408382-linux.zip```，解压后的文件放到与之前版本的android studio不同的文件夹
3. 如果之前已安装jdk8可以直接略过jdk安装，安装方法请看：https://github.com/openthos/testing-analysis/blob/master/Auto-test/uiautomator/%E7%BC%96%E8%AF%91%E7%8E%AF%E5%A2%83%E6%90%AD%E5%BB%BA.md
4. 如果因为防火墙无法下载安装sdk可以在/etc/hosts文件中加入下面两行：
```203.208.43.105  dl.google.com```
```203.208.43.105  dl-ssl.google.com```
5. ```chmod -R 777 android-studio```
```vim android-studio/bin/studio.sh```
在第一行添加下面字段以防止运行时提示找不到jdk路径
```JAVA_HOME="/usr/bin/jdk8"```
6. 运行sh文件并按照之前习惯进行安装
```./android-studio/bin/studio.sh```
