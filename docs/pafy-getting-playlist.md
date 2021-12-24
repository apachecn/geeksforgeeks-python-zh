# Pafy–获取播放列表

> 原文:[https://www.geeksforgeeks.org/pafy-getting-playlist/](https://www.geeksforgeeks.org/pafy-getting-playlist/)

在本文中，我们将看到如何在 pafy 中获得 youtube 播放列表。Pafy 是一个 python 库，用于下载 YouTube 内容和检索元数据。Pafy 对象是包含给定视频所有信息的对象。YouTube 中的播放列表是按顺序播放的视频列表或组，一个视频接一个视频。当一个视频结束播放时，下一个视频会自动开始播放，因此您不必单击或搜索来开始播放新视频。

播放列表的网址应该存在于 youtube 上，因为它获取了 youtube 上那些视频的信息。YouTube 是一个美国在线视频分享平台。

为了做到这一点，我们使用`pafy.get_playlist`方法

> **语法:** pafy.get_playlist(url)
> 
> **参数:**以播放列表的网址为参数
> 
> **返回:**返回字典

下面是实现

```
# importing pafy
import pafy 

# url of playlist
url = "https://www.youtube.com / playlist?list = PLqM7alHXFySGqCvcwfqqMrteqWukz9ZoE"

# getting playlist
playlist = pafy.get_playlist(url)

# prinintg playlist
print(playlist["title"])
```

**输出:**

```
Amazon Programming Interview Questions | GeeksforGeeks

```

另一个例子

```
# importing pafy
import pafy 

# url of playlist
url = "https://www.youtube.com / playlist?list = PLqM7alHXFySE71A2bQdYp37vYr0aReknt"

# getting playlist
playlist = pafy.get_playlist(url)

# prinintg playlist
print(playlist["title"])
```

**输出:**

```
Google Programming Interview Questions4

```