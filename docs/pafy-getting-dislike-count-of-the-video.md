# Pafy–获得对视频的不喜欢计数

> 原文:[https://www . geeksforgeeks . org/pafy-get-厌恶-count-of-the-video/](https://www.geeksforgeeks.org/pafy-getting-dislike-count-of-the-video/)

在本文中，我们将看到如何在 pafy 中获得给定 youtube 视频的不喜欢计数。Pafy 是一个 python 库，用于下载 YouTube 内容和检索元数据。Pafy 对象是包含给定视频所有信息的对象。一个 YouTube 视频有一个喜欢和不喜欢的计数表，但是视频所有者可以随时关闭这个功能。

我们可以借助`new`方法获取 pafy 对象，下面是给定视频获取 pafy 对象的命令

```
video = pafy.new(url)
```

视频网址应该存在于 youtube 上，因为它获得了那些在 youtube 上出现的视频的信息。YouTube 是一个美国在线视频分享平台。

为此，我们对视频的 pafy 对象使用`dislikes`属性

> **语法:**视频.不喜欢
> 
> **论证:**不需要论证
> 
> **返回:**返回整数

下面是实现

```
# importing pafy
import pafy 

# url of video 
url = "https://www.youtube.com / watch?v = vG2PNdI8axo"

# getting video
video = pafy.new(url) 

# getting dislikes of the video
value = video.dislikes

# printing the value
print(value)
```

**输出:**

```
17

```

另一个例子

```
# importing pafy
import pafy 

# url of video 
url = "https://www.youtube.com / watch?v = i6rhnSoK_gc"

# getting video
video = pafy.new(url) 

# getting dislikes of the video
value = video.dislikes

# printing the value
print(value)
```

**输出:**

```
2388

```