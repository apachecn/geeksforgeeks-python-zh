# Pafy–获取视频描述

> 原文:[https://www . geesforgeks . org/pafy-get-description-of-the-video/](https://www.geeksforgeeks.org/pafy-getting-description-of-the-video/)

在本文中，我们将看到如何在 pafy 中获得给定 youtube 视频的描述。Pafy 是一个 python 库，用于下载 YouTube 内容和检索元数据。Pafy 对象是包含给定视频所有信息的对象。YouTube 视频描述是每个视频下面的文本。它帮助观众找到内容并决定是否观看。

我们可以借助`new`方法获取 pafy 对象，下面是给定视频获取 pafy 对象的命令

```
video = pafy.new(url)
```

视频网址应该存在于 youtube 上，因为它获得了那些在 youtube 上出现的视频的信息。YouTube 是一个美国在线视频分享平台。

为此，我们对视频的 pafy 对象使用`description`属性

> **语法:**视频。描述
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

# getting description of the video
value = video.description

# printing the value
print(value)
```

**输出:**

```
Still having doubts about this course? Well, don't worry, that's how we humans are coded. But clear all your doubts by heading to the course page of the DSA Self Paced Course: https://practice.geeksforgeeks.org/co...
The course is a bestseller and one of the most promising courses for Data Structures and Algorithms by GeeksforGeeks till date. Register Now: https://practice.geeksforgeeks.org/co...

Please Like, Comment and Share the Video among your friends.

Install our Android App:
https://play.google.com/store/apps/de...

If you wish, translate into the local language and help us reach millions of other geeks:
http://www.youtube.com/timedtext_cs_p...

Follow us on Facebook:
https://www.facebook.com/GfGVideos/

And Twitter:
ht=tps://twitter.com/gfgvideos

Also, Subscribe if you haven't already! :)

```

另一个例子

```
# importing pafy
import pafy 

# url of video 
url = "https://www.youtube.com / watch?v = 3QKiK4rJIB0"

# getting video
video = pafy.new(url) 

# getting description of the video
value = video.description

# printing the value
print("Video description : " + str(value))
```

**输出:**

```
Video description : None

```