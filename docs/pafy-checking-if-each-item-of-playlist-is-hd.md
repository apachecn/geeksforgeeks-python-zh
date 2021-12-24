# Pafy–检查播放列表的每个项目是否高清

> 原文:[https://www . geesforgeks . org/pafy-检查播放列表中的每个项目是否为 hd/](https://www.geeksforgeeks.org/pafy-checking-if-each-item-of-playlist-is-hd/)

在本文中，我们将看到如何在 pafy 中检查播放列表的每个项目是否高清。Pafy 是一个 python 库，用于下载 YouTube 内容和检索元数据。Pafy 对象是包含给定视频所有信息的对象。YouTube 中的播放列表是按顺序播放的视频列表或组，一个视频接一个视频。在 YouTube 上，高清表示视频的垂直分辨率在 720 到 1080 行之间(在 YouTube 播放器的质量设置中显示为 720p 或 1080p)，而标清通常为 360 或 480 行。

借助`get_playlist`方法，我们可以在 pafy 中从 youtube 获取播放列表，下面是这样做的命令

```py
 pafy.get_playlist(url)
```

播放列表的网址应该存在于 youtube 上，因为它获取了 youtube 上那些视频的信息。YouTube 是一个美国在线视频分享平台。

> 实施步骤
> 1。导入 pafy 模块
> 2。借助播放列表
> 3 的网址获取播放列表。返回播放列表作为字典工作，因此在返回播放列表
> 4 中使用“项目”作为关键字。将结果存储在变量中，并从项目中选择单个项目
> 5。对于单个项目，使用“playlist_meta”键获取元数据
> 6。对于元数据，使用“是高清”键，当项目在高清模式下可用时，该键将返回真

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

# getting meta data
metadata = item['playlist_meta']

# checking if item is HD
value = metadata['is_hd']

# printing value
print(value)
```

**输出:**

```py
True
```

另一个例子

```py
# importing pafy
import pafy 

# url of playlist
url = "https://www.youtube.com / playlist?list = PLqM7alHXFySE71A2bQdYp37vYr0aReknt"

# getting playlist
playlist = pafy.get_playlist(url)

# getting playlist items
items = playlist["items"]

# selecting single item
item = items[2]

# getting meta data
metadata = item['playlist_meta']

# checking if item is HD
value = metadata['is_hd']

# printing value
print(value)
```

**输出:**

```py
True

```