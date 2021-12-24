# Pafy–获取视频长度

> 原文:[https://www . geesforgeks . org/pafy-get-length-of-video/](https://www.geeksforgeeks.org/pafy-getting-length-of-the-video/)

在本文中，我们将看到如何在 pafy 中获得给定 youtube 视频的长度。Pafy 是一个 python 库，用于下载 YouTube 内容和检索元数据。Pafy 对象是包含给定视频所有信息的对象。与持续时间不同，长度是视频的持续时间，以秒为单位，即视频有多长。

我们可以借助`new`方法获取 pafy 对象，下面是给定视频获取 pafy 对象的命令

```
video = pafy.new(url)
```

视频网址应该存在于 youtube 上，因为它获得了那些在 youtube 上出现的视频的信息。YouTube 是一个美国在线视频分享平台。

为此，我们对视频的 pafy 对象使用`length`属性

> **语法:**视频.长度
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

# getting length of the video
value = video.length

# printing the value
print("Length : " + str(value))
```

**输出:**

```
Length : 66

```

另一个例子

```
# importing pafy
import pafy 

# url of video 
url = "https://www.youtube.com / watch?v = i6rhnSoK_gc"

# getting video
video = pafy.new(url) 

# getting length of the video
value = video.length

# printing the value
print("Length : " + str(value))
```

**输出:**

```
Length : 702

```