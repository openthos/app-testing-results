## 报错
### java.lang.SecurityException
问题：   
运行自动化测试时报错longMsg=java.lang.SecurityException: Permission Denial: getIntentSender() from pid=8427, uid=2000, (need uid=1000) is not allowed to send as package android    
workaround：   
有些无障碍服务打开时运行uiautomator会出现这个错误，比如TalkBack、Tincore KeyMapper等，可以在设置 ->无障碍中关闭这些服务
