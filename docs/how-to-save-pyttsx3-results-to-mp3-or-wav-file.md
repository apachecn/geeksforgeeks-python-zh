# 如何将 pyttsx3 结果保存到 MP3 或 WAV 文件？

> 原文:[https://www . geesforgeks . org/how-save-pyttsx 3-results-to-MP3-or-wav-file/](https://www.geeksforgeeks.org/how-to-save-pyttsx3-results-to-mp3-or-wav-file/)

在本文中，我们将看到如何将 *pyttsx3* 结果生成并保存为 mp3 和 wav 文件。 *Pyttsx3* 是一个 python 模块，提供了文本到语音的 API。我们可以用这个 API 把文本转换成语音。

### 环境设置:

要使用 pyttsx3，我们必须首先安装 *espeak* 和 *ffmpeg* 。

```py
sudo apt update
sudo apt install espeak
sudo apt install ffmpeg
```

另外，我们需要安装最新版本的 *pyttsx3*

```py
python3 -m pip install pyttsx3
```

我们可以通过导入模块来确认安装。

```py
import pyttsx3
```

如果上述语句运行无误，则环境设置成功。

### 使用 Pyttsx3

*   首先，我们要初始化 *pyttsx3* 发动机。 *init()* 方法为我们做到了。
*   接下来，我们需要用我们想要转换成音频的文本创建一个字符串。
*   *say()* 方法以字符串为参数。它会设定它要说的字符串。
*   由于语音需要一段时间才能在机器的扬声器上播放，我们需要等待该过程完成。因此，我们需要调用 *runAndWait()* 方法，以便让解释器在此之前停止执行。
*   以下是上述步骤的代码:

## 蟒蛇 3

```py
# Import the required module
import pyttsx3

# Create a string
string = "Lorem Ipsum is simply dummy text " \
    + "of the prting and typesetting industry."

# Initialize the Pyttsx3 engine
engine = pyttsx3.init()

# Command it to speak the given string
engine.say(string)

# Wait until above command is not finished.
engine.runAndWait()
```

**输出:**

<video class="wp-video-shortcode" id="video-559973-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210217223730/op3-2021-02-17_22.36.14.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20210217223730/op3-2021-02-17_22.36.14.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210217223730/op3-2021-02-17_22.36.14.mp4)</video>

### 将产生的声音保存在文件中

*   注意，我们的系统中需要有 *ffmpeg* 。因此，请确保环境设置正确无误。
*   *Pyttsx3* 自带 *save_to_file()* 方法，以要说话的文本和文件路径为参数。
*   此方法将给定文件保存在路径中。但是，此模块处于开发状态，因此在某些操作系统中，卷和速率选项可能无法正常工作。
*   我们必须把图书馆更新到最新版本。使用以下方法安装模块:

```py
sudo apt install git
python3 -m pip install git+https://github.com/nateshmbhat/pyttsx3
```

*   这将直接安装可用的最新版本。
*   下面是执行相同操作的代码:

## 蟒蛇 3

```py
# Import the required module
import pyttsx3

# Create a string
string = "Lorem Ipsum is simply dummy text " \
    + "of the prting and typesetting industry."

# Initialize the Pyttsx3 engine
engine = pyttsx3.init()

# We can use file extension as mp3 and wav, both will work
engine.save_to_file(string, 'speech.mp3')

# Wait until above command is not finished.
engine.runAndWait()
```

**输出:**

<video class="wp-video-shortcode" id="video-559973-2" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210217223731/op2.mp4?_=2">[https://media.geeksforgeeks.org/wp-content/uploads/20210217223731/op2.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210217223731/op2.mp4)</video>