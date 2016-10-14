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
1）安装到硬盘时有两个选项 oto install without extract，    oto install with extract 用户无法体会到区别。
2） oto install with extract 选项进入 后 安装 需要三个分区，提示需要二个，需修改


###测试机(安装过oto-ota)安装新版本（主分支-legacy）部署
    ###搭建自动安装后想重新安装新版本，有如下注意事项 ：
    1)  UEFI,切换为legacy
    2) security 切换为enable
    3) 硬盘格式由GPT 重新转化为msdos
    4) 删除oto-ota安装下化分的三个分区。然后 重新划分区
    5) 此时安装新系统方可安装成功。
    6) 如有两个硬盘，还需在BIOS中修改硬盘启动顺序
  折腾了好久，记录下来。为方便后期测试 

建议及意见： oto-ota 分支上的代码同步主分支代码，这样安装完后的版本也可作为新版本测试使用。否则要重新安装主分支版本，切换起来比较复杂。
