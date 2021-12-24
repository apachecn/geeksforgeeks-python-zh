# Pafy–获取视频的元数据

> 原文:[https://www . geesforgeks . org/pafy-get-meta-data-of-video/](https://www.geeksforgeeks.org/pafy-getting-meta-data-of-the-video/)

在本文中，我们将看到如何在 pafy 中获取给定 youtube 视频的元数据。Pafy 是一个 python 库，用于下载 YouTube 内容和检索元数据。Pafy 对象是包含给定视频所有信息的对象。元数据是“提供其他数据信息的数据”。换句话说，它是“关于数据的数据”存在许多不同类型的元数据，包括描述性元数据、结构性元数据、管理元数据、参考元数据和统计元数据。

我们可以借助`new`方法获取 pafy 对象，下面是给定视频获取 pafy 对象的命令

```py
video = pafy.new(url)
```

视频网址应该存在于 youtube 上，因为它获得了那些在 youtube 上出现的视频的信息。YouTube 是一个美国在线视频分享平台。

为了做到这一点，我们使用`__repr__`方法与视频的 pafy 对象

> **语法:**视频。__repr__()
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

# getting meta data of video
value = video.__repr__()

# printing the value
print("Meta Data : " + value)
```

**输出:**

```py
Meta Data : Title: DSA Self Paced Course | GeeksforGeeks
Author: GeeksforGeeks
ID: vG2PNdI8axo
Duration: 00:01:06
Rating: 4.6923075
Views: 75562
Thumbnail: http://i.ytimg.com/vi/vG2PNdI8axo/default.jpg

```

另一个例子

```py
# importing pafy
import pafy 

# url of video 
url = "https://www.youtube.com / watch?v = i6rhnSoK_gc"

# getting video
video = pafy.new(url) 

# getting meta data of video
value = video.__repr__()

# printing the value
print("Meta Data : " + value)
```

**输出:**

```py
Meta Data : Title: COVID CASE IN OUR BUILDING - VLOG 32
Author: Tanmay Bhat
ID: i6rhnSoK_gc
Duration: 00:11:42
Rating: 4.9447651
Views: 1128643
Thumbnail: http://i.ytimg.com/vi/i6rhnSoK_gc/default.jpg

```