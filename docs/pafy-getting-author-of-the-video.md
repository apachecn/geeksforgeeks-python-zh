# Pafy–获取视频作者

> 原文:[https://www . geesforgeks . org/pafy-get-视频作者/](https://www.geeksforgeeks.org/pafy-getting-author-of-the-video/)

在本文中，我们将看到如何在 pafy 中找到给定 youtube 视频的作者。Pafy 是一个 python 库，用于下载 YouTube 内容和检索元数据。Pafy 对象是包含给定视频所有信息的对象。作者基本上是 youtube 上视频的上传者。

我们可以借助`new`方法获取 pafy 对象，下面是给定视频获取 pafy 对象的命令

```
video = pafy.new(url)
```

视频网址应该存在于 youtube 上，因为它获得了那些在 youtube 上出现的视频的信息。YouTube 是一个美国在线视频分享平台。

为此，我们对视频的 pafy 对象使用`author`属性

> **语法:**视频.作者
> 
> **论证:**不需要论证
> 
> **返回:**返回字符串

下面是实现

```
# importing pafy
import pafy 

# url of video 
url = "https://www.youtube.com / watch?v = vG2PNdI8axo"

# getting video
video = pafy.new(url) 

# getting author of the video
value = video.author

# printing the value
print("Author : " + value)
```

**输出**

```
Author : GeeksforGeeks

```

另一个例子

```
# importing pafy
import pafy 

# url of video 
url = "https://www.youtube.com / watch?v = vVSKoLJmn8w&t = 13s"

# getting video
video = pafy.new(url) 

# getting author of the video
value = video.author

# printing the value
print("Author : " + value)
```

**输出**

```
Author : Triggered Insaan

```