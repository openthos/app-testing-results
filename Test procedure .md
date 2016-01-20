##openthos 功能测试的测试 流程

* [[安装新IMG| ]]
* 安装完系统后需进行的设置
  * 安装好系统后设置-应用兼容性-打开可兼容使用arm库的应用 
  * 显示-设备旋转时-保持当前方向（横屏时设置）
  * 双击预安装的rotation locker-landscape。使竖屏切换成横屏
* 安装所需APK包到系统(三种方法)
  * 播放含apk包的U盘，点击进行安装
  * 豌豆夾进行安装
  * pm install packagename进行安装
* 运行各APP，且街截取LOG信息并上传至此目录下（步骤）
  * #cd /data/
  * #cat /dev/null>log.txt
  * 执行安装和运行APP使用测试 
  * #cp log.txt date-apkname-log-version.txt
  * 将所有app的log.txt文件上传至 [[app-testing-results |https://github.com/openthos/app-testing-results]] 对应目录下
* 汇总各APP测试结果至app-list.md文件中。使其一目了解的看到测试结果
  * 当前版本测试结果始终放在最上面，方便查看。
  * 每版测试结果包含CPU，测试版本、各APP测试结果


