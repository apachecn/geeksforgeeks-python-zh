# Pafy–获取流的原始比特率

> 原文:[https://www . geeksforgeeks . org/pafy-get-raw-bit-rate-stream/](https://www.geeksforgeeks.org/pafy-getting-raw-bit-rate-of-stream/)

在本文中，我们将了解如何在 pafy 中获取给定 youtube 视频流的原始比特率。Pafy 是一个 python 库，用于下载 YouTube 内容和检索元数据。Pafy 对象是包含给定视频所有信息的对象。在电信和计算中，比特率是单位时间内传送或处理的位数。比特率用每秒比特数来量化。比特率基本上是对于音频流对于视频流它的值是 0。原始比特率是比特率的精确值。

借助`new`方法，我们可以得到 pafy 对象，借助`allstreams`属性，我们可以得到视频可用的所有流，下面是获取给定视频的 pafy 对象的命令

```
video = pafy.new(url)
streams = video.allstreams

```

视频网址应该存在于 youtube 上，因为它获得了那些在 youtube 上出现的视频的信息。YouTube 是一个美国在线视频分享平台。

为此，我们对视频的 pafy 流对象使用`rawbitrate`属性

> **语法:**流。比特率
> 
> **论证:**不需要论证
> 
> **返回:**返回整数

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
stream = streams[1]

# getting raw bit rate of stream
value = stream.rawbitrate

# printing the value
print("Raw Bit rate : " + str(value))
```

**输出:**

```
Raw Bit rate : 71680

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

# getting raw bit rate of stream
value = stream.rawbitrate

# printing the value
print("Raw Bit rate : " + str(value))
```

**输出:**

```
Raw Bit rate : 0

```