# 使用 Python 创建录音机

> 原文:[https://www . geesforgeks . org/create-a-voice-recorder-use-python/](https://www.geeksforgeeks.org/create-a-voice-recorder-using-python/)

Python 可以用来执行各种任务。其中一个是创造一个录音机。我们可以使用 python 的 **sounddevice** 模块来录制和播放音频。该模块与 **wavio** 或 **scipy** 模块一起提供了保存录制音频的方法。

### 装置

*   **sounddevice:** 该模块提供播放和录制包含音频信号的 NumPy 阵列的功能。让我们通过运行以下命令来安装**T3:**

```
$ pip3 install sounddevice

```

*   我们可以使用 **wavio** 和 **scipy** 以文件格式**保存录制的音频。**我们会在这里看到他们两个。
*   要安装 **wavio:**

```
$ pip3 install wavio

```

*   要安装 **scipy** :

```
$ pip3 install scipy

```

现在，我们已经完成了所需模块的安装。那么，让我们编写代码。

## 入门指南

首先，导入所需的库。

```
# import required libraries
import sounddevice as sd
from scipy.io.wavfile import write
import wavio as wv
```

现在，在启动记录器之前，我们必须声明几个变量。第一个是音频的采样频率(在大多数情况下，这将是每秒 44100 或 48000 帧)，第二个是记录持续时间。我们必须以秒为单位指定持续时间，以便它在该持续时间后停止录制。

所以，让我们也宣布它们。

```
# Sampling frequency
freq = 44100

# Recording duration
duration = 5
```

现在，我们准备启动录音机。它将为录制的音频创建一个 NumPy 数组。

```
# Start recorder with the given values of 
# duration and sample frequency
recording = sd.rec(int(duration * freq), 
                   samplerate=freq, channels=2)

# Record audio for the given number of seconds
sd.wait()
```

现在，我们完成了录音。所以，我们还是省省吧。要保存音频文件，我们可以使用 **scipy** 模块或 **wavio** 模块。让我们一个一个地看一遍。

### **使用 Scipy:**

我们将使用 scipy.io.wavfile 中的 write 函数将 NumPy 数组转换为音频文件。

```
# This will convert the NumPy array to an audio
# file with the given sampling frequency
write("recording0.wav", freq, recording)
```

### **使用波形:**

我们也可以使用 **wavio** 库中的 write 函数。

```
# Convert the NumPy array to audio file
wv.write("recording1.wav", recording, freq, sampwidth=2)
```

**完整代码:**

## 蟒蛇 3

```
# import required libraries
import sounddevice as sd
from scipy.io.wavfile import write
import wavio as wv

# Sampling frequency
freq = 44100

# Recording duration
duration = 5

# Start recorder with the given values 
# of duration and sample frequency
recording = sd.rec(int(duration * freq), 
                   samplerate=freq, channels=2)

# Record audio for the given number of seconds
sd.wait()

# This will convert the NumPy array to an audio
# file with the given sampling frequency
write("recording0.wav", freq, recording)

# Convert the NumPy array to audio file
wv.write("recording1.wav", recording, freq, sampwidth=2)
```