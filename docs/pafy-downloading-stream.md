# Pafy–下载流

> 原文:[https://www.geeksforgeeks.org/pafy-downloading-stream/](https://www.geeksforgeeks.org/pafy-downloading-stream/)

在本文中，我们将看到如何在 pafy 中下载给定的 youtube 视频流。Pafy 是一个 python 库，用于下载 YouTube 内容和检索元数据。Pafy 对象是包含给定视频所有信息的对象。流基本上是可用的分辨率的视频是可以在 youtube 上获得的。下载的文件保存在程序文件夹中。

借助`new`方法，我们可以得到 pafy 对象，借助`allstreams`属性，我们可以得到视频可用的所有流，下面是获取给定视频的 pafy 对象的命令

```py
video = pafy.new(url)
streams = video.allstreams

```

视频网址应该存在于 youtube 上，因为它获得了那些在 youtube 上出现的视频的信息。YouTube 是一个美国在线视频分享平台。

为此，我们对视频流对象使用`download`方法

> **语法:** stream.download()
> 
> **论证:**不需要论证
> 
> **返回:**返回无

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

# downloading stream
stream.download()
```

**输出:**

```py
 554, 085.0 Bytes [100.00%] received. Rate: [7396 KB/s].  ETA: [0 secs]    

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

# downloading stream
stream.download()
```

**输出:**

```py
8, 125, 774.0 Bytes [100.00%] received. Rate: [15493 KB/s].  ETA: [0 secs]    

```