# Pafy–创建 Pafy 对象

> 原文:[https://www.geeksforgeeks.org/pafy-creating-a-pafy-object/](https://www.geeksforgeeks.org/pafy-creating-a-pafy-object/)

在本文中，我们将看到如何创建一个 pafy 对象。Pafy 是一个 python 库，用于下载 YouTube 内容和检索元数据。Pafy 对象是包含给定视频所有信息的对象。该视频应该存在于 youtube 上，因为它获得了 youtube 上那些视频的信息。YouTube 是一个美国在线视频分享平台，总部位于加州圣布鲁诺。

为了做到这一点，我们使用`pafy.new`方法

> **语法:** pafy.new(视频)
> 
> **参数:**取 youtube 视频 url 或 11 个字符视频 id
> 
> **返回:**返回 pafy 对象

下面是实现

```
# importing pafy
import pafy 

# url of video 
url = "https://www.youtube.com / watch?v = vG2PNdI8axo"

# getting video
video = pafy.new(url) 

# printing video object
print(video)
```

**输出:**

```
Title: DSA Self Paced Course | GeeksforGeeks
Author: GeeksforGeeks
ID: vG2PNdI8axo
Duration: 00:01:06
Rating: 4.6894979
Views: 75431
Thumbnail: http://i.ytimg.com/vi/vG2PNdI8axo/default.jpg
```

另一个例子

```
# importing pafy
import pafy 

# id of video 
i_d = "vG2PNdI8axo"

# getting video through id
video = pafy.new(url) 

print(video)
```

**输出:**

```
Title: DSA Self Paced Course | GeeksforGeeks
Author: GeeksforGeeks
ID: vG2PNdI8axo
Duration: 00:01:06
Rating: 4.6894979
Views: 75431
Thumbnail: http://i.ytimg.com/vi/vG2PNdI8axo/default.jpg
```