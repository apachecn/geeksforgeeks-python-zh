# Pafy–获取流的弱引用

> 原文:[https://www . geeksforgeeks . org/pafy-get-weak-reference-of-stream/](https://www.geeksforgeeks.org/pafy-getting-weak-reference-of-stream/)

在这篇文章中，我们将看到如何在 pafy 中为给定的 youtube 视频流获取弱引用。Pafy 是一个 python 库，用于下载 YouTube 内容和检索元数据。Pafy 对象是包含给定视频所有信息的对象。流基本上是可用的分辨率的视频是可以在 youtube 上获得的。弱引用对象在弱可达时被垃圾收集器清除。弱可达性意味着一个对象既没有强引用也没有软引用指向它。只有通过遍历弱引用才能到达该对象。

我们可以在新方法的帮助下获得 pafy 对象，在 allstreams 属性的帮助下，我们可以获得视频的所有可用流，下面是获取给定视频的 pafy 对象的命令。

```
video = pafy.new(url)
streams = video.allstreams
```

视频网址应该存在于 youtube 上，因为它获得了那些在 youtube 上出现的视频的信息。YouTube 是一个美国在线视频分享平台。

为此，我们对视频的 pafy 对象使用 __weakref__ 属性

> **语法:**视频。__weakref__
> 
> **论证:**不需要论证
> 
> **返回:**返回列表

下面是实现

## 蟒蛇 3

```
# importing pafy
import pafy

# url of video
url = "https://www.youtube.com / watch?v = vG2PNdI8axo"

# getting video
video = pafy.new(url)

# getting all the available streams
streams = video.allstreams

# selecting one stream
stream = streams[2]

# getting weak reference of the stream
value = stream.__weakref__

# printing the value
print(value)
```

**输出:**

```
None
```

另一个例子

## 蟒蛇 3

```
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

# getting weak reference of the stream
value = stream.__weakref__

# printing the value
print(value)
```

**输出:**

```
None
```