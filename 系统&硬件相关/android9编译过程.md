方法一，直接从服务器同步

```
mkdir android-9
cd android-9
repo init -u git://192.168.0.185/android-x86/platform/manifest.git -b android-9.0.0_r46
repo sync
```

方法二，打包lxx的.repo目录

```
cd lxx/android-9
tar cf _repo.tar ./.repo
mkdir ~/qjw/android-9
mv _repo.tar ~/qjw/android-9
cd ~/qjw/android-9
tar xf _repo.tar
repo sync
```

后续工作

```
cd lxx/android-9
repo forall -c "pwd && git status"
# 找到修改的文件，复制到自己目录下对应的位置
```

