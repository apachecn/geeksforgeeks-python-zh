# Pafy–获取播放列表标题

> 原文:[https://www.geeksforgeeks.org/pafy-getting-playlist-title/](https://www.geeksforgeeks.org/pafy-getting-playlist-title/)

在本文中，我们将看到如何在 pafy 中获得 youtube 播放列表标题。Pafy 是一个 python 库，用于下载 YouTube 内容和检索元数据。Pafy 对象是包含给定视频所有信息的对象。YouTube 中的播放列表是按顺序播放的视频列表或组，一个视频接一个视频。当一个视频结束播放时，下一个视频会自动开始播放，因此您不必单击或搜索来开始播放新视频。播放列表的标题是播放列表中所有视频的大致标题

借助`get_playlist`方法，我们可以在 pafy 中从 youtube 获取播放列表，下面是这样做的命令

```
 pafy.get_playlist(url)
```

播放列表的网址应该存在于 youtube 上，因为它获取了 youtube 上那些视频的信息。YouTube 是一个美国在线视频分享平台。

> 获取播放列表标识的步骤
> 1。导入 pafy 模块
> 2。借助播放列表
> 3 的网址获取播放列表。返回播放列表作为字典工作，因此在返回播放列表
> 4 中使用“标题”作为关键字。将结果存储在变量中并打印出来

下面是实现

```
# importing pafy
import pafy 

# url of playlist
url = "https://www.youtube.com / playlist?list = PLqM7alHXFySGqCvcwfqqMrteqWukz9ZoE"

# getting playlist
playlist = pafy.get_playlist(url)

# pgetting playlist title
title = playlist["title"]

# printing title
print("Title : " + title) 
```

**输出:**

```
Title : Amazon Programming Interview Questions | GeeksforGeeks
```

另一个例子

```
# importing pafy
import pafy 

# url of playlist
url = "https://www.youtube.com / playlist?list = PLqM7alHXFySE71A2bQdYp37vYr0aReknt"

# getting playlist
playlist = pafy.get_playlist(url)

# pgetting playlist title
title = playlist["title"]

# printing title
print("Title : " + title) 
```

**输出:**

```
Title : Google Programming Interview Questions
```