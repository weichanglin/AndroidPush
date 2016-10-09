# AndroidPush

### 使用
>1. 调用Push的register()方法即可。代码会判断当前手机的类型，如果是小米则启动小米推送，华为则启用华为推送，flyme则启用flyme推送，其他情况下启用极光推送
>2. 实现PushInterface接口，然后根据各个回调方法做相关的任务


### 各个推送的特殊情况说明 （个人理解）
>1. 小米和极光推送做的都很不错，没什么可说的

>2. 华为推送
如果推送的消息类型为透传消息的话，则无法使用extra字段，只可以用onPushMsg()回调中的 byte[] msg 参数。
通知栏的话,只有点击以后的回调接口

>3. flyme推送
无法对通知栏做任何的控制(除了改改样式),一切都由服务器控制
透传消息的话，在onMessage()的回调中使用。
