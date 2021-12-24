# 如何获取 Python 中音频的时长？

> 原文:[https://www . geesforgeks . org/如何获得 python 中音频的持续时间/](https://www.geeksforgeeks.org/how-to-get-the-duration-of-audio-in-python/)

使用 Python 语言可以找到音频文件的持续时间，Python 语言的库使用丰富。使用一些库如**诱变剂、**波、**有声读物**、**T5 等。不仅仅限于提取音频文件的长度/持续时间，还提供了更多功能。**

**源音频文件:**

<audio class="wp-audio-shortcode" id="audio-552164-1" preload="none" style="width:100%" controls=""><source type="audio/wav" src="https://media.geeksforgeeks.org/wp-content/uploads/20210121195917/alarm.wav?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20210121195917/alarm.wav](https://media.geeksforgeeks.org/wp-content/uploads/20210121195917/alarm.wav)</audio>

现在让我们看看，我们如何使用 python 获得任何音频文件的持续时间:

### **方法 1:使用 Python 库‘诱变剂’**

诱变剂是一个处理音频元数据的 Python 模块。它支持各种格式的音频文件，如 wavpack、mp3、Ogg 等。以下是使用它计算音频文件持续时间的步骤:

**第一步:安装诱变剂**

由于诱变剂是一个外部 python 库，因此首先需要使用 pip 命令安装它，如下所示:

```
pip install mutagen
```

**第二步:导入诱变剂**

安装后，需要使用以下命令将其导入到我们的脚本中，

```
import mutagen
```

在我们的程序中，我们将使用诱变剂库的一些内置功能，让我们稍微探索一下它们，以更好地理解源代码:

**1) WAVE()**

> **语法:** WAVE(文件事物/文件名)
> 
> **使用:**它只是创建一个文件名作为参数的 WAVE 对象。
> 
> **示例**:voice = WAVE(“sample . wav”)

**2)信息**

> **语法**:变量.信息
> 
> **使用**:获取已经创建 WAVE 对象的音频文件的元数据。
> 
> **示例** : voice_info = voice.info

**3)长度**

> **语法:**可变长度
> 
> **使用**:以秒为单位返回音频长度。返回值是浮点型的(默认情况下)。
> 
> **示例**:voice _ length = voice _ info . length

下面是记录任何音频文件的持续时间/长度的实际 Python 脚本:

## 蟒蛇 3

```
import mutagen
from mutagen.wave import WAVE

# function to convert the information into 
# some readable format
def audio_duration(length):
    hours = length // 3600  # calculate in hours
    length %= 3600
    mins = length // 60  # calculate in minutes
    length %= 60
    seconds = length  # calculate in seconds

    return hours, mins, seconds  # returns the duration

# Create a WAVE object
# Specify the directory address of your wavpack file
# "alarm.wav" is the name of the audiofile
audio = WAVE("alarm.wav")

# contains all the metadata about the wavpack file
audio_info = audio.info
length = int(audio_info.length)
hours, mins, seconds = audio_duration(length)
print('Total Duration: {}:{}:{}'.format(hours, mins, seconds))
```

**输出**:

```
Total Duration: 0:0:2
```

### **方法 2:使用 Python 库‘audio read’**

Audioread 是 Python 的跨库音频解码。它使用任何可用的后端解码音频文件。以下是使用它计算音频文件持续时间的步骤:

**第一步:安装 audioread**

由于 audioread 是一个外部 python 库，因此首先需要使用 pip 命令安装它，如下所示:

```
pip install audioread
```

步骤 2:导入音频读取

安装后，需要使用以下命令将其导入到我们的脚本中，

```
import audioread
```

在我们的程序中，我们将使用 audioread 库的一些内置功能，让我们对它们进行一些探索，以更好地理解源代码:

**1) audio_open()**

> **语法** : audioread.audio_open(文件名)
> 
> **使用**:它只是使用系统上可用的库打开一个音频文件
> 
> **示例**:以 audio read . audio _ open(‘示例. wav’)为例:
> 
> #声明 1…声明 n

**2)持续时间**

> **语法** : fileobject.duration
> 
> **使用**:以秒为单位返回音频长度(默认为浮点)。
> 
> **示例**:变量= fptr.duration

下面是记录任何音频文件的持续时间/长度的实际 Python 脚本:

## 蟒蛇 3

```
# METHOD 2
import audioread

# function to convert the information into 
# some readable format
def duration_detector(length):
    hours = length // 3600  # calculate in hours
    length %= 3600
    mins = length // 60  # calculate in minutes
    length %= 60
    seconds = length  # calculate in seconds

    return hours, mins, seconds

# alarm.wav is the name of the audio file
# f is the fileobject being created
with audioread.audio_open('alarm.wav') as f:

    # totalsec contains the length in float
    totalsec = f.duration
    hours, mins, seconds = duration_detector(int(totalsec))
    print('Total Duration: {}:{}:{}'.format(hours, mins, seconds))
```

**输出**:

```
Total Duration: 0:0:2
```

### **方法 3:使用 Python 库‘Scipy’**

SciPy 有许多模块、类和函数可用于从各种文件格式(如 Wav 声音文件、MATLAB 文件等)中读取数据和向其中写入数据。以下是使用它计算音频文件持续时间的步骤:

**步骤 1:安装 Scipy**

由于 Scipy 是一个外部 python 库，因此首先需要使用 pip 命令安装它，如下所示:

```
pip install scipy
```

**第二步：导入 Scipy**

安装后，需要使用以下命令将其导入到我们的脚本中，

```
import scipy
from scipy.io import wavfile
```

在我们的程序中，我们将使用 Scipy 库的一些内置功能，让我们对它们进行一些探索，以更好地理解源代码:

**1） scipy.io.wavfile.read（）**

> **语法** : scipy.io.wavfile.read(文件名)
> 
> **使用:**它从 WAV 文件中返回采样速率(以采样/秒为单位)和数据。该文件可以是打开的文件或文件名。返回的采样率是一个 Python 整数。数据以 NumPy 数组的形式返回，数据类型由文件确定。
> 
> **示例** : variable1，variable 2 = scipy . io . wav file . read(' Example . wav ')

下面是记录任何音频文件的持续时间/长度的实际 Python 脚本:

## 蟒蛇 3

```
# Method 3
import scipy
from scipy.io import wavfile

# function to convert the information into 
# some readable format
def output_duration(length):
    hours = length // 3600  # calculate in hours
    length %= 3600
    mins = length // 60  # calculate in minutes
    length %= 60
    seconds = length  # calculate in seconds

    return hours, mins, seconds

# sample_rate holds the sample rate of the wav file
# in (sample/sec) format
# data is the numpy array that consists
# of actual data read from the wav file
sample_rate, data = wavfile.read('alarm.wav')

len_data = len(data)  # holds length of the numpy array

t = len_data / sample_rate  # returns duration but in floats

hours, mins, seconds = output_duration(int(t))
print('Total Duration: {}:{}:{}'.format(hours, mins, seconds))
```

**输出**:

```
Total Duration: 0:0:2
```