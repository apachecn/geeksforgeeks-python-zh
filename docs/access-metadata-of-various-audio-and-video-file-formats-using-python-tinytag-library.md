# 使用 Python–tinytag 库访问各种音视频文件格式的元数据

> 原文:[https://www . geesforgeks . org/access-各种音频和视频文件格式的元数据-使用-python-tinytag-library/](https://www.geeksforgeeks.org/access-metadata-of-various-audio-and-video-file-formats-using-python-tinytag-library/)

元数据提取是制作音乐播放器或其他相关应用程序的必要任务。读取各种音视频文件格式的音乐元数据最好的 python 库是 **tinytag** 。该库允许您访问各种音频和视频文件格式的元数据，如 mp3、m4a、mp4、flac、wav 等。

您可以访问的属性列表包括专辑、专辑艺术家、艺术家、音频偏移量、比特率、评论、作曲家、光盘、光盘总数、持续时间、文件大小、流派、采样率、标题、轨道、轨道总数和年份。请注意，您只能读取元数据，不能编辑元数据。

### 安装:

这个模块没有内置 Python。要安装此模块，请在终端中键入以下命令。

```
pip install tinytag

```

这个库支持 python 2.7+和 3.4+以及 pypy。

### 元数据提取

首先，从 tinytag 库中导入 Tinytag 方法。然后，将文件名传递给 Tinytag.get()方法(如果它存在于同一个目录中)，如果不存在，则传递完整路径并将其分配给任何变量。现在，可以使用以下格式访问这些属性:variable_name.attribute_name。

您可以使用返回布尔值的方法*TinyTag . is _ supported(filename)*来检查您正在使用的文件格式是否受支持。

**注意:**缺失的元数据将显示为无

如果您愿意，本文使用的音频和视频文件的下载链接如下: [m4a](https://drive.google.com/uc?export=download&id=1jNXkVnEJMdpqh4_V3WmpGjJS90yaDtqa) (音频)和 [mp4](https://drive.google.com/uc?export=download&id=16Dnz0yXYP-tU_cHHy1zjjAb7w0-cC71V) (视频)。

**例 1(音频):**

## 蟒 3

```
# Python3 program to illustrate
# accessing of audio metadata
# using tinytag library

# Import Tinytag method from
# tinytag library
from tinytag import TinyTag

# Pass the filename into the
# Tinytag.get() method and store
# the result in audio variable
audio = TinyTag.get("GeeksForGeeks_Audio.m4a")

# Use the attributes
# and Display
print("Title:" + audio.title)
print("Artist: " + audio.artist)
print("Genre:" + audio.genre)
print("Year Released: " + audio.year)
print("Bitrate:" + str(audio.bitrate) + " kBits/s")
print("Composer: " + audio.composer)
print("Filesize: " + str(audio.filesize) + " bytes")
print("AlbumArtist: " + audio.albumartist)
print("Duration: " + str(audio.duration) + " seconds")
print("TrackTotal: " + str(audio.track_total))
```

**输出:**

```
Title:GeeksForGeeks_Audio
Artist: Neeraj Rana/GFG
Genre:Geek Music
Year Released: 2020
Bitrate:182.72 kBits/s
Composer: GeeksForGeeks Team
Filesize: 63076 bytes
AlbumArtist: Voice Recorder
Duration: 2.7306458333333334 seconds
TrackTotal: None

```

**例 2(视频):**

## 蟒 3

```
# Python3 program to illustrate
# accessing of video metadata
# using tinytag library

# Import Tinytag method from
# tinytag library
from tinytag import TinyTag

# Pass the filename into the
# Tinytag.get() method and store
# the result in audio variable
video = TinyTag.get("GeeksForGeeks_Video.mp4")

# Use the attributes
# and display
print("Title:" + video.title)
print("Artist: " + video.artist)
print("Genre:" + video.genre)
print("Year Released: " + video.year)
print("Bitrate:" + str(video.bitrate) + " kBits/s")
print("Composer: " + video.composer)
print("Filesize: " + str(video.filesize) + " bytes")
print("AlbumArtist: " + str(video.albumartist))
print("Duration: " + str(video.duration) + " seconds")
print("TrackTotal: " + str(video.track_total))
```

**输出:**

```
Title:GeeksForGeeks_Video
Artist: Neeraj Rana/GFG
Genre:Geek Video
Year Released: 2020
Bitrate:294651.393 kBits/s
Composer: GFG Video Team
Filesize: 511940 bytes
AlbumArtist: None
Duration: 1.8239333333333334 seconds
TrackTotal: None

```

如果遇到任何类型错误，可以使用类型转换。