# Pafy–获取播放列表每一项的描述

> 原文:[https://www . geeksforgeeks . org/pafy-get-description-for-item-of-playlist/](https://www.geeksforgeeks.org/pafy-getting-description-for-each-item-of-playlist/)

在本文中，我们将看到如何在 pafy 中获得播放列表的每个项目的描述。Pafy 是一个 python 库，用于下载 YouTube 内容和检索元数据。Pafy 对象是包含给定视频所有信息的对象。YouTube 中的播放列表是按顺序播放的视频列表或组，一个视频接一个视频。项目的描述是给出关于播放列表的给定项目的信息的文本。

借助`get_playlist`方法，我们可以在 pafy 中从 youtube 获取播放列表，下面是这样做的命令

```
 pafy.get_playlist(url)
```

播放列表的网址应该存在于 youtube 上，因为它获取了 youtube 上那些视频的信息。YouTube 是一个美国在线视频分享平台。

> 实施步骤
> 1。导入 pafy 模块
> 2。借助播放列表
> 3 的网址获取播放列表。返回播放列表作为字典工作，因此在返回播放列表
> 4 中使用“项目”作为关键字。将结果存储在变量中，并从项目中选择单个项目
> 5。对于单个项目，使用“playlist_meta”键获取元数据
> 6。对于元数据，使用“描述”键，这将返回给定项目的描述

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

# getting description of item
value = metadata['description']

# printing value
print("Description : " + str(value))
```

**输出:**

```
Description : Explanation for the Article: https://www.geeksforgeeks.org/write-a-c-program-to-print-all-permutations-of-a-given-string/

This video is contributed by Sephiri.
#geeksforgeeks
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

# getting description of item
value = metadata['description']

# printing value
print("Description : " + str(value))
```

**输出:**

```
Description : Find Complete Code at GeeksforGeeks Article: https://www.geeksforgeeks.org/find-subarray-with-given-sum/

Practice Problem Online Judge: http://practice.geeksforgeeks.org/problems/subarray-with-given-sum/0

This video is contributed by Shubham Kumar

Please Like, Comment and Share the Video among your friends.

Also, Subscribe if you haven't already! :)

```