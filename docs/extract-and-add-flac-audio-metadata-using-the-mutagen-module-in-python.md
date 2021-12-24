# 使用 Python 中的诱变剂模块提取并添加 FLAC 音频元数据

> 原文:[https://www . geesforgeks . org/extract-and-add-FLAC-audio-metadata-使用 python 中的诱变剂模块/](https://www.geeksforgeeks.org/extract-and-add-flac-audio-metadata-using-the-mutagen-module-in-python/)

音频元数据是嵌入音频文件中的信息，用于识别和标记音频文件。元数据包括艺术家、流派、专辑和曲目号等信息。这些信息对于制作音乐播放器和其他相关应用程序非常重要。流媒体平台还使用元数据根据不同的过滤器(如艺术家、流派和专辑)对音乐进行分类。

**FLAC** 是发烧友喜闻乐见的无损音频格式，其中还包含嵌入的元数据。使用 Python 中的**诱变剂**模块，您可以访问元数据，并为 FLAC 音频文件的元数据添加标签。

**安装:**该模块没有内置 Python。要安装此模块，请在终端中键入以下 pip 命令。

```
pip install mutagen
```

如果您愿意跟随，您可以使用[这个](https://drive.google.com/uc?export=download&id=1U63tcdUOq2-Qo7dLSQLLM9OlmiVkbIZ1)谷歌驱动链接来下载本文中使用的 FLAC 文件。

### 访问 FLAC 元数据:

要访问 FLAC 文件元数据，我们将使用诱变剂模块的 **FLAC()** 方法读取 FLAC 文件。然后我们将使用 **pprint()** 方法获取其元数据，并以人类可读的方式打印它。

## 蟒蛇 3

```
# Python program to illustrate the
# extraction of FLAC audio metadata
# using the mutagen module

# Importing the FLAC method
# from the mutagen module
from mutagen.flac import FLAC

# Loading a flac file
audio = FLAC("GeeksForGeeks_Music.flac")

# Printing all the metadata
print(audio.pprint())
```

**输出:**

```
FLAC, 310.31 seconds, 44100 Hz (audio/flac)
GENRE=Geek Music
TRACKNUMBER=1/1
ALBUM=GeeksForGeeks Album
TITLE=GeeksForGeeks_Music
COMMENTS=Special soundtrack for all the GFG Fans.
ARTIST=Neeraj Ranametadata:
```

您还可以在元数据中添加自己的标记和值，使用的语法与向 Python 字典添加项目时使用的语法相同。另外，请注意，可以编辑已经存在的标签值。确保在对标签进行任何更改后使用保存功能。

**示例:**

## 蟒蛇 3

```
# Python program to illustrate
# adding tags to the FLAC metadata
# using mutagen module

# Importing the FLAC method from
# the mutagen module
from mutagen.flac import FLAC

# Loading a flac file
audio = FLAC("GeeksForGeeks_Music.flac")

# Adding tags to the metadata
audio["YEAR_OF_RELEASE"] = "2020"
audio["WEBSITE"] = "geeksforgeeks.org"
audio["GEEK_SCORE"] = "9"

# Modifying existing metadata tag
audio["ARTIST"] = "GeeksForGeeks Team"

# Printing the metadata
print(audio.pprint())

# Saving the changes
audio.save()
```

**输出:**

```
FLAC, 310.31 seconds, 44100 Hz (audio/flac)
GENRE=Geek Music
TRACKNUMBER=1/1
ALBUM=Geeks
ForGeeks Album
TITLE=GeeksForGeeks_Music
COMMENTS=Special soundtrack for all the GFG Fans.
YEAR_OF_RELEASE=2020
WEBSITE=geeksforgeeks.org
GEEK_SCORE=9
ARTIST=GeeksForGeeks Team

```