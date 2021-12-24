# 使用 PyTube 下载 MP3 格式的视频

> 原文:[https://www . geesforgeks . org/download-video-in-MP3-format-using-pytube/](https://www.geeksforgeeks.org/download-video-in-mp3-format-using-pytube/)

YouTube 是世界上最常见的视频分享网站，你可以体验到一种作为黑客的情况，你想要编写一些脚本来下载视频。为此，我们向您赠送 Pytube。

*   Pytube 是一个轻量级的 Python 编写的库。它不依赖于第三方，并且力求极其安全。
*   Pytube 还简化了流水线操作，允许您为各种下载事件定义回调功能，例如进度或完成。
*   最后，pytube 还提供了一个命令行功能，允许您轻松地从终端直接流式传输视频。

为了完成我们的任务，我们将使用一些库，尤其是 python 中的 pytube。为此，我们必须导入它。要导入 pytube，我们可以根据 python 版本使用命令。

```
For Python2 : pip install pytube
For Python3 : pip3 install pytube
For pyube3 : pip install pytube3
```

要保存音频文件，我们使用操作系统模块，并使用下面给出的命令进行导入:

```
pip install os_sys
```

**程序:**

*   首先，我们需要导入所需的(pytube 和 os)模块。
*   然后我们接受用户的输入，即:YouTube 视频的链接。
*   因为，我们只需要视频中的一个音频文件，所以我们使用了过滤方法。
*   现在我们需要设置音频文件的输出路径，这将通过使用 os 模块来完成。
*   现在，我们终于可以将音频扩展更改为 MP3 并播放我们的音频了。

**实施:**

## 蟒蛇 3

```
# importing packages
from pytube import YouTube
import os

# url input from user
yt = YouTube(
    str(input("Enter the URL of the video you want to download: \n>> ")))

# extract only audio
video = yt.streams.filter(only_audio=True).first()

# check for destination to save file
print("Enter the destination (leave blank for current directory)")
destination = str(input(">> ")) or '.'

# download the file
out_file = video.download(output_path=destination)

# save the file
base, ext = os.path.splitext(out_file)
new_file = base + '.mp3'
os.rename(out_file, new_file)

# result of success
print(yt.title + " has been successfully downloaded.")
```

**输出:**

<video class="wp-video-shortcode" id="video-558641-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210216162351/Output.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20210216162351/Output.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210216162351/Output.mp4)</video>