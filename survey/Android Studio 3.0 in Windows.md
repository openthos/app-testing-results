## Android Studio 3.0 下载地址：http://www.android-studio.org/

- 相关链接如下：
  - http://www.cnblogs.com/mliangchen/p/5125114.html

  - http://www.jianshu.com/p/f07f83d1fbdf

  - https://zhidao.baidu.com/question/1306216642640128619.html?qbl=relate_question_0&word=Android%208.0%C8%E7%BA%CE%B2%E2%CA%D4%D0%D4%C4%DC

  - https://www.zhihu.com/question/19716849/answer/42525356

## android针对应用性能的情况提供了一些列的工具：
- 布局复杂度：
hierarchyviewer：检测布局复杂度，各视图的布局耗时情况：

Android开发者模式—GPU过渡绘制：

- 耗电量：Android开发者模式中的电量统计；
- 内存：
应用运行时内存使用情况查看：Android Studio—Memory/CPU/GPU；

内存泄露检测工具：DDMS—MAT；
- 网络：Android Studio—NetWork；
- 程序执行效率：
静态代码检查工具：Android studio—Analyze—Inspect Code.../Code cleanup... ，用于检测代码中潜在的问题、存在效率问题的代码段并提供改善方案；
DDMS—TraceView，用于查找程序运行时具体耗时在哪；
StrictMode：用于查找程序运行时具体耗时在哪，需要集成到代码中；
Andorid开发者模式—GPU呈现模式分析。
- 程序稳定性：monkey，通过monkey对程序在提交测试前做自测，可以检测出明显的导致程序不稳定的问题，执行monkey只需要一行命令，提交测试前跑一次可以避免应用刚提交就被打回的问题。
说明：
上面提到的这些工具可以进Android开发者官网性能工具介绍查看每个工具的介绍和使用说明；

Android开发者选项中有很多测试应用性能的工具，对应用性能的检测非常有帮助，具体可以查看：All about your phone's developer options和15个必知的Android开发者选项对Android开发者选项中每一项的介绍；

针对Android应用性能的优化，Google官方提供了一系列的性能优化视频教程，对应用性能优化具有非常好的指导作用，具体可以查看：优酷Google Developers或者Android Performance Patterns。

## 第三方性能优化工具介绍
除了android官方提供的一系列性能检测工具，还有很多优秀的第三方性能检测工具使用起来更方便
比如对内存泄露的检测，使用leakcanry比MAT更人性化，能够快速查到具体是哪存在内存泄露。
leakcanary：square/leakcanary · GitHub，通过集成到程序中的方式，在程序运行时检测应用中存在的内存泄露，并在页面中显示，在应用中集成leancanry后，程序运行时会存在卡顿的情况，这个是正常的，因为leancanry就是通过gc操作来检测内存泄露的，gc会知道应用卡顿，说明文档：LeakCanary 中文使用说明、LeakCanary: 让内存泄露无所遁形。
GT：GT Home，GT是腾讯开发的一款APP的随身调测平台，利用GT，可以对CPU、内存、流量、点亮、帧率/流畅度进行测试，还可以查看开发日志、crash日志、抓取网络数据包、APP内部参数调试、真机代码耗时统计等等，需要说明的是，应用需要集成GT的sdk后，GT这个apk才能在应用运行时对各个性能进行检测。

## 新的探查器
Android Studio中3.0提供您的应用程序的活动的实时、统一的视图。而Android Profiler窗口取代了Android的监控 窗口。要打开Android的探查器，请按照下列步骤操作：
View　> Tool windows > Android Profiler （你也可以点击工具栏中的）
选择您想要从Android探查器工具栏配置的设备和应用程序,点击network，CPU或MEMORY时间表打开每个探查的更详细视图。

## 即时应用(Instant App)的支持
Android Studio 3.0允许您在项目中使用两种新的模块类型：即时应用模块和功能模块来创建即时应用
Android Studio 3.0还包括一个新的重构模块化操作和App Links Assistant，以帮助您实施即时应用。有关Instant Apps的详细信息，请参阅Android Instant Apps
APK Debugger(APK调试者)
Android Studio 3.0中的新版APK调试器可让您配置和调试APK，而无需从Android Studio项目中构建它们,只要它们是可调试的。 更多信息参阅Profile and Debug Pre-built APKs。

## APK分析器的改进
Android Studio 3.0对APK分析工具进行了以下改进：
显示除包之外的字段，类和方法之外的字段
顶部显示和隐藏字段和方法的新过滤选项
在树视图中，以斜体显示的节点是未在DEX文件中定义的引用
对于启用Proguard构建的APK，您可以加载向DEX查看器添加功能的Proguard映射文件，其中包括：
 - 粗体表示节点的节点不应该删除，当收缩编码
 - 启用一个按钮，使得在收缩过程中被删除的节点可见
 - 启用一个按钮，显示树视图中由Proguard混淆的节点的原始名称

## 探查器详解(Android Profiler)
Android Studio 3.0中的新的Android Profiler窗口替代了Android Monitor工具，这些新的分析工具可为应用程序的CPU，内存和网络活动提供实时数据。您可以执行sample-based的方法跟踪代码执行、捕获堆转储、查看内存分配和检查网络传输文件的详细信息。

## apk调试器
Android Studio 3.0允许您配置和调试APK，而无需从Android Studio项目中构建它们。但是，您需要确保使用了APK的调试版本。
要开始调试APK，从Android Studio欢迎屏幕上单击Profile或debug APK。或者，如果你已经打开了一个项目，点击 File > Profile 或者从工具栏点击 debug APK。在下一个对话框窗口中，选择想要导入Android Studio的APK，然后单击OK。
提示: 当您将APK导入Android Studio时，IDE会在您的主目录中创建一个新项目，并制作目标APK的本地副本。
在Project窗格中的Android视图允许您检查您的APK的以下内容：
APK file: 双击APK打开APK分析器。
manifests: 从APK中提取出来应用清单。
java: 包含Android Studio反汇编的Java代码。你的APK的DEX文件中的smali文件对应一个Java类。
cpp: 如果你的app包含Native代码，这个目录包含了你的native库(.so文件)。
External Libraries: 包含Android SDK。
您可以立即使用Android profiler来开始测试应用程序的性能，但是profiler目前只适用于app的Java进程。使用断点来调试应用程序的Java和native代码,您需要首先Attach Java sources并attach native debug symbols。
