# Pafy–获取流的元数据

> 原文:[https://www . geeksforgeeks . org/pafy-get-meta-data-of-stream/](https://www.geeksforgeeks.org/pafy-getting-meta-data-of-stream/)

在本文中，我们将看到如何在 pafy 中获取给定 youtube 视频流的元数据。Pafy 是一个 python 库，用于下载 YouTube 内容和检索元数据。Pafy 对象是包含给定视频所有信息的对象。流基本上是可用的分辨率的视频是可以在 youtube 上获得的。元数据是“提供其他数据信息的数据”。换句话说，它是“关于数据的数据”存在许多不同类型的元数据，包括描述性元数据、结构性元数据、管理元数据、参考元数据和统计元数据

借助`new`方法，我们可以得到 pafy 对象，借助`allstreams`属性，我们可以得到视频可用的所有流，下面是获取给定视频的 pafy 对象的命令

```
video = pafy.new(url)
streams = video.allstreams

```

视频网址应该存在于 youtube 上，因为它获得了那些在 youtube 上出现的视频的信息。YouTube 是一个美国在线视频分享平台。

为此，我们对视频流对象使用`__repr__`方法

> **语法:**流。__repr__()
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

# getting all the available streams
streams = video.allstreams

# getting meta data of stream
value = stream.__repr__()

# printing the value
print("Meta Data : " + str(value))
```

**输出:**

```
Meta Data : audio:webm@70k 

```

另一个例子

```
# importing pafy
import pafy 

# url of video 
url = "https://www.youtube.com / watch?v = i6rhnSoK_gc"

# getting video
video = pafy.new(url) 

# getting all the available streams
streams = video.allstreams

# getting meta data of stream
value = stream.__repr__()

# printing the value
print("Meta Data : " + str(value))
```

**输出:**

```
Meta Data : video:webm@256x144

```