#20160421版本测试情况 
#测试设备
    1、超越Z8000（同方小PC）

    2、神舟笔记本（飞天UI47）

    3、联想笔记本（Yoga 3 11）

    4、同方笔记本，

#测试版本
1. 20160421-1 eng-------------------可用
2. 20160421-1 user------------------无法安装
3. 20160421-1 userdebug-------------安装后，所有第三方包无法打开
4. 20160421-2 eng-------------------可用

#前提条件：
 - 1. 安装好系统后设置-应用兼容性-打开可兼容使用arm库的应用 
 
#存在的问题：
1、qq
2、




-------------------------------------------------------------------------------------------------------------------------------
#环境
- cpu:skylake
- os: android-x86-5.1+kernel-4.4.0-final user版本
- 前提条件：
 - 1. 安装好系统后设置-应用兼容性-打开可兼容使用arm库的应用 
 - 2. 显示-设备旋转时-保持当前方向（横屏时设置）
 - 3. 双击预安装的rotation locker-landscape。使竖屏切换成横屏

#app测试结果列表

名称 | 运行情况|　备注
----- | ---- | ----
QQ  | PASS |Rotation locker工具使其显示正常
搜狗输入法| PASS| 使用正常
2048| PASS| Rotation locker工具使其显示正常
ES文件管理器| PASS|使用正常。
QQ 音乐| PASS|Rotation locker工具使其显示正常
WPSoffice| PASS| 使用正常。
chrome| PASS| 使用正常。
firefox| PASS| 使用正常。
豌豆荚| PASS| Rotation locker工具使其显示正常
QQ浏览器| PASS| Rotation locker工具使其显示正常
seafile| PASS| 使用正常
微信| PASS| 打开应用兼容性后可用，否则不可用
地铁跑酷| PASS| 打开应用兼容性后可用，否则不可用
开心消消乐| PASS| 打开应用兼容性后可用，否则不可用
植物大战僵尸|PASS|打开应用兼容性后可用，否则不可用
水果忍者| FAIL|双击已安装好的应用，无法打开使用.注：（通过在apk中将x86的lib进行删除，app可以正常启动）
百度云| FAIL|双击已安装好的应用，一闪而过无法打开使用 注：（通过在apk中将x86的lib进行删除，app可以正常启动）
Microsoft Excel| NE| 未下载到x86版Microsoft Excel版本，手机版安装不成功
Microsoft Word| NE| 未下载到x86版Microsoft Word版本，手机版安装不成功
Microsoft Powerpoint| NE| 未下载到x86版Microsoft Powerpoint版本，手机版安装不成功

##其他问题
1、QQ music 无法下载声音，只能播放本地音乐。后期需考虑APP识别有线网线，而非只支持WIFI和gms

2、 在以下四种情况下rotation功能失效

      重启;休眠唤醒后;新安装APP;一段时间不操作再次打开竖屏程序时又回到竖屏

3、设置-语言-中文（简体）后有的APP仍为英文显示，如note，打开后菜单项均为英文

4、删除预安装的APP后，APP图标仍在，打开后不停提示“*APP已停止运行”。无法进行其他操作，重启后恢复正常


------------------------------------------------------------------------------------------------------------


#环境
- cpu:skylake
- os: android-x86-5.1+kernel-4.4.0-rc8 user版本
- 前提条件：安装好系统后执行#enable_nativebridge及设置-应用兼容性-打开

#app测试结果列表

名称 | 运行情况|　备注
----- | ---- | ----
QQ  | PASS|屏幕旋转90度，不方便操作。
搜狗输入法| PASS| 使用正常
2048| PASS| 屏幕旋转90度，不方便操作。
ES文件管理器| PASS|使用正常。
QQ 音乐| PASS| 屏幕旋转90度，不方便操作。
WPSoffice| PASS| 使用正常。
chrome| PASS| 使用正常。
firefox| PASS| 使用正常。
豌豆荚| PASS| 屏幕旋转90度，不方便操作
QQ浏览器| PASS| 广告宣传时屏幕旋转90度，不方便操作。点跳过后可回到橫屏。
seafile| PASS| 休眠唤醒后无法安装，提示没有存储空间,重启后安装正常。
微信| PASS| 打开应用兼容性后可用，否则不可用
地铁跑酷| PASS| 打开应用兼容性后可用，否则不可用
开心消消乐| PASS| 打开应用兼容性后可用，否则不可用
植物大战僵尸|PASS|打开应用兼容性后可用，否则不可用
水果忍者| FAIL|安装后无法运行，提示"很抱歉，×××已停止运行." 注：（通过在apk中将x86的lib进行删除，app可以正常启动）
百度云| FAIL|安装后无法运行，提示"很抱歉，×××已停止运行."  注：（通过在apk中将x86的lib进行删除，app可以正常启动）
Microsoft Excel| NE| 未下载到x86版Microsoft Excel版本，手机版安装不成功
Microsoft Word| NE| 未下载到x86版Microsoft Word版本，手机版安装不成功
Microsoft Powerpoint| NE| 未下载到x86版Microsoft Powerpoint版本，手机版安装不成功

#无存储空间问题定位
设置-显示-休眠（默认无操作10分钟后进入休眠状态），这时需要按电源键唤醒。唤醒后安装APP时会有两种错误
-提示“没有存储空间”
-提示“解析软件包出现问题”
此时无论安装哪个APK均报以上两种错误中的一种。即唤醒系统后安装APK存在问题。重启后再安装apk 包才会正常。
设置中选项最长为30分钟，所以这个问题需要解决，用户在使用过程中肯定会存在休眠问题，如中午去吃饭不关机。

------------------------------------------------------------------------------------------------------------
#环境
- cpu:skylake
- os: android-x86-5.1+kernel-4.4.0-rc8 eng版本

#app测试结果列表

名称 | 运行情况|　备注
----- | ---- | ----
QQ  | PASS|屏幕旋转90度，不方便操作
微信| PASS| 屏幕旋转90度，不方便操作
2048| PASS| 屏幕旋转90度，不方便操作
ES文件管理器| PASS|使用正常
QQ 音乐| PASS| 屏幕旋转90度，不方便操作
WPSoffice| PASS| 使用正常
chrome| PASS| 使用正常
firefox| PASS| 使用正常
QQ浏览器| PASS| 广告宣传时屏幕旋转90度，不方便操作。点跳过后可回到橫屏。
seafile| PASS| 使用正常
地铁跑酷| FAIL| https://github.com/openthos/app-testing-results/issues/24 
开心消消乐| FAIL| https://github.com/openthos/app-testing-results/issues/23
搜狗输入法| PASS| 使用正常
植物大战僵尸| FAIL| https://github.com/openthos/app-testing-results/issues/14
水果忍者| FAIL| https://github.com/openthos/app-testing-results/issues/22
百度云| FAIL|https://github.com/openthos/app-testing-results/issues/10
豌豆荚| PASS| 屏幕旋转90度，不方便操作
Microsoft Excel| NE| 未下载到x86版Microsoft Excel版本，手机版安装不成功
Microsoft Word| NE| 未下载到x86版Microsoft Word版本，手机版安装不成功
Microsoft Powerpoint| NE| 未下载到x86版Microsoft Powerpoint版本，手机版安装不成功
