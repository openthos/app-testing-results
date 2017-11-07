# 下载安装   
Android Studio 3.0可以和之前安装的稳定版共存，不会影响自动化测试。
1. 下载页面：http://www.android-studio.org/ ，选择Linux版本下载
2. 解压：```unzip android-studio-ide-171.4408382-linux.zip```，解压后的文件放到与之前版本的android studio不同的文件夹
3. 如果之前已安装jdk8可以直接略过jdk安装，安装方法请看：   https://github.com/openthos/testing-analysis/blob/master/Auto-test/uiautomator/%E7%BC%96%E8%AF%91%E7%8E%AF%E5%A2%83%E6%90%AD%E5%BB%BA.md
4. 如果因为防火墙无法下载安装sdk可以在/etc/hosts文件中加入下面两行：   
```203.208.43.105  dl.google.com```   
```203.208.43.105  dl-ssl.google.com```
5. ```chmod -R 777 android-studio```   
```vim android-studio/bin/studio.sh```
在第一行添加下面字段以防止运行时提示找不到jdk路径   
```JAVA_HOME="/usr/bin/jdk8"```
6. 运行sh文件并按照之前习惯进行安装   
```./android-studio/bin/studio.sh```
# 新增工具
AndroidStudio3.0 下载使用新功能介绍:http://blog.csdn.net/niubitianping/article/details/72600923
与我们相关的工具：
## 新的Android模拟器功能

Android模拟器还包括许多新功能，包括以下内容：

    新的API Level 24系统映像和Android O Beta系统映像，包括Google Play商店，以促进您的应用程序的端到端测试，并帮助您保持Google Play服务与您的AVDs保持同步。

    支持Windows和Linux机器上的OpenGL ES 3.0系统图像API级别24及更高版本，并在较老的模拟器系统映像上对OpenGL ES 2.0图形性能进行显着改进。
        提示：目前正尽最大努力使OpenGL ES 3.0能从英特尔、英伟达和AMD的所有gpu自动启用，如果运行OpenGL ES 3.x应用程序时遇到问题，系统可能尚未自动启用。您可以通过修改~/.android/advancedFeatures.ini进行手动启用OpenGL ES 3.0。修改为：GLESDynamicVersion = true

    一种新的更简单的方法来从Android模拟器生成您的应用的错误报告。
    个新的链接，可以在Android问题跟踪器上为Android团队快速提交与模拟器相关的错误(Emulator Tool Bar > Extended Controls > Help > Emulator Help > File a Bug)
    一个新的UI来配置Android模拟器使用的代理设置。Extended Controls > Settings > Proxy.
    在模拟器上支持Android Wear设备的旋转输入。

更多模拟器的升级，请查阅Android Emulator Release Notes: https://developer.android.google.cn/studio/releases/emulator.html.
## 探查器(Android Profiler)

Android Studio 3.0中的新的Android Profiler窗口替代了Android Monitor工具，这些新的分析工具可为应用程序的CPU，内存和网络活动提供实时数据。您可以执行sample-based的方法跟踪代码执行、捕获堆转储、查看内存分配和检查网络传输文件的详细信息。

要打开Android Profiler窗口，请按照下列步骤操作：

    点击View > Tool Windows > Android Profiler(你也可以点击工具栏的image).
    在Android Profiler窗口的顶部，如图所示，选择设备①和您想要配置的应用程序②。
    如果您已通过USB连接设备但未看到它，请确保已启用USB调试。
        如果您使用Android模拟器或已经Root的设备，Android Profiler将列出所有正在运行的进程，即使它们可能是不可调试的。当您启动一个可调试的应用程序时，该进程是默认选择的。

Android Profiler现在显示了一个共享的时间线视图(下图)，其中包括一个时间线，用于CPU、内存和网络使用的实时图。窗口还包括时间线缩放控件③，跳转到实时更新的按钮④以及显示活动状态，用户输入事件和屏幕旋转事件的事件时间轴⑤。

image

此共享时间轴视图仅显示时间线图。要访问详细的分析工具，请单击与您要检查的性能数据相对应的图表。例如，要访问工具以检查堆并跟踪内存分配，请单击MEMORY图。
# 测试结果
测试了上面两个工具，在android studio3.0下载Oreo版本模拟器后可以进入android 8.0系统并测试应用。探查器也可以显示cpu、内存和网络使用数据，但是目前只能针对某一个应用进行探查，还没有找到可以探查操作系统的方法。
