# Pafy–为播放列表的每个项目获取 Pafy 对象

> 原文:[https://www . geeksforgeeks . org/pafy-get-pafy-播放列表中每个项目的对象/](https://www.geeksforgeeks.org/pafy-getting-pafy-object-for-each-item-of-playlist/)

在本文中，我们将看到如何从 pafy 中的播放列表项中获取 pafy 对象。Pafy 是一个 python 库，用于下载 YouTube 内容和检索元数据。Pafy 对象是包含给定视频所有信息的对象。YouTube 中的播放列表是按顺序播放的视频列表或组，一个视频接一个视频。当一个视频结束播放时，下一个视频会自动开始播放，因此您不必单击或搜索来开始播放新视频。播放列表项目是单个视频总项目是播放列表中存在的总视频。使用 pafy 对象，我们可以下载选定的视频，获得视频质量。

借助`get_playlist`方法，我们可以在 pafy 中从 youtube 获取播放列表，下面是这样做的命令

```py
 pafy.get_playlist(url)
```

播放列表的网址应该存在于 youtube 上，因为它获取了 youtube 上那些视频的信息。YouTube 是一个美国在线视频分享平台。

> 获取播放列表标识的步骤
> 1。导入 pafy 模块
> 2。借助播放列表
> 3 的网址获取播放列表。返回播放列表作为字典工作，因此在返回播放列表
> 4 中使用“项目”作为关键字。将结果存储在变量中，并从项目中选择单个项目
> 5。单项使用' pafy '键
> 6。存储结果并打印结果

下面是实现

```py
# importing pafy
import pafy 

# url of playlist
url = "https://www.youtube.com / playlist?list = PLqM7alHXFySGqCvcwfqqMrteqWukz9ZoE"

# getting playlist
playlist = pafy.get_playlist(url)

# getting playlist items
items = playlist["items"]

# selecting single item
item = items[1]

# getting pafy object
i_pafy = item['pafy']

# printing pafy object
print(i_pafy) 
```

**输出:**

```py
Pafy object: AfxHGNRtFac [Write a program to print all permutations of ..]
```

另一个例子

```py
# importing pafy
import pafy 

# url of playlist
url = "https://www.youtube.com / playlist?list = PLqM7alHXFySE71A2bQdYp37vYr0aReknt"

# getting playlist
playlist = pafy.get_playlist(url)

# selecting single item
item = items[1]

# getting pafy object
i_pafy = item['pafy']

# printing pafy object
print(i_pafy)
```

**输出:**

```py
Pafy object: WdgAKCnWnwA [Merge Overlapping Intervals | GeeksforGeeks..]

```