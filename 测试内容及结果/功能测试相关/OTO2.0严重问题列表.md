# OTO2.0严重问题列表（严重等级为１）
## 设置
- [bug 2162] 目前台式机和笔记本的自动休眠时间是以“用电池时“为准的，应该是“接通电源时“
- [bug 2593]有时系统重启后会连接不上以太网，需要手动关闭打开隔离模式才能恢复。（复现方式：将连接wifi设备的配置还原到网线连接的设备上时，还原后的设备不识别有线网，自动连接备份文件保存的wifi，如果关闭wifi打开有线网，会提示请检查网线。解决方法：关闭打开隔离模式。）

## 浏览器
- [bug 2557]浏览器打开部分网页后卡死，页面所有按钮无法点击，新建标签页后也无法进行输入网址等操作，重启无法恢复，只能清除数据再打开，复现方法如下:
   - 登录阿里云邮箱，打开王之旭6月28日18：51提交的patch邮件，界面会卡死；
   - 打开下面的网址后静止10秒钟：https://www.zhihu.com/question/278856112/answer/406989615
- [浏览器其它问题](https://github.com/openthos/app-testing-results/blob/master/%E6%B5%8B%E8%AF%95%E5%86%85%E5%AE%B9%E5%8F%8A%E7%BB%93%E6%9E%9C/%E5%8A%9F%E8%83%BD%E6%B5%8B%E8%AF%95%E7%9B%B8%E5%85%B3/%E6%B5%8F%E8%A7%88%E5%99%A8%E5%B8%B8%E8%A7%81%E9%97%AE%E9%A2%98.md)

## system ui
- 通知中心没有通知的情况下，多次点击通知中心按钮会发现每次点击时任务栏移到屏幕上方
![](../picture/notification_wrongposition.jpg)

## google相关
- 自从在系统中加入google服务，第一次打开日历的时候会卡在登陆google帐号页面（老问题，最近有用户遇到在问，建议修改）
![](https://github.com/openthos/app-testing-results/blob/master/testresult/picture/calendar_1.png)
- 首次配置安装应用阶段弹出是否允许google定期检查安全问题的提示，如果没来得及点接受的话，提示会消失，之后首次配置会一直卡在安装xposed步骤(8.1也存在，只有在eng和userdebug中有，user版正常)  
![](../picture/firstconfig_googlesecurity.png)

## 文件管理器
- [bug 2178]文件管理器不能搜索文件，界面空白

## 终端
- [bug 2732]openthos终端上dd镜像到ｕ盘时经常复制不全，同一个镜像文件在ubuntu上dd时则无此问题

## 首次配置
- [bug 2714] 首次配置安装应用时，如果一直放着不管的话，5分钟后会进入待机状态，此时部分电脑无法唤醒设备

