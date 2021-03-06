# Pafy–获得最佳视频缩略图

> 原文:[https://www . geesforgeks . org/pafy-get-best-缩略图视频/](https://www.geeksforgeeks.org/pafy-getting-best-thumbnail-of-the-video/)

在本文中，我们将看到如何在 pafy 中获得给定 youtube 视频的最佳缩略图。Pafy 是一个 python 库，用于下载 YouTube 内容和检索元数据。Pafy 对象是包含给定视频所有信息的对象。缩略图是图片或视频的缩小版本，用于帮助识别和组织它们，对图像的作用与普通文本索引对单词的作用相同。最佳缩略图是所有可用缩略图中分辨率最高的缩略图

我们可以借助`new`方法获取 pafy 对象，下面是给定视频获取 pafy 对象的命令

```py
video = pafy.new(url)
```

视频网址应该存在于 youtube 上，因为它获得了那些在 youtube 上出现的视频的信息。YouTube 是一个美国在线视频分享平台。

为了做到这一点，我们使用`getbestthumb`方法与视频的 pafy 对象

> **语法:**video . getbestumb()
> 
> **论证:**不需要论证
> 
> **返回:**返回图像的链接字符串

下面是实现

```py
# importing pafy
import pafy 

# url of video 
url = "https://www.youtube.com / watch?v = vG2PNdI8axo"

# getting video
video = pafy.new(url)

# getting best thumbnail of video
value = video.getbestthumb()

# printing the value
print("Best Thumbnail: " + str(value))
```

**输出:**

```py
Best Thumbnail: https://i.ytimg.com/vi/vG2PNdI8axo/hqdefault.jpg?sqp=-oaymwEYCKgBEF5IVfKriqkDCwgBFQAAiEIYAXAB&rs=AOn4CLC_-IzdZ3mCtOwNAt9vRGH37r3lPw

```

另一个例子

```py
# importing pafy
import pafy 

# url of video 
url = "https://www.youtube.com / watch?v = i6rhnSoK_gc"

# getting video
video = pafy.new(url) 

# getting best thumbnail of video
value = video.getbestthumb()

# printing the value
print("Best Thumbnail: " + str(value))
```

**输出:**

```py
Best Thumbnail: https://i.ytimg.com/vi/i6rhnSoK_gc/hqdefault.jpg?sqp=-oaymwEYCKgBEF5IVfKriqkDCwgBFQAAiEIYAXAB&rs=AOn4CLD-H7SG3HtUA_fpvaOGIU0cqulv4Q

```