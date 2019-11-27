```
repo init -u git://192.168.0.185/android-x86/manifest -b oreo-x86
repo sync -f -j1	# 如不能同步，需修改.repo/manifest.xml
make iso_img -j32
```

