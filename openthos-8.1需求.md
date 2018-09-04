# openthos-8.1需求
1. 权限需要修改代码默认赋予openthos app，另外应用需要su提权的时候，我们应修改sudo弹出对话框要求用户输入锁屏密码，而不是让supersu额外提示授权。
2. 网络问题需要我们的xposed patch，如果想直接改原始代码也行，以太网视同无需密码的WIFI，如果需要返回SSID，返回 “OPENTHOS  LAN”（中文“OPENTHOS有线网”）。
3. 需要ubuntu binary tools,希望能用上一个真正的terminal，哪怕是chroot的
4. 提升用户体验交互感应方式：监控应用的打开关闭，区分常用应用和不常用应用；鼠标操作时能够进行调整，防止鼠标错位等问题
5. 通知中心，消息分组
6. 任务管理器在无Xposed的情况下实现阻止应用关联启动
