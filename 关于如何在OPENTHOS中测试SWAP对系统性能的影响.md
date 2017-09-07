# 关于如何在OPENTHOS中测试SWAP对系统性能的影响

## 设置
  - 1、打开OPENTHOS的终端程序， 输入命令su进入到管理员状态
  - 2、使用dd创建一个swap.img文件  （仅首次设置时需要运行）  
    
    ` dd if=/dev/zero of=/data/swap.img bs=1g count=8   (count为几就表示创建几个GB的SWAP）`

  - 3、使用vi /data/startswap.sh来创建swap的启用脚本，文件内容如下：  (仅首次设置需要运行）
  
    ` #!/system/xbin/ash`
    
    ` losetup /dev/block/loop7 /data/swap.img`
    
    ` mkswap /dev/block/loop7`
    
    ` swapon /dev/block/loop7`
      
  - 4、使用chmod来给 startswap.sh赋予运行权限  (仅首次设置需要运行）
  
    ` chmod 755 /data/startswap.sh`

  - 5、执行startswap.sh来进行相关测试
  
    ` ./startswap.sh`

  - 如果想测试swap配合小内存时的效果，需要在系统启动时限制系统可以使用的内存大小
  
    ` mkdir /mnt/tmp/disk`
    
    ` mount -t vfat /dev/block/sdb1 /mnt/tmp/disk      对于T45而言ssd是sdb， 如系统是安装在机械硬盘上，则为sda1.`
    
    ` vi /mnt/tmp/disk/OpenThos/boto_linux.conf 为相应的引导选项加上参数mem=1G`，比如T45在第一行的quiet前加上mem=1G ,添加后的结果如下   
    `"OpenThos" "mem=1G quiet androidboot.h...`
  
  ## 20170906测试结果
  机器|swapoff|swapon+内存限制|
  ----|----|----|
  T45|pcmark：8112<br>3dmark：运行其他应用情况下会崩溃，无其他应用在运行2588|pcmark：7847<br>3dmark：2537|
  T43U|pcmark：8108<br>3dmark：2443|pcmark：6389<br>3dmark：2096|
  同方台式机<br>h110-4s-R2|pcmark：8029<br>3dmark：1765|pcmark：8218<br>3dmark：1765|
