# 播放列表–从播放列表中填充每个项目

> 原文:[https://www . geeksforgeeks . org/pafy-从播放列表中获取每个项目的填充/](https://www.geeksforgeeks.org/pafy-getting-populate-of-each-item-from-playlist/)

在本文中，我们将看到如何在 pafy 中将项目填充到播放列表中。Pafy 是一个 python 库，用于下载 YouTube 内容和检索元数据。Pafy 对象是包含给定视频所有信息的对象。YouTube 中的播放列表是按顺序播放的视频列表或组，一个视频接一个视频。填充意味着填写播放列表。

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
> 5。单项使用' pafy '键
> 6。使用此 pafy 对象填充播放列表属性

为了做到这一点，我们对播放列表项目的 pafy 对象使用`populate_from_playlist`属性

> **语法:**playlist _ pafy . populate _ from _ playlist
> 
> **论证:**不需要论证
> 
> **返回:**返回字符串

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

# populating to playlist
value = i_pafy.populate_from_playlist

# printing value
print(value)
```

**输出:**

```
bound method BasePafy.populate_from_playlist of Pafy object: AfxHGNRtFac [Write a program to print all permutations of ..]
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
item = items[1]

# getting pafy object
i_pafy = item['pafy']

# populating to playlist
value = i_pafy.populate_from_playlist

# printing value
print(value)
```

**输出:**

```
bound method BasePafy.populate_from_playlist of Pafy object: WdgAKCnWnwA [Merge Overlapping Intervals | GeeksforGeeks..]

```