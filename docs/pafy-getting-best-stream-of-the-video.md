# Pafy–获得最佳视频流

> 原文:[https://www . geesforgeks . org/pafy-获取最佳视频流/](https://www.geeksforgeeks.org/pafy-getting-best-stream-of-the-video/)

在本文中，我们将了解如何在 pafy 中获得给定 youtube 视频的最佳流。Pafy 是一个 python 库，用于下载 YouTube 内容和检索元数据。Pafy 对象是包含给定视频所有信息的对象。最佳流基本上是一个视频+音频流，这是可用的，并在最高的分辨率。这是视频+音频的最佳流。

我们可以借助`new`方法获取 pafy 对象，下面是给定视频获取 pafy 对象的命令

```
video = pafy.new(url)
```

视频网址应该存在于 youtube 上，因为它获得了那些在 youtube 上出现的视频的信息。YouTube 是一个美国在线视频分享平台。

为了做到这一点，我们使用`getbest`方法与视频的 pafy 对象

> **语法:** video.getbest()
> 
> **论证:**不需要论证
> 
> **返回:**返回 YtdlStream 对象

下面是实现

```
# importing pafy
import pafy 

# url of video 
url = "https://www.youtube.com / watch?v = vG2PNdI8axo"

# getting video
video = pafy.new(url)

# getting best stream of video
value = video.getbest()

# printing the value
print("Best Stream : " + str(value))
```

**输出:**

```
Best Stream : normal:mp4@1280x720

```

另一个例子

```
# importing pafy
import pafy 

# url of video 
url = "https://www.youtube.com / watch?v = i6rhnSoK_gc"

# getting video
video = pafy.new(url) 

# getting best stream of video
value = video.getbest()

# printing the value
print("Best Stream : " + str(value))
```

**输出:**

```
Best Stream : normal:mp4@1280x720

```