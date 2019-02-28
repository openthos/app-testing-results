# 系统测试流程
1、制作ISO到U盘
$ dd if=android.iso of=/dev/sdd

2、安装或U盘启动（物理机）

3、安装好系统后设置-应用兼容性-打开可兼容使用arm库的应用 (必须，否则第三方应用好多不可用)

4、安装第三方应用 ，可通过U盘安装，也可通过脚本。

    方法1）U盘：直接单击即可安装
      
    方法2）脚本安装。
      
       A）git clone git://192.168.0.185/openthos-apps 至本地工作机-内含APK包及脚本文件
       
       B）阅读openthos-apps 下的readme文件，修改好PATH后执行脚本 即可安装测试所需第三方包

5、测试系统（包含如下几个模块）

      测试项                  测试内容
    
     1)系统安装               系统安装程序、启动和引导
    
     2)初始化检查              桌面框架下初始陈列的items清单、初始值，无须测试程序的调用
     
     3)SystemUI              包括开始菜单、快速启动栏、任务栏、通知栏
    
     4)文件管理              文件管理器、回收站、网上邻居、文件操作、左右键及快捷键等
    
     5)桌面环境              桌面框架的配置和功能（背景、快捷键、右键等）
    
     6)产品信息检查          系统中产品的信息（产品名称，产品logo，公司信息等）
    
     7)系统关联              系统中文件和程序间的关联对应（如：双击mp4文件，可打开视频文件）
    
     8)APP                   系统默认安装的应用（打开，使用，关闭，拖拽及缩放）
    
     9)设置                  开始菜单-设置-测试系统设置各项功能是否正常
    
     10)输入法               支持中文输入及快捷键切换
    
     11)软件兼容性           安装第三方应用，如利用APK包安装或豌豆夹安装第三方应用
    
     12)硬件兼容性           对台式机、笔记本、网卡、声卡、显卡、无线等硬件的兼容性测试

 # 日常测试安排

 ## 功能测试
 1. 每天编译新版本进行回归测试
 2. 每周选一版稳定版进行全面测试（一般选在周三，周四开始，否则周五测试不完）
 3. 装机前每周要在下周一要交付的版本上做一轮交互手册验证
 4. 每周五进行周进度检查核对，并整理到github
 5. 每周选一稳定版本上传至网盘，供爱好者下载使用
 6. 日报，周报及月报编写（月报要有本月总结评价及下月计划）


 ## 自动化测试
回归测试时，抽出时间做自动化用例深度编写


 # 小技巧
1. 查看当前分辨率
- wm size
- 调整1366投影：setprop debug.drm.mode.force 1366x768@60


2. 自研应用包及activity

    com.openthos.filemanager/com.openthos.filemanager.MainActivity
    adb shell monkey -p com.openthos.filemanager

    appstore:
    (name=com.openthos.appstore/com.openthos.appstore.MainActivity)
    adb shell monkey -p com.openthos.appstore -v -v -v 1000 --throttle 3000

    ota:
    (name=com.openthos.ota/com.openthos.ota.MainActivity）
    adb shell monkey -p com.openthos.ota -v -v -v 1000 --throttle 3000

    fennec:
    (name=org.mozilla.fennec_root/org.mozilla.fennec_root.App)
    adb shell monkey -p org.mozilla.fennec_root -v -v -v 1000 --throttle 3000

# 快捷链接
### 云服务
- [云服务](https://github.com/openthos/app-testing-results/tree/master/%E6%B5%8B%E8%AF%95%E5%86%85%E5%AE%B9%E5%8F%8A%E7%BB%93%E6%9E%9C/%E5%8A%9F%E8%83%BD%E6%B5%8B%E8%AF%95%E7%9B%B8%E5%85%B3/%E4%BA%91%E6%9C%8D%E5%8A%A1)
- [云服务问题列表](https://github.com/openthos/app-testing-results/blob/master/%E6%B5%8B%E8%AF%95%E5%86%85%E5%AE%B9%E5%8F%8A%E7%BB%93%E6%9E%9C/%E5%8A%9F%E8%83%BD%E6%B5%8B%E8%AF%95%E7%9B%B8%E5%85%B3/%E4%BA%91%E6%9C%8D%E5%8A%A1/%E4%BA%91%E6%9C%8D%E5%8A%A1%E4%BC%98%E5%85%88%E8%A7%A3%E5%86%B3%E9%97%AE%E9%A2%98%E5%88%97%E8%A1%A8.md)

# 目录结构

## list

应用、物品、硬件等的列表

## requirement

对需求的记录

## survey

调研的记录

## 工作资料

与工作相关的文档

## 测试内容及结果

测试的内容与结果

## 自动化测试

与自动化测试相关

## other

其它暂未归类的部分

