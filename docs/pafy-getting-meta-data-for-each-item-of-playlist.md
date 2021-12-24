# Pafy–获取播放列表每一项的元数据

> 原文:[https://www . geeksforgeeks . org/pafy-get-meta-data-for-item-of-playlist/](https://www.geeksforgeeks.org/pafy-getting-meta-data-for-each-item-of-playlist/)

在本文中，我们将看到如何在 pafy 中获取播放列表每一项的元数据。Pafy 是一个 python 库，用于下载 YouTube 内容和检索元数据。Pafy 对象是包含给定视频所有信息的对象。YouTube 中的播放列表是按顺序播放的视频列表或组，一个视频接一个视频。元数据是“提供其他数据信息的数据”。换句话说，它是“关于数据的数据”存在许多不同类型的元数据，包括描述性元数据、结构性元数据、管理元数据、参考元数据和统计元数据。

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
> 5。单个项目使用“playlist_meta”键
> 6。将结果存储在变量中并保存。

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

# printing meta data
print(metadata)
```

**输出:**

```py
{'added': '06/01/2016', 'is_cc': False, 'is_hd': True, 'likes': 1111, 'title': 'Write a program to print all permutations of a given string | GeeksforGeeks', 'views': '334, 905', 'rating': 4.0, 'author': 'GeeksforGeeks', 'user_id': '0RhatS1pyxInC00YKjjBqQ', 'privacy': 'public', 'start': 0.0, 'dislikes': 227, 'duration': '11:52', 'comments': '116', 'keywords': '', 'thumbnail': 'https://i.ytimg.com/vi/AfxHGNRtFac/default.jpg', 'cc_license': False, 'category_id': 22, 'description': 'Explanation for the Article: https://www.geeksforgeeks.org/write-a-c-program-to-print-all-permutations-of-a-given-string/\n\nThis video is contributed by Sephiri.\n#geeksforgeeks', 'encrypted_id': 'AfxHGNRtFac', 'time_created': 1490874673, 'time_updated': None, 'length_seconds': 712, 'end': 712}
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

# printing meta data
print(metadata)
```

**输出:**

```py
{'added': '27/09/2017', 'is_cc': True, 'is_hd': True, 'likes': 192, 'title': 'Find subarray with given sum | Set 1 (Non-negative Numbers) | GeeksforGeeks', 'views': '32, 716', 'rating': 3.0, 'author': 'GeeksforGeeks', 'user_id': '0RhatS1pyxInC00YKjjBqQ', 'privacy': 'public', 'start': 0.0, 'dislikes': 78, 'duration': '2:50', 'comments': '24', 'keywords': 'GeeksforGeeks Programming Algorithms "Data Structures" Coding Tutorial array "non-negative numbers"', 'thumbnail': 'https://i.ytimg.com/vi/GY-KULykGaw/default.jpg', 'cc_license': False, 'category_id': 27, 'description': "Find Complete Code at GeeksforGeeks Article: https://www.geeksforgeeks.org/find-subarray-with-given-sum/\n\nPractice Problem Online Judge: http://practice.geeksforgeeks.org/problems/subarray-with-given-sum/0\n\nThis video is contributed by Shubham Kumar\n\nPlease Like, Comment and Share the Video among your friends.\n\nAlso, Subscribe if you haven't already! :)", 'encrypted_id': 'GY-KULykGaw', 'time_created': 1506577926, 'time_updated': None, 'length_seconds': 170, 'end': 170}

```