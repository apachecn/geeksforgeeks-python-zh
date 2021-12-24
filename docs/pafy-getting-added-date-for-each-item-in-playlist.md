# Pafy–获取播放列表中每个项目的添加日期

> 原文:[https://www . geesforgeks . org/pafy-获得添加日期-播放列表中的每个项目/](https://www.geeksforgeeks.org/pafy-getting-added-date-for-each-item-in-playlist/)

在本文中，我们将看到如何在 pafy 中获取播放列表中每一项的添加日期。Pafy 是一个 python 库，用于下载 YouTube 内容和检索元数据。Pafy 对象是包含给定视频所有信息的对象。YouTube 中的播放列表是按顺序播放的视频列表或组，一个视频接一个视频。元数据是“提供其他数据信息的数据”。添加日期是播放列表所有者在播放列表中添加项目的日期。

借助`get_playlist`方法，我们可以在 pafy 中从 youtube 获取播放列表，下面是这样做的命令

```
 pafy.get_playlist(url)
```

播放列表的网址应该存在于 youtube 上，因为它获取了 youtube 上那些视频的信息。YouTube 是一个美国在线视频分享平台。

> 获取播放列表标识的步骤
> 1。导入 pafy 模块
> 2。借助播放列表
> 3 的网址获取播放列表。返回播放列表作为字典工作，因此在返回播放列表
> 4 中使用“项目”作为关键字。将结果存储在变量中，并从项目中选择单个项目
> 5。单个项目使用“playlist_meta”键
> 6。将“添加”作为元数据的关键字，存储结果并打印出来

下面是实现

```
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

# getting added date
date = metadata['added']

# printing date
print(date)
```

**输出:**

```
06/01/2016
```

另一个例子

```
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

# getting added date
date = metadata['added']

# printing date
print(date)
```

**输出:**

```
27/09/2017

```