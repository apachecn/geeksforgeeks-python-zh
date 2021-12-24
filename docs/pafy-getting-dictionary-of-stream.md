# Pafy–获取流字典

> 原文:[https://www . geesforgeks . org/pafy-get-dictionary-of-stream/](https://www.geeksforgeeks.org/pafy-getting-dictionary-of-stream/)

在本文中，我们将看到如何在 pafy 中获取给定 youtube 视频流的流字典。Pafy 是一个 python 库，用于下载 YouTube 内容和检索元数据。Pafy 对象是包含给定视频所有信息的对象。流基本上是可用的分辨率的视频是可以在 youtube 上获得的。讨论由信息流的所有信息组成。

借助`new`方法，我们可以得到 pafy 对象，借助`allstreams`属性，我们可以得到视频可用的所有流，下面是获取给定视频的 pafy 对象的命令

```
video = pafy.new(url)
streams = video.allstreams

```

视频网址应该存在于 youtube 上，因为它获得了那些在 youtube 上出现的视频的信息。YouTube 是一个美国在线视频分享平台。

为此，我们对视频的 pafy 对象使用`__dict__`属性

> **语法:**视频。__dict__
> 
> **论证:**不需要论证
> 
> **返回:**返回字典

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

# selecting one stream
stream = streams[2]

# getting dictionary of the stream
value = stream.__dict__

# printing the value
print(value)
```

**输出:**

```
{'_itag': '140', '_mediatype': 'audio', '_threed': False, '_rawbitrate': 131072, '_resolution': '0x0', '_quality': '128k', '_dimensions': (0, 0), '_bitrate': '128k

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

# selecting one stream
stream = streams[4]

# getting dictionary of the stream
value = stream.__dict__

# printing the value
print(value)
```

**输出:**

```
{'_itag': '278', '_mediatype': 'video', '_threed': False, '_rawbitrate': 0, '_resolution': '256x144', '_quality': '256x144', '_dimensions': (256, 144), '_bitrate': '0k', '_extension': 'webm', 'encrypted': None, '_notes':.....

```