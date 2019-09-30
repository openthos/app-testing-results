#### 支持x86，单窗口

```
repo init -u git://192.168.0.115/android-desktop/manifest -b android-desktop-oreo-mr1 --repo-url=git://192.168.0.115/tools/repo
repo sync -f -j1
. build/envsetup.sh
lunch generic_pc-userdebug
make iso_img -j32

# 将生成的镜像刻入U盘
# 在电脑上设置从U盘启动
# 登入系统
```

#### 支持x86，多窗口

```
# 前提是已安装x86的单窗口代码，否则不执行对.repo目录的操作
mv .repo _repo
repo init -u git://192.168.0.115/android-desktop/manifest -b multiwindow-oreo-mr1 --repo-url=git://192.168.0.115/tools/repo
mv _repo/project*s .repo
rm -rf _repo out
rm -rf *		# 注：由于目前对源码的修改较为激进，每次编译前都需要重新删除所有的源码并重新同步
repo sync -f -j1
source build/envsetup.sh
lunch generic_pc-userdebug
make iso_img -j32

# 将生成的镜像刻入U盘
# 在电脑上设置从U盘启动
# 登入系统
```

#### android-desktop-pie

```
repo init -u git://192.168.0.115/android-desktop/manifest -b multiwindow-oreo-mr1 --repo-url=git://192.168.0.115/tools/repo
repo sync -f -j1

# 注：由于目前相关的软件仓库还没更新，需要从cwhuang的目录把相关仓库复制过来
rm -rf external/ffmpeg external/stagefright-plugins
cp -r -t external/ $HOME/cwhuang/external/ffmpeg $HOME/cwhuang/external/stagefright-plugins

. build/envsetup.sh
lunch generic_pc-userdebug
make iso_img -j32
```



#### 支持GoogleTV机顶盒

```
repo init -u git://192.168.0.115/android-desktop/manifest -b multiwindow-oreo-mr1-temp --repo-url=git://192.168.0.115/tools/repo
repo sync -f -j1
. build/envsetup.sh
lunch aosp-fugu_userdebug
make -j32

# Google TV连接电脑
adb devices 	# 确认已连接
adb reboot recovery	# 重启进入recovery模式
fastboot devices	# 确认已连接
fastboot flash boot boot.img
fastboot flash recovery ercovery.img
fastboot flash system system.img
fastboot -w
fastboot reboot
```



#### 支持arm Pixel C

```
repo init -u git://192.168.0.115/android-desktop/manifest -b multiwindow-oreo-mr1-temp --repo-url=git://192.168.0.115/tools/repo
repo sync -f -j1
. build/envsetup.sh
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

