# Pafy–获取超大视频缩略图

> 原文:[https://www . geesforgeks . org/pafy-get-超大视频缩略图/](https://www.geeksforgeeks.org/pafy-getting-extra-large-thumbnail-of-video/)

在本文中，我们将看到如何在 pafy 中获得给定 youtube 视频的超大缩略图。Pafy 是一个 python 库，用于下载 YouTube 内容和检索元数据。Pafy 对象是包含给定视频所有信息的对象。缩略图是图片或视频的缩小版本，用于帮助识别和组织它们，对图像的作用与普通文本索引对单词的作用相同。超大缩略图比普通大缩略图大。

我们可以借助`new`方法获取 pafy 对象，下面是给定视频获取 pafy 对象的命令

```
video = pafy.new(url)
```

视频网址应该存在于 youtube 上，因为它获得了那些在 youtube 上出现的视频的信息。YouTube 是一个美国在线视频分享平台。

为此，我们对视频的 pafy 对象使用`bigthumbhd`属性

> **语法:** video.bigthumbhd
> 
> **论证:**不需要论证
> 
> **返回:**返回大缩略图链接的字符串

下面是实现

```
# importing pafy
import pafy 

# url of video 
url = "https://www.youtube.com / watch?v = vG2PNdI8axo"

# getting video
video = pafy.new(url) 

# getting extra large thumbnail of the video
value = video.bigthumbhd

# printing the value
print("Extra Large Thumbnail : " + value)
```

**输出:**

```
Extra Large Thumbnail : http://i.ytimg.com/vi/vG2PNdI8axo/hqdefault.jpg

```

当我们打开这个链接时，下面给出的图像出现
![](img/3e936bfb1c7b833af09b4f8b52ba20be.png)

另一个例子

```
# importing pafy
import pafy 

# url of video 
url = "https://www.youtube.com / watch?v = vVSKoLJmn8w&t = 13s"

# getting video
video = pafy.new(url) 

# getting extra large thumbnail of the video
value = video.bigthumbhd

# printing the value
print("Extra Large Thumbnail : " + value)
```

**输出:**

```
Extra Large Thumbnail : http://i.ytimg.com/vi/vVSKoLJmn8w/hqdefault.jpg

```