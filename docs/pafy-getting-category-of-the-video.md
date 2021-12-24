# Pafy–获取视频类别

> 原文:[https://www . geesforgeks . org/pafy-get-category-of-the-video/](https://www.geeksforgeeks.org/pafy-getting-category-of-the-video/)

在本文中，我们将看到如何在 pafy 中获得给定 youtube 视频的类别。Pafy 是一个 python 库，用于下载 YouTube 内容和检索元数据。Pafy 对象是包含给定视频所有信息的对象。Youtube 类别是根据内容对视频进行的分类，YouTube 用户观看的前四个内容类别是喜剧、音乐、娱乐/流行文化和“如何”

我们可以借助`new`方法获取 pafy 对象，下面是给定视频获取 pafy 对象的命令

```
video = pafy.new(url)
```

视频网址应该存在于 youtube 上，因为它获得了那些在 youtube 上出现的视频的信息。YouTube 是一个美国在线视频分享平台。

为此，我们对视频的 pafy 对象使用`category`属性

> **语法:**视频.类别
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

# getting category of the video
value = video.category

# printing the value
print("Video Category : " + value)
```

**输出:**

```
Video Category : Education

```

另一个例子

```
# importing pafy
import pafy 

# url of video 
url = "https://www.youtube.com / watch?v = vVSKoLJmn8w&t = 13s"

# getting video
video = pafy.new(url) 

# getting category of the video
value = video.category

# printing the value
print("Video Category : " + value)
```

**输出:**

```
Video Category : Comedy

```