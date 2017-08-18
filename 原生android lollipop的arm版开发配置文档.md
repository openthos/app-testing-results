### Start
### 1. 下载ｒｅpo 工具(在docker中则不需要)
```
mkdir ~/bin
PATH=~/bin:$PATH
curl http://192.168.0.185/git-repo-downloads/repo > ~/bin/repo 
chmod a+x ~/bin/repo
```
### 2.建立工作目录：
```
mkdir WORKING_DIRECTORY
cd WORKING_DIRECTORY
```
### 3.初始化仓库
```
repo init -u git://192.168.0.185/lollipop/platform/manifest.git -b multiwindow  

## 如果提示无法连接到 gerrit.googlesource.com，可以编辑 ~/bin/repo，把 REPO_URL 一行替换成：REPO_URL = 'git://192.168.0.185/git-repo'
```
### 4.同步源码
```
repo sync
```
### 5. 建立ｍultiwindow开发分支
```
repo start multiwindow --all 
```
### 6.设置代码提交的远程仓库别名为“devorg”
```
repo forall -c 'git remote add devorg git://192.168.0.185/lollipop/$REPO_PROJECT.git $@'
```

***
### 7. push 代码
```
git push devorg multiwindow:refs/heads/multiwindow
```
### 8. 编译
```
source build/envsetup.sh
lunch aosp_x86_64-eng
make -j<cups>
镜像目录；out/target/product/generic_x86_64/system.img
```
### 9. 下载Ｓdk (服务器上：scp lh@192.168.0.180:~/sdk/5.1.tar.gz ./)
  - 创建模拟器：openthos
  - cd tools
  - 推荐参数：Ｎexus10, Android5.1.1 , Intel Atom(x86_64). noSkin
  - 启动：./emulator -avd openthos -system ../../../android_iso_img/system.img    (后面是：system.img的路径)
  - (如果启动的镜像修改处没有改变，则选择添加　-data ../../../android_iso_img/userdata.img)
  
  ***
 ### 10.查看ｌｏｇ
   - platform-tools: 
   - adb logcat >> DEBUG.log
   
  ##### end
