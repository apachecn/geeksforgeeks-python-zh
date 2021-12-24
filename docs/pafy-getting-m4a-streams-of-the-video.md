# Pafy–获取视频的 M4A 流

> 原文:[https://www . geesforgeks . org/pafy-get-m4a-streams-of-the-video/](https://www.geeksforgeeks.org/pafy-getting-m4a-streams-of-the-video/)

在本文中，我们将看到如何在 pafy 中获得给定 youtube 视频的 m4a 编码流。Pafy 是一个 python 库，用于下载 YouTube 内容和检索元数据。Pafy 对象是包含给定视频所有信息的对象。M4A 是用高级音频编码(AAC)编码的音频文件的文件扩展名，高级音频编码是一种有损压缩。M4A 通常被认为是 MP3 的继承者，MP3 最初不是仅为音频设计的，而是 MPEG 1 或 2 视频文件中的第三层。M4A 代表 MPEG 4 音频。

我们可以借助`new`方法获取 pafy 对象，下面是给定视频获取 pafy 对象的命令

```py
video = pafy.new(url)
```

视频网址应该存在于 youtube 上，因为它获得了那些在 youtube 上出现的视频的信息。YouTube 是一个美国在线视频分享平台。

为此，我们对视频的 pafy 对象使用`m4astreams`属性

> **语法:** video.m4astreams
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

# getting m4a encoded streams of the video
value = video.m4astreams

# printing the value
print(value)
```

**输出:**

```py
[audio:m4a@128k]

```

另一个例子

```py
# importing pafy
import pafy 

# url of video 
url = "https://www.youtube.com / watch?v = i6rhnSoK_gc"

# getting video
video = pafy.new(url) 

# getting m4a encoded streams of the video
value = video.m4astreams

# printing the value
print(value)
```

**输出:**

```py
[audio:m4a@128k]

```