# Pafy–取消活动下载流

> 原文:[https://www . geesforgeks . org/pafy-取消-活动-下载-流/](https://www.geeksforgeeks.org/pafy-canceling-active-download-stream/)

在本文中，我们将了解如何在 pafy 中取消给定 youtube 视频流的活动流。Pafy 是一个 python 库，用于下载 YouTube 内容和检索元数据。Pafy 对象是包含给定视频所有信息的对象。流基本上是可用的分辨率的视频是可以在 youtube 上获得的。

借助`new`方法，我们可以得到 pafy 对象，借助`allstreams`属性，我们可以得到视频可用的所有流，下面是获取给定视频的 pafy 对象的命令

```py
video = pafy.new(url)
streams = video.allstreams

```

视频网址应该存在于 youtube 上，因为它获得了那些在 youtube 上出现的视频的信息。YouTube 是一个美国在线视频分享平台。

为此，我们对视频流对象使用`cancel`方法

> **语法:** stream.cancel()
> 
> **论证:**不需要论证
> 
> **返回:**返回无

下面是实现

```py
# importing pafy
import pafy 

# url of video 
url = "https://www.youtube.com / watch?v = vG2PNdI8axo"

# getting video
video = pafy.new(url) 

# getting all the available streams
streams = video.allstreams

stream = streams[1]

# cancelling the download
stream.cancel()

print("Cancelled")
```

**输出:**

```py
Cancelled  

```

另一个例子

```py
# importing pafy
import pafy 

# url of video 
url = "https://www.youtube.com / watch?v = i6rhnSoK_gc"

# getting video
video = pafy.new(url) 

# getting all the available streams
streams = video.allstreams

stream = streams[4]

# cancelling the download
stream.cancel()

print("Cancelled")
```

**输出:**

```py
Cancelled 

```