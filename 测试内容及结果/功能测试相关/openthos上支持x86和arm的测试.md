支持x86，经测试，编译生成的镜像基本可以运行

```
repo init -u git://192.168.0.115/android-desktop/manifest -b android-desktop-oreo-mr1 --repo-url=git://192.168.0.115/tools/repo
repo sync -f -j1
./build/envsetup.sh
lunch generic_pc-userdebug
make iso_img -j32

# 将生成的镜像刻入U盘
# 在电脑上设置从U盘启动
# 登入系统
```

支持arm Pixel C

```
repo init -u git://192.168.0.115/android-desktop/manifest -b multiwindow-oreo-mr1-temp --repo-url=git://192.168.0.115/tools/repo
repo sync -f -j1
./build/envsetup.sh
lunch aosp_dragon-userdebug
make -j32

# Pixel C用type C数据线连接到电脑
# Pixel C进入fastboot模式
fastboot flash boot boot.img 
fastboot flash recovery recovery.img 
fastboot flash system system.img 
fastboot flash vendor vendor.img 
fastboot flash cache cache.img 
fastboot -w
fastboot reboot
# 重启登入系统
```

