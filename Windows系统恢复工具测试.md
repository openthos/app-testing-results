# Windows系统恢复工具测试
## windows 镜像下载
  - 选中win10-》下一步-》出现进度条，等待进度条走完（）

## windows 镜像部署
  - 提示：“请选择windows恢复分区，并按下一步”
  - 手动选择安装windows的数据分区-点下一步。提示“正在检验wim文件完整性，请耐心等待”
  - 弹出“系统将恢复到分区：/dev/block/sda4（上步中选择的分区，此处为sda4）,原有数据将会丢失”-点击 确定按钮
  - 弹出正在恢复windows系统，请耐心等待进度条。
    
## 检验文件完整性
  - 将 windows.wim 和 efi.tar 拷贝到 /sdcard/tsing_recovery/下
  
  
