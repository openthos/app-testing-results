#环境
- cpu:skylake
- os: android-x86-5.1+kernel-4.4.0-rc8 user版本

#app测试结果列表

名称 | 运行情况|　备注
----- | ---- | ----
QQ  | PASS|屏幕旋转90度，不方便操作。
微信| FAIL| 安装后无法打开且无任何提示。
2048| PASS| 屏幕旋转90度，不方便操作。
ES文件管理器| PASS|使用正常。
QQ 音乐| PASS| 屏幕旋转90度，不方便操作。
WPSoffice| PASS| 使用正常。
chrome| PASS| 使用正常。
firefox| PASS| 使用正常。
QQ浏览器| PASS| 广告宣传时屏幕旋转90度，不方便操作。点跳过后可回到橫屏。
seafile| PASS| 休眠唤醒后无法安装，提示没有存储空间,重启后安装正常。
地铁跑酷| FAIL| 安装后无法运行，提示"很抱歉，×××已停止运行."
开心消消乐| FAIL| 安装后无法运行,提示"很抱歉，×××已停止运行."
搜狗输入法| PASS| 使用正常
植物大战僵尸|FAIL |安装后无法运行，提示"很抱歉，×××已停止运行."
水果忍者| FAIL|安装后无法运行，提示"很抱歉，×××已停止运行."
百度云| FAIL|安装后无法运行，提示"很抱歉，×××已停止运行."
豌豆荚| PASS| 屏幕旋转90度，不方便操作
Microsoft Excel| NE| 未下载到x86版Microsoft Excel版本，手机版安装不成功
Microsoft Word| NE| 未下载到x86版Microsoft Word版本，手机版安装不成功
Microsoft Powerpoint| NE| 未下载到x86版Microsoft Powerpoint版本，手机版安装不成功

#无存储空间问题定位
设置-显示-休眠（默认无操作10分钟后进入休眠状态），这时需要按电源键唤醒。唤醒后安装APP时会有两种错误
1. 提示“没有存储空间”
2. 提示“解析软件包出现问题”
此时无论安装哪个APK均报以上两种错误中的一种。即唤醒系统后安装APK存在问题。重启后再安装apk 包才会正常。
设置中选项最长为30分钟，所以这个问题需要解决，用户在使用过程中肯定会存在休眠问题，如中午去吃饭不关机。

--------------------------------------------------------------------------------------
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
