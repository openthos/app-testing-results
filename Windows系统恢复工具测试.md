# Windows系统恢复工具测试

## 安装windows+openthos双系统
  - 分区
    - uefi分区(2G) 里面有efi相关的文件，openthos的system.sfs文件（是的，初期我们不做独立system分区），以及用于重置和升级系统的相关脚本，
    - oto_data分区（ext4, 8G）openthos的/data目录
    - windows分区（ntfs, 100G）
    - data分区（exfat，剩下所有空间）
  - ubuntu分区完成后，先安装windows，安装过程中选择自定义安装，其中需要将分区3（100G）先删除，再新建，点击确定后windows会自动划分出另外的三个分区，选择主分区安装
  - 手动安装openthos（目前手动安装后无法启动openthos，需要U盘启动引导）

## windows 镜像下载
  - 选中win10-》下一步-》出现进度条，等待进度条走完（）

## windows 镜像部署
  - 提示：“请选择windows恢复分区，并按下一步”
  - 手动选择安装windows的数据分区-点下一步。提示“正在检验wim文件完整性，请耐心等待”
  - 弹出“系统将恢复到分区：/dev/block/sda6（上步中选择的分区，此处为sda6）,原有数据将会丢失”-点击 确定按钮
  - 弹出正在恢复windows系统，请耐心等待进度条。
  - 等待一段时间后弹出“系统已经恢复成功”-重新启动。可立即重启，也可稍后重启。
    
## 检验文件完整性
  - 重启到WINDOS，检查是否恢复成功
  
  
