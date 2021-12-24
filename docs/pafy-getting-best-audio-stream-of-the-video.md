# Pafy–获得视频的最佳音频流

> 原文:[https://www . geesforgeks . org/pafy-get-best-音频-视频流/](https://www.geeksforgeeks.org/pafy-getting-best-audio-stream-of-the-video/)

在本文中，我们将了解如何在 pafy 中获得给定 youtube 视频的最佳音频流。Pafy 是一个 python 库，用于下载 YouTube 内容和检索元数据。Pafy 对象是包含给定视频所有信息的对象。最佳音频流基本上是可用且分辨率最高的音频流。这是音频可用的最佳流。

我们可以借助`new`方法获取 pafy 对象，下面是给定视频获取 pafy 对象的命令

```
video = pafy.new(url)
```

视频网址应该存在于 youtube 上，因为它获得了那些在 youtube 上出现的视频的信息。YouTube 是一个美国在线视频分享平台。

为了做到这一点，我们使用`getbestaudio`方法与视频的 pafy 对象

> **语法:**video . getbeastudio()
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

# getting best audio stream of video
value = video.getbestaudio()

# printing the value
print("Best Audio Stream : " + str(value))
```

**输出:**

```
Best Audio Stream : audio:webm@160k

```

另一个例子

```
# importing pafy
import pafy 

# url of video 
url = "https://www.youtube.com / watch?v = i6rhnSoK_gc"

# getting video
video = pafy.new(url) 
# getting best audio stream of video
value = video.getbestaudio()

# printing the value
print("Best Audio Stream : " + str(value))
```

**输出:**

```
Best Audio Stream : audio:webm@160k

```