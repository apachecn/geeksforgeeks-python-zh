# Pafy–检查流是否为 3D

> 原文:[https://www . geesforgeks . org/pafy-checking-if-stream-is-3d/](https://www.geeksforgeeks.org/pafy-checking-if-stream-is-3d/)

在这篇文章中，我们将看到我们如何检查给定的 youtube 视频流是否是 3D 的。Pafy 是一个 python 库，用于下载 YouTube 内容和检索元数据。Pafy 对象是包含给定视频所有信息的对象。3D 可视化。各种技术使图像和电影在印刷品、电脑、电影或电视上看起来更加逼真。被称为“立体成像”和“3D 立体”，人们感觉到比 2D 更深的深度，并觉得他们可以伸手触摸物体。

借助`new`方法，我们可以得到 pafy 对象，借助`allstreams`属性，我们可以得到视频可用的所有流，下面是获取给定视频的 pafy 对象的命令

```py
video = pafy.new(url)
streams = video.allstreams

```

视频网址应该存在于 youtube 上，因为它获得了那些在 youtube 上出现的视频的信息。YouTube 是一个美国在线视频分享平台。

为此，我们对视频的 pafy 对象使用`threed`属性

> **语法:**stream . 3d
> 
> **论证:**不需要论证
> 
> **返回:**返回 bool

下面是实现

```py
# importing pafy
import pafy 

# url of video 
url = "https://www.youtube.com / watch?v = vG2PNdI8axo"

# getting video
video = pafy.new(url) 

# getting all the available streams
streams = video.allstreams

# selecting one stream
stream = streams[1]

# checking if stream is 3D
value = stream.threed

# printing the value
print("3D : " + str(value))
```

**输出:**

```py
3D : False

```

另一个例子

```py
# importing pafy
import pafy 

# url of video 
url = "https://www.youtube.com / watch?v = i6rhnSoK_gc"

# getting video
video = pafy.new(url) 

# getting all the available streams
streams = video.allstreams

# selecting one stream
stream = streams[4]

# checking if stream is 3D
value = stream.threed

# printing the value
print("3D : " + str(value))
```

**输出:**

```py
3D : False

```