# Pafy–获取视频的音频流

> 原文:[https://www . geesforgeks . org/pafy-get-音频-视频流/](https://www.geeksforgeeks.org/pafy-getting-audio-streams-of-the-video/)

在本文中，我们将看到如何在 pafy 中获取给定 youtube 视频的音频流。Pafy 是一个 python 库，用于下载 YouTube 内容和检索元数据。Pafy 对象是包含给定视频所有信息的对象。音频流基本上是所有可用于视频的音频流。

我们可以借助`new`方法获取 pafy 对象，下面是给定视频获取 pafy 对象的命令

```
video = pafy.new(url)
```

视频网址应该存在于 youtube 上，因为它获得了那些在 youtube 上出现的视频的信息。YouTube 是一个美国在线视频分享平台。

为此，我们对视频的 pafy 对象使用`audiostreams`属性

> **语法:**视频.音频流
> 
> **论证:**不需要论证
> 
> **返回:**返回流列表

下面是实现

```
# importing pafy
import pafy 

# url of video 
url = "https://www.youtube.com / watch?v = vG2PNdI8axo"

# getting video
video = pafy.new(url) 

# getting audio streams of the video
value = video.audiostreams

# printing the value
print(value)
```

**输出:**

```
[audio:webm@50k, audio:webm@70k, audio:m4a@128k, audio:webm@160k]

```

另一个例子

```
# importing pafy
import pafy 

# url of video 
url = "https://www.youtube.com / watch?v = mmjDZGSr7EA"

# getting video
video = pafy.new(url) 

# getting audio streams of the video
value = video.audiostreams

# printing the value
print(value)
```

**输出:**

```
[audio:webm@50k, audio:webm@70k, audio:m4a@128k, audio:webm@160k]

```