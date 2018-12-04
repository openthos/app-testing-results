# kernel升级问题记录

- kernel 4.4 -> kernel 4.9
   - 打印机crash
- kernel 4.15 -> kernel 4.16
   - 相机crash
- kernel 4.15 -> kernel 4.17
   - 与mesa不适配，起不来，改用SwiftShader
   - 开机速度变慢
   - s1笔记本gfxbench无法连接服务器
- kernel 4.17 -> kernel 4.19
   - gfxbench跑高水平测试时报out of memory (出问题的为kernel4.19,mesa 18.1.8，升级mesa到18.1.9后问题消失)
   
# mesa升级或更改问题记录
- mesa13 -> SwiftShader
   - vmware上屏幕右侧有多余画面的问题
