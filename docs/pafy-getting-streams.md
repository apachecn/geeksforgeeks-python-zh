# Pafy–获取流

> 原文:[https://www.geeksforgeeks.org/pafy-getting-streams/](https://www.geeksforgeeks.org/pafy-getting-streams/)

在本文中，我们将看到如何在 pafy 中获取给定 youtube 视频的流。Pafy 是一个 python 库，用于下载 YouTube 内容和检索元数据。Pafy 对象是包含给定视频所有信息的对象。流基本上是给定视频的可用流，它不包括音频和视频的单独值。

我们可以借助`new`方法获取 pafy 对象，下面是给定视频获取 pafy 对象的命令

```py
video = pafy.new(url)
```

视频网址应该存在于 youtube 上，因为它获得了那些在 youtube 上出现的视频的信息。YouTube 是一个美国在线视频分享平台。

为此，我们对视频的 pafy 对象使用`streams`属性

> **语法:**视频流
> 
> **论证:**不需要论证
> 
> **返回:**返回列表

下面是实现

```py
# importing pafy
import pafy 

# url of video 
url = "https://www.youtube.com / watch?v = vG2PNdI8axo"

# getting video
video = pafy.new(url) 

# getting video streams  of the video
value = video.streams

# printing the value
print("Streams : " + str(value))
```

**输出:**

```py
Streams : [normal:mp4@640x360, normal:mp4@1280x720]

```

另一个例子

```py
# importing pafy
import pafy 

# url of video 
url = "https://www.youtube.com / watch?v = i6rhnSoK_gc"

# getting video
video = pafy.new(url) 
# getting video streams  of the video
value = video.streams

# printing the value
print("Streams : " + str(value))
```

**输出:**

```py
Streams : [normal:mp4@640x360, normal:mp4@1280x720]

```