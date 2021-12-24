# 播放列表–检查播放列表中每个项目的抄送

> 原文:[https://www . geesforgeks . org/pafy-checking-cc-for-item-of-playlist/](https://www.geeksforgeeks.org/pafy-checking-cc-for-each-item-of-playlist/)

在本文中，我们将看到如何在 pafy 中检查播放列表的项目是否是 CC。Pafy 是一个 python 库，用于下载 YouTube 内容和检索元数据。Pafy 对象是包含给定视频所有信息的对象。YouTube 中的播放列表是按顺序播放的视频列表或组，一个视频接一个视频。元数据是“提供其他数据信息的数据”。CC 代表隐藏字幕，它只是在字幕之间切换，如果你打开它，视频作者提交的或语音识别生成的字幕(更准确地说是隐藏字幕)会随着视频一起显示。

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
> 6。对元数据使用“is_cc”作为关键字，并存储和打印结果

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

# checking if it is CC
value = metadata['is_cc']

# printing value
print(value)
```

**输出:**

```
False
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

# checking if it is CC
value = metadata['is_cc']

# printing value
print(value)
```

**输出:**

```
False

```