# Pafy–获取给定视频的视频标识

> 原文:[https://www . geeksforgeeks . org/pafy-get-video-id-of-given-video/](https://www.geeksforgeeks.org/pafy-getting-video-id-of-the-given-video/)

在本文中，我们将看到如何在 pafy 中获取给定 youtube 视频的视频 ID。Pafy 是一个 python 库，用于下载 YouTube 内容和检索元数据。Pafy 对象是包含给定视频所有信息的对象。Youtube 视频标识是识别上传到 Youtube 的视频的唯一标识。Youtube 视频 ID 用于创建显示视频的唯一网址，并可用于在任何网站上嵌入 Youtube 视频。

我们可以借助`new`方法获取 pafy 对象，下面是给定视频获取 pafy 对象的命令

```py
video = pafy.new(url)
```

视频网址应该存在于 youtube 上，因为它获得了那些在 youtube 上出现的视频的信息。YouTube 是一个美国在线视频分享平台。

为此，我们对视频的 pafy 对象使用`videoid`属性

> **语法:** video.videoid
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

# getting video ID
value = video.videoid

# printing the value
print("Video ID : " + value)
```

**输出:**

```py
Video ID : vG2PNdI8axo

```

另一个例子

```py
# importing pafy
import pafy 

# url of video 
url = "https://www.youtube.com / watch?v = i6rhnSoK_gc"

# getting video
video = pafy.new(url) 

# getting video ID
value = video.videoid

# printing the value
print("Video ID : " + value)
```

**输出:**

```py
Video ID : i6rhnSoK_gc

```