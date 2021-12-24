# Pafy–生成流的文件名

> 原文:[https://www . geesforgeks . org/pafy-gen rating-file-name-of-stream/](https://www.geeksforgeeks.org/pafy-genrating-file-name-of-stream/)

在本文中，我们将看到如何在 pafy 中生成给定 youtube 视频流的文件名。Pafy 是一个 python 库，用于下载 YouTube 内容和检索元数据。Pafy 对象是包含给定视频所有信息的对象。流基本上是可用的分辨率的视频是可以在 youtube 上获得的。文件名是流文件的标题。
我们可以借助新方法获得 pafy 对象，借助 allstreams 属性我们可以获得视频可用的所有流，下面是获取给定视频的 pafy 对象的命令

```py
video = pafy.new(url)
streams = video.allstreams
```

视频网址应该存在于 youtube 上，因为它获得了那些在 youtube 上出现的视频的信息。YouTube 是一个美国在线视频分享平台。
为了做到这一点，我们对视频的流对象使用 generate_filename 方法

> **语法:**stream . generate _ filename()
> **参数:**不需要参数
> **返回:**返回字符串

下面是实现

## 蟒蛇 3

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

# generating file name
value = stream.generate_filename()

# printing the value
print("Generated File Name : " + str(value))
```

**输出:**

```py
Generated File Name : DSA Self Paced Course _ GeeksforGeeks.webm
```

另一个例子

## 蟒蛇 3

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
# generating file name
value = stream.generate_filename()

# printing the value
print("Generated File Name : " + str(value))
```

**输出:**

```py
Generated File Name : COVID CASE IN OUR BUILDING - VLOG 32.webm
```