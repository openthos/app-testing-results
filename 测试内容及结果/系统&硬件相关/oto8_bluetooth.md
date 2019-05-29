#### 20190529

- patch描述：解决oto8上蓝牙不能使用的问题

- 测试平台：S1笔记本，t45笔记本，Z1-520V一体机，201905290437-oto8-eng.img

- patch内容：

  system/bt

  commit id:409538efc594458e5b826a89b04b1c18b0151f66

  Replace Bluetooth HAL by Intel's implementation. Linaro's implementation is buggy.

  commit id:c4aae0c7481b8355e3d1fb8a33182ba8f88f90a5

  Add back libbt-vendor

- 测试结果

  | 测试内容 | 测试结果                                                     |
  | -------- | ------------------------------------------------------------ |
  | 扫描     | 可以扫描到蓝牙设备，扫描结果与T45上的Ubuntu18.04一致         |
  | 配对     | 可以与T45上的Ubuntu18.04配对，可以与小米手机8SE配对，可以与WH-1000XM2配对 |
  | 传文件   | 可以向T45传文件，可以与小米手机8SE互传文件                   |
  | 播音乐   | 可以通过耳机WH-1000XM2播放音乐                               |

  

