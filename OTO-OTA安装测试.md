###注意事项
1. 必须 UEFI ,关闭 secure boot


###自动安装操作步骤：
1）安装without extract

2) auto install (说明文本中有单词错误 will -> wilal;;erase->EARSE，需修改)

3) 自动安装会删除化整个硬盘，可以选择手动安装来规避此问题

4） 自动化安装时分两个分区
    8G -------system file
    20G ---------app and data
    
5)安装命令行有句 提示0 写入

6）无法自动进入到系统，必须 F10，进入菜单选择。手动选择刚安装的硬盘。如：UEFI OF（P2：LITEON CV1-8B128）

7）安装后有ubuntu,android两个图标，点ubuntu图标也进入 openthos系统，但进入的是之前安装好的系统，非新安装的系统。怪异
   原因：sda硬盘上有两个系统，一个ubuntu,一个android.扫描到ubuntu，但安装android时安装了grub ,替换掉了ubuntu grub。导致的此问题
   

###手动安装操作步骤：
1） oto install without extract
    oto install with extract []
