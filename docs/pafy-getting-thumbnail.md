# 点击获取缩略图

> 原文:[https://www.geeksforgeeks.org/pafy-getting-thumbnail/](https://www.geeksforgeeks.org/pafy-getting-thumbnail/)

在本文中，我们将看到如何在 pafy 中获得给定 youtube 视频的缩略图。Pafy 是一个 python 库，用于下载 YouTube 内容和检索元数据。Pafy 对象是包含给定视频所有信息的对象。缩略图是图片或视频的缩小版本，用于帮助识别和组织它们，对图像的作用与普通文本索引对单词的作用相同。

我们可以借助`new`方法获取 pafy 对象，下面是给定视频获取 pafy 对象的命令

```
video = pafy.new(url)
```

视频网址应该存在于 youtube 上，因为它获得了那些在 youtube 上出现的视频的信息。YouTube 是一个美国在线视频分享平台。

为此，我们对视频的 pafy 对象使用`thumb`属性

> **语法:**视频.拇指
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

# getting thumbnail of the video
value = video.thumb

# printing the value
print("Thumbnail : " + value)
```

**输出:**

```
Thumbnail : http://i.ytimg.com/vi/vG2PNdI8axo/default.jpg

```

当我们打开这个链接时，下面给出的图像出现
![](img/9cd601aaa6a7ba1ee319ce494d158ce5.png)

另一个例子

```
# importing pafy
import pafy 

# url of video 
url = "https://www.youtube.com / watch?v = vVSKoLJmn8w&t = 13s"

# getting video
video = pafy.new(url) 

# getting thumbnail of the video
value = video.thumb

# printing the value
print("Thumbnail : " + value)
```

**输出:**

```
Thumbnail : http://i.ytimg.com/vi/i6rhnSoK_gc/default.jpg

```