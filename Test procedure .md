##openthos 功能测试的测试 流程

* [[安装新IMG| ]]

* 安装所需APK包到系统(三种方法)
  * 播放含apk包的U盘，点击进行安装
  * 豌豆夾进行安装
  * pm install packagename进行安装
* 运行各APP，且街截取LOG信息并上传至此目录下（步骤）
  * #cd /data/
  * #cat /dev/null>log.txt
  * 执行安装和运行APP使用测试 
  * #cp log.txt date-apkname-log-version.txt
* 汇总各APP测试结果至app-list.md文件中。使其一目了解的看到测试结果


