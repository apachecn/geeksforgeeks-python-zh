# Pafy–获取上传者的用户名

> 原文:[https://www . geesforgeks . org/pafy-get-用户名上传者/](https://www.geeksforgeeks.org/pafy-getting-user-name-of-the-uploader/)

在本文中，我们将看到如何在 pafy 中获取给定 youtube 视频上传者的用户名。Pafy 是一个 python 库，用于下载 YouTube 内容和检索元数据。Pafy 对象是包含给定视频所有信息的对象。Username 是在 youtube 上上传给定视频的人使用的处理程序唯一名称。

我们可以借助`new`方法获取 pafy 对象，下面是给定视频获取 pafy 对象的命令

```
video = pafy.new(url)
```

视频网址应该存在于 youtube 上，因为它获得了那些在 youtube 上出现的视频的信息。YouTube 是一个美国在线视频分享平台。

为此，我们对视频的 pafy 对象使用`username`属性

> **语法:**视频.用户名
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

# getting username of the video's uploader
value = video.username

# printing the value
print("Username : " + value)
```

**输出:**

```
Username : UC0RhatS1pyxInC00YKjjBqQ

```

另一个例子

```
# importing pafy
import pafy 

# url of video 
url = "https://www.youtube.com / watch?v = vVSKoLJmn8w&t = 13s"

# getting video
video = pafy.new(url) 

# getting username of the video's uploader
value = video.username

# printing the value
print("Username : " + value)
```

**输出:**

```
Username : tanmay316

```