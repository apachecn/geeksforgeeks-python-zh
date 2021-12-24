# Pafy–获取播放列表每个项目的观看网址

> 原文:[https://www . geesforgeks . org/pafy-get-watch-URL-for-item-of-playlist/](https://www.geeksforgeeks.org/pafy-getting-watch-url-for-each-item-of-playlist/)

在本文中，我们将看到如何在 pafy 中从播放列表项目中获取观看 URL。Pafy 是一个 python 库，用于下载 YouTube 内容和检索元数据。Pafy 对象是包含给定视频所有信息的对象。YouTube 中的播放列表是按顺序播放的视频列表或组，一个视频接一个视频。观看网址基本上是 youtube 每个项目的实际网址，即每个播放列表视频。

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
> 6。对这个 pafy 对象使用 watchv_url 属性来获取 url

为了做到这一点，我们对播放列表项目的 pafy 对象使用`watchv_url`属性

> **语法:** playlist_pafy.watchv_url
> 
> **论证:**不需要论证
> 
> **返回:**返回字符串

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

# getting watch url
y_url = i_pafy.watchv_url

# printing url
print(y_url)
```

**输出:**

```py
http://www.youtube.com/watch?v=AfxHGNRtFac
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
item = items[1]

# getting pafy object
i_pafy = item['pafy']

# getting watch url
y_url = i_pafy.watchv_url

# printing url
print(y_url)
```

**输出:**

```py
http://www.youtube.com/watch?v=WdgAKCnWnwA
```