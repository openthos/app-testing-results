基于Qt的客户端

```
# 需要的库libssl-dev libcurl4-openssl-dev
scp 180:/zsm/seafile/seafile-client_20190127.tar.gz
tar xf seafile-client_20190127.tar.gz
dpkg-buildpackage -b -uc -us
./build/openthos-cloud
```

基于ndk的seafile

```
# 下载ndk
wget https://dl.google.com/android/repository/android-ndk-r17c-linux-x86_64.zip
unzip android-ndk-r17c-linux-x86_64.zip
cd android-ndk-r17c
vim .bashrc		# 将ndk加入环境变量

# 安装
scp lh@192.168.0.180:zsm/seafile/seafile-ndkbuild_20190127.tar.gz .
tar xf seafile-ndkbuild_20190127.tar.gz .
cd seafile-ndkbuild
ndk-build
```

