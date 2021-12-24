# Pafy–获取视频的所有流

> 原文:[https://www . geesforgeks . org/pafy-get-all-streams-of-the-video/](https://www.geeksforgeeks.org/pafy-getting-all-streams-of-the-video/)

在本文中，我们将看到如何在 pafy 中获得给定 youtube 视频的所有流。Pafy 是一个 python 库，用于下载 YouTube 内容和检索元数据。Pafy 对象是包含给定视频所有信息的对象。所有流基本上是视频和音频组合的所有可用流。

我们可以借助`new`方法获取 pafy 对象，下面是给定视频获取 pafy 对象的命令

```
video = pafy.new(url)
```

视频网址应该存在于 youtube 上，因为它获得了那些在 youtube 上出现的视频的信息。YouTube 是一个美国在线视频分享平台。

为此，我们对视频的 pafy 对象使用`allstreams`属性

> **语法:** video.allstreams
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

# getting allstreams of the video
value = video.allstreams

# printing the value
print(value)
```

**输出:**

```
[audio:webm@50k, audio:webm@70k, audio:m4a@128k, audio:webm@160k, video:mp4@256x144, video:webm@256x144, video:mp4@426x240, video:webm@426x240, video:mp4@640x360, video:mp4@854x480, video:webm@640x360, video:webm@854x480, video:mp4@1280x720, video:webm@1280x720, normal:mp4@640x360, normal:mp4@1280x720]

```

另一个例子

```
# importing pafy
import pafy 

# url of video 
url = "https://www.youtube.com / watch?v = mmjDZGSr7EA"

# getting video
video = pafy.new(url) 

# getting allstreams of the video
value = video.allstreams

# printing the value
print(value)
```

**输出:**

```
[audio:webm@50k, audio:webm@70k, audio:m4a@128k, audio:webm@160k, video:mp4@256x144, video:webm@256x144, video:mp4@426x240, video:webm@426x240, video:mp4@640x360, video:webm@640x360, video:webm@854x480, video:mp4@854x480, video:mp4@1280x720, video:webm@1280x720, normal:mp4@640x360, normal:mp4@1280x720]

```