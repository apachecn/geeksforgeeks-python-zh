# Pafy–获得视频点赞

> 原文:[https://www . geeksforgeeks . org/pafy-get-喜欢的视频/](https://www.geeksforgeeks.org/pafy-getting-likes-of-the-video/)

在本文中，我们将看到如何在 pafy 中获得给定 youtube 视频的点赞数。Pafy 是一个 python 库，用于下载 YouTube 内容和检索元数据。Pafy 对象是包含给定视频所有信息的对象。Youtube 视频有两类喜欢和不喜欢观众增加了喜欢和不喜欢的计数。

我们可以借助`new`方法获取 pafy 对象，下面是给定视频获取 pafy 对象的命令

```
video = pafy.new(url)
```

视频网址应该存在于 youtube 上，因为它获得了那些在 youtube 上出现的视频的信息。YouTube 是一个美国在线视频分享平台。

为此，我们对视频的 pafy 对象使用`likes`属性

> **语法:**视频.赞
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

# getting likes of the video
value = video.likes

# printing the value
print("Likes : " + str(value))
```

**输出:**

```
Likes : 202

```

另一个例子

```
# importing pafy
import pafy 

# url of video 
url = "https://www.youtube.com / watch?v = i6rhnSoK_gc"

# getting video
video = pafy.new(url) 

# getting likes of the video
value = video.likes

# printing the value
print("Likes : " + str(value))
```

**输出:**

```
Likes : 148627

```