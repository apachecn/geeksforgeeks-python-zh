# Pafy–获取视频的 OGG 流

> 原文:[https://www . geeksforgeeks . org/pafy-get-ogg-streams-of-the-video/](https://www.geeksforgeeks.org/pafy-getting-ogg-streams-of-the-video/)

在本文中，我们将看到如何在 pafy 中获得给定 youtube 视频的 ogg 编码流。Pafy 是一个 python 库，用于下载 YouTube 内容和检索元数据。Pafy 对象是包含给定视频所有信息的对象。Ogg 是一种由 Xiph.Org 基金会维护的免费开放容器格式。Ogg 格式的创建者表示，它不受软件专利的限制，旨在提供高效的流式传输和高质量数字多媒体的操作。

我们可以借助`new`方法获取 pafy 对象，下面是给定视频获取 pafy 对象的命令

```
video = pafy.new(url)
```

视频网址应该存在于 youtube 上，因为它获得了那些在 youtube 上出现的视频的信息。YouTube 是一个美国在线视频分享平台。

为此，我们对视频的 pafy 对象使用`oggstreams`属性

> **语法:** video.oggstreams
> 
> **论证:**不需要论证
> 
> **返回:**返回列表

下面是实现

```
# importing pafy
import pafy 

# url of video 
url = "https://www.youtube.com / watch?v = vG2PNdI8axo"

# getting video
video = pafy.new(url) 

# getting ogg encoded streams of the video
value = video.oggstreams

# printing the value
print(value)
```

**输出:**

```
[]

```

另一个例子

```
# importing pafy
import pafy 

# url of video 
url = "https://www.youtube.com / watch?v = i6rhnSoK_gc"

# getting video
video = pafy.new(url) 

# getting ogg encoded streams of the video
value = video.oggstreams

# printing the value
print(value)
```

**输出:**

```
[]

```