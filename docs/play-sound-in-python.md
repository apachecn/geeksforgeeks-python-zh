# 用 Python 播放声音

> 原文:[https://www.geeksforgeeks.org/play-sound-in-python/](https://www.geeksforgeeks.org/play-sound-in-python/)

在本文中，我们将看到如何使用一些最流行的音频库在 Python 中播放声音。我们将学习播放声音的各种方法。

**方法 1:** 使用*播放声音*模块

运行以下命令安装软件包:

```py
pip install playsound
```

*   *playsound* 模块只包含一个名为 **playsound()** 的功能。
*   它需要一个参数:我们必须播放的声音文件的路径。可以是*本地文件*，也可以是*网址*。
*   还有一个可选的第二个参数**阻止**，默认设置为*真*。我们可以将其设置为*假*，使功能异步运行**。**
*   **它适用于 **WAV** 和 **MP3** 文件。**

****示例:**对于 WAV 格式**

## **蟒蛇 3**

```py
# import required module
from playsound import playsound

# for playing note.wav file
playsound('/path/note.wav')
print('playing sound using  playsound')
```

****输出:****

**<video class="wp-video-shortcode" id="video-536240-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210102134813/gfgplaysound.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20210102134813/gfgplaysound.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210102134813/gfgplaysound.mp4)</video>**

****示例:**对于 mp3 格式**

## **蟒蛇 3**

```py
# import required module
from playsound import playsound

# for playing note.mp3 file
playsound('/path/note.mp3')
print('playing sound using  playsound')
```

****输出:****

**<video class="wp-video-shortcode" id="video-536240-2" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210102134813/gfgplaysound.mp4?_=2">[https://media.geeksforgeeks.org/wp-content/uploads/20210102134813/gfgplaysound.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210102134813/gfgplaysound.mp4)</video>**

****方法 2:** 使用 *pydub* 模块**

**运行以下命令来安装软件包:**

```py
sudo apt-get install ffmpeg libavcodec-extra
pip install pydub
```

****注意:**可以用 python 打开 WAV 文件。打开 mp3，你需要 [ffmpeg](http://www.ffmpeg.org/) 或 [libav](http://libav.org/) **。****

**本模块使用 **from_wav()** 方法播放 wav 文件，使用 **from_mp3()** 方法播放 mp3 文件。 **play()** 方法用于播放 wav 和 mp3 文件:**

****示例 1:** 对于 WAV 格式**

## **蟒蛇 3**

```py
# import required modules
from pydub import AudioSegment
from pydub.playback import play

# for playing wav file
song = AudioSegment.from_wav("note.wav")
print('playing sound using  pydub')
play(song)
```

****输出:****

**<video class="wp-video-shortcode" id="video-536240-3" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210102134814/gfgpydub.mp4?_=3">[https://media.geeksforgeeks.org/wp-content/uploads/20210102134814/gfgpydub.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210102134814/gfgpydub.mp4)</video>**

****示例 2:** 对于 mp3 格式**

## **蟒蛇 3**

```py
# import required module
from pydub import AudioSegment
from pydub.playback import play

# for playing mp3 file
song = AudioSegment.from_mp3("note.mp3")
print('playing sound using  pydub')
play(song)
```

****输出:****

**<video class="wp-video-shortcode" id="video-536240-4" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210102134814/gfgpydub.mp4?_=4">[https://media.geeksforgeeks.org/wp-content/uploads/20210102134814/gfgpydub.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210102134814/gfgpydub.mp4)</video>**

****方法 3:** 使用*tk 小吃*模块**

****tk 小吃**模块依赖于一个名为 **tkinter** 的模块来激活 python 脚本中的一个 **tk** 对象。您必须为 Python 安装 **tkinker** 和**tk 小吃**包。运行以下命令来安装软件包:**

```py
sudo apt-get install python3-tk
sudo apt-get install python3-tksnack
```

****播放()**方法用于播放音频文件。**阻塞**论点声明声音将异步播放**。****

******示例:******

## ****蟒蛇 3****

```py
**# import required modules
from Tkinter import *
import tkSnack

# initialize tk object to use tksnack
root = Tk()
tkSnack.initializeSnack(root)

# play sound
snd = tkSnack.Sound()
snd.read('note.wav')
print('playing sound using tkSnack')
snd.play(blocking=1)**
```

******输出:******

****<video class="wp-video-shortcode" id="video-536240-5" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210102134818/gfgtksnack.mp4?_=5">[https://media.geeksforgeeks.org/wp-content/uploads/20210102134818/gfgtksnack.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210102134818/gfgtksnack.mp4)</video>****

******方法 4:** 使用原生玩家****

****在这种方法中，我们在系统上本地播放声音**。该方法通过安装在您终端上的**外部播放器**播放音频文件。******

******示例 1:** 对于 Mac OS X****

## ****蟒蛇 3****

```py
**# import required module
import os

# play sound
file = "note.wav"
print('playing sound using native player')
os.system("afplay " + file)**
```

******输出:******

****<video class="wp-video-shortcode" id="video-536240-6" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210102134811/gfgnativeplayer.mp4?_=6">[https://media.geeksforgeeks.org/wp-content/uploads/20210102134811/gfgnativeplayer.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210102134811/gfgnativeplayer.mp4)</video>****

******示例 2:** 对于 Linux****

## ****蟒蛇 3****

```py
**# import required module
import os

# play sound
file = "note.mp3"
print('playing sound using native player')
os.system("mpg123 " + file)**
```

******输出**:****

****<video class="wp-video-shortcode" id="video-536240-7" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210102134811/gfgnativeplayer.mp4?_=7">[https://media.geeksforgeeks.org/wp-content/uploads/20210102134811/gfgnativeplayer.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210102134811/gfgnativeplayer.mp4)</video>****

******方法 5:** 使用*简单音频*模块****

****这主要是为了玩 **WAV** 文件和 **NumPy 数组。**运行以下命令安装软件包:****

```py
**$ sudo apt-get install libasound2-dev
$ pip3 install simpleaudio**
```

******播放()**方法用于播放音频文件。****

******示例:******

## ****蟒蛇 3****

```py
**# import required module
import simpleaudio as sa

# define an object to play
wave_object = sa.WaveObject.from_wave_file('note.wav)
print('playing sound using simpleaudio')

# define an object to control the play
play_object = wave_object.play()
play_object.wait_done()**
```

******输出:******

****<video class="wp-video-shortcode" id="video-536240-8" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210102134816/gfgsimpleaudio.mp4?_=8">[https://media.geeksforgeeks.org/wp-content/uploads/20210102134816/gfgsimpleaudio.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210102134816/gfgsimpleaudio.mp4)</video>****