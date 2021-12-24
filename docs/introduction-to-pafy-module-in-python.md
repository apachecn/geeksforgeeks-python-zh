# Python 中 Pafy 模块介绍

> 原文:[https://www . geesforgeks . org/introduction-to-pafy-module-in-python/](https://www.geeksforgeeks.org/introduction-to-pafy-module-in-python/)

在本文中，我们将了解 pafy 模块。 **Pafy** 是一个下载 YouTube 内容和检索元数据的 Python 库。

> **以下是 Pafy 提供的功能列表**
> 1。检索元数据，如浏览量，持续时间，评级，作者，缩略图，关键词
> 2。以要求的分辨率/比特率/格式/文件大小下载视频或音频
> 2。命令行工具(ytdl)用于直接从命令行下载
> 3。检索网址，在 vlc 或 mplayer 等播放器中播放视频
> 4。处理年龄限制视频和不可嵌入视频
> 5。小型、独立、单一可导入模块文件
> 6。选择最高质量的流进行下载或流式传输
> 7。仅下载 m4v 或 webm 格式的视频(无音频)
> 8。仅下载 ogg 或 m4a 格式的音频(无视频)
> 9。检索播放列表和播放列表元数据
> 10。适用于 Python 2.6+和 3.3+

**安装**
为了安装 pafy，我们使用下面给出的命令

```py
pip install pafy
```

**注意:** Pafy 可选地依赖于 youtube-dl，因此为了更稳定的使用，建议在安装 Pafy 之前安装 youtube-dl。下面是安装 youtube-dl 的命令

```py
pip install youtube_dl
```

**示例 1:**
获取视频浏览量的程序

## 蟒蛇 3

```py
# importing pafy
import pafy

# url of video
url = "https://www.youtube.com / watch?v = mmjDZGSr7EA"

# instant created
video = pafy.new(url)

# getting number of likes
count = video.viewcount

# showing likes
print("View Count : " + str(count))
```

**输出:**

```py
View Count : 287205
```

**示例 2:**
获取视频拇指图像的程序

## 蟒蛇 3

```py
# importing pafy
import pafy

# url of video
url = "https://www.youtube.com / watch?v = mmjDZGSr7EA"

# instant created
video = pafy.new(url)

# getting thumb image
count = video.thumb

# showing likes
print("Thumb Image : " + str(count))
```

**输出:**

```py
Thumb Image : http://i.ytimg.com/vi/vG2PNdI8axo/default.jpg
```

**示例 3:**
获取视频标题的程序

## 蟒蛇 3

```py
# importing pafy
import pafy

# url of video
url = "https://www.youtube.com / watch?v = vG2PNdI8axo"

# instant created
video = pafy.new(url)

# getting title
value = video.title

# showing likes
print("Title : " + str(value))
```

**输出:**

```py
Title : DSA Self Paced Course | GeeksforGeeks
```