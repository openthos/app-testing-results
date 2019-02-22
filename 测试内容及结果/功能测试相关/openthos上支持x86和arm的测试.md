支持x86，经测试，编译生成的镜像基本可以运行

```
repo init -u git://192.168.0.115/android-desktop/manifest -b android-desktop-oreo-mr1 --repo-url=git://192.168.0.115/tools/repo
repo sync -f -j1
./build/envsetup.sh
lunch generic_pc-userdebug
make iso_img -j32
```

支持arm，当前编译过程较复杂，ZSM需要进一步修改

