# Pafy–获得视频评分

> 原文:[https://www . geesforgeks . org/pafy-获得视频评级/](https://www.geeksforgeeks.org/pafy-getting-rating-of-the-video/)

在本文中，我们将了解如何在 pafy 中获得给定 youtube 视频的评级。Pafy 是一个 python 库，用于下载 YouTube 内容和检索元数据。Pafy 对象是包含给定视频所有信息的对象。分级基本上是从 0 到 5 的分级，它取决于观众对视频的反应。

我们可以借助`new`方法获取 pafy 对象，下面是给定视频获取 pafy 对象的命令

```py
video = pafy.new(url)
```

视频网址应该存在于 youtube 上，因为它获得了那些在 youtube 上出现的视频的信息。YouTube 是一个美国在线视频分享平台。

为此，我们对视频的 pafy 对象使用`rating`属性

> **语法:**视频.评级
> 
> **论证:**不需要论证
> 
> **返回:**返回浮动

下面是实现

```py
# importing pafy
import pafy 

# url of video 
url = "https://www.youtube.com / watch?v = vG2PNdI8axo"

# getting video
video = pafy.new(url) 

# getting rating  of the video
value = video.rating

# printing the value
print("Rating : " + str(value))
```

**输出:**

```py
Rating : 4.6894979

```

另一个例子

```py
# importing pafy
import pafy 

# url of video 
url = "https://www.youtube.com / watch?v = i6rhnSoK_gc"

# getting video
video = pafy.new(url) 

# getting rating  of the video
value = video.rating

# printing the value
print("Rating : " + str(value))
```

**输出:**

```py
Rating : 4.9455032

```