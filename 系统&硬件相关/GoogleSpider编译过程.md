#### 环境准备

```
# 需要安装python3，node
apt install python3 node

＃ 需要安装mongodb,robo3t

# 需要一个运行在x86上的安卓系统

# 本机需要能连接到googleplay
```



#### 自动执行

```
# 注：需要修改源文件中的脚本中的路径，以与本机相符
# 注：需要修改脚本里googleplay的账户和密码
git clone //192.168.0.185/openthos/oto-GooglePlayspider
cd oto-GooglePlayspider
tar xf apkinfo_v1.1.6.tar.bz2

sudo apt install python3-scrapy
sudo apt install mongodb

./menu.sh
# 如果提示 ModuleNotFoundError: No module named 'selenium' ，则sudo apt install python3-selenium
# 如果提示 ModuleNotFoundError: No module named 'items'，这是因为在google.py里sys.path.append路径不正确，改正即可。
# 如果提示 ModuleNotFoundError: No module named 'pymongo'，则sudo apt install python3-pymongo
```

#### 分步执行

##### 1 抓取google play上的信息，保存在数据库里

```
tar xf apkinfo*.tar.bz2
cd apkinfo_v1.1-CN/apkinfo
scrapy crawl google		# 注意要在apkinfo目录下，且连接vPN才可成功运行
	# 如碰到“不能解码”的错误，可删除代码里对应的注释符号
python3 DuplicateRemoval.py	# app信息去重
```

##### 2 运行down_main_all.js下载所有apk

```
cd AppStore
node down_main_all.js 		# 大量timeoutError，对网络要求较高
	# 如“Cannot find module xxx”，则"npm i xxx"
	# 修改account和password，还有邮件接收者
```

##### 3 拷贝虚拟机里/data/app目录到本地的目录

```
sudo vmvare-mount PhoenixOS.vmdk 1 -o ro /mnt
cd /mnt/PhoenixOS/data
cp -r app /data/apk
sudo vmvare-mount -x
```

##### 4 应用信息写入数据库

```
mkdir image
python3 download_img.py		# 下载所有apk的图标
python3 aapt.py				# 解析出openthos应用商店需要的信息
python3 aggregate.py		# 生成应用商店需要的all文件和game文件
```

##### 5 上传apk到应用商店

```
cp -r image icon
./push.sh
```

