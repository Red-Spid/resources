# **vx 中 audio 不在支持 html标记**

> 使用 wx.createInnerAudioContext() 方法代替

> .src 为播放地址

> 播放暂停等方法未作改变

[官网地址]([InnerAudioContext | 微信开放文档 (qq.com)](https://developers.weixin.qq.com/miniprogram/dev/api/media/audio/InnerAudioContext.html))

~~~js
InnerAudioContext.play()
播放

InnerAudioContext.pause()
暂停。暂停后的音频再播放会从暂停处开始播放

InnerAudioContext.stop()
停止。停止后的音频再播放会从头开始播放。

InnerAudioContext.seek(number position)
跳转到指定位置

InnerAudioContext.destroy()
销毁当前实例

InnerAudioContext.onCanplay(function callback)
监听音频进入可以播放状态的事件。但不保证后面可以流畅播放

InnerAudioContext.offCanplay(function callback)
取消监听音频进入可以播放状态的事件

InnerAudioContext.onPlay(function callback)
监听音频播放事件

InnerAudioContext.offPlay(function callback)
取消监听音频播放事件

InnerAudioContext.onPause(function callback)
监听音频暂停事件

InnerAudioContext.offPause(function callback)
取消监听音频暂停事件

InnerAudioContext.onStop(function callback)
监听音频停止事件

InnerAudioContext.offStop(function callback)
取消监听音频停止事件

InnerAudioContext.onEnded(function callback)
监听音频自然播放至结束的事件

InnerAudioContext.offEnded(function callback)
取消监听音频自然播放至结束的事件

InnerAudioContext.onTimeUpdate(function callback)
监听音频播放进度更新事件

InnerAudioContext.offTimeUpdate(function callback)
取消监听音频播放进度更新事件

InnerAudioContext.onError(function callback)
监听音频播放错误事件

InnerAudioContext.offError(function callback)
取消监听音频播放错误事件

InnerAudioContext.onWaiting(function callback)
监听音频加载中事件。当音频因为数据不足，需要停下来加载时会触发

InnerAudioContext.offWaiting(function callback)
取消监听音频加载中事件

InnerAudioContext.onSeeking(function callback)
监听音频进行跳转操作的事件

InnerAudioContext.offSeeking(function callback)
取消监听音频进行跳转操作的事件

InnerAudioContext.onSeeked(function callback)
监听音频完成跳转操作的事件

InnerAudioContext.offSeeked(function callback)
取消监听音频完成跳转操作的事件
~~~

