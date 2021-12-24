# Pafy–获取流的分辨率

> 原文:[https://www . geeksforgeeks . org/pafy-get-resolution-of-stream/](https://www.geeksforgeeks.org/pafy-getting-resolution-of-stream/)

在本文中，我们将了解如何在 pafy 中获得给定 youtube 视频流的分辨率。Pafy 是一个 python 库，用于下载 YouTube 内容和检索元数据。Pafy 对象是包含给定视频所有信息的对象。分辨率是视频流的质量，最流行的标准分辨率是视频 640×360 和 640×480，DVD 720×480 和 720×576。高清视频通常分辨率为 1280×720 (720p)或 1920×1080 (1080p，也称为全高清)。对于音频分辨率值为 0

借助`new`方法，我们可以得到 pafy 对象，借助`allstreams`属性，我们可以得到视频可用的所有流，下面是获取给定视频的 pafy 对象的命令

```py
video = pafy.new(url)
streams = video.allstreams

```

视频网址应该存在于 youtube 上，因为它获得了那些在 youtube 上出现的视频的信息。YouTube 是一个美国在线视频分享平台。

为此，我们对视频的 pafy 流对象使用`resolution`属性

> **语法:**流分辨率。
> 
> **论证:**不需要论证
> 
> **返回:**返回字符串

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

# selecting one stream
stream = streams[1]

# getting resolution of stream
value = stream.resolution

# printing the value
print("Resolution : " + str(value))
```

**输出:**

```py
Resolution : 0x0

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

# selecting one stream
stream = streams[4]

# getting resolution of stream
value = stream.resolution

# printing the value
print("Resolution : " + str(value))
```

**输出:**

```py
Resolution : 256x144

```