# 如何用 Python 播放和录制音频？

> 原文:[https://www . geesforgeks . org/如何用 python 播放和录制音频/](https://www.geeksforgeeks.org/how-to-play-and-record-audio-in-python/)

因为 python 可以做任何你能想象到的事情，包括播放和录制音频。本文将让您熟悉一些 python 库以及使用这些库在 python 中播放和录制声音的简单方法，用一些更多的功能来换取一些额外的 python 行。

大多数音频文件都是 MP3 和 WAV 文件格式。WAV 音频文件是最简单的数字音频格式，具有无损的高录制速率，因此与其他格式相比，WAV 文件很大。出于同样的原因，使用的 MP3 格式尺寸较小，压缩文件对整体音质的影响很小。此外，通过互联网上广泛提供的开源和免费软件，很容易将 WAV 转换为 MP3。

## **播放音频**

下面提到的是一些 python 库，使用它们可以播放 python 中的各种音频格式，包括 MP3 格式、WAV 格式，甚至 NumPy 数组。

**方法一:使用 Playsound**

仅用一行代码播放音频文件的即用包。人们可以用它播放 WAV 或 MP3 文件。这是一个单一的功能模块，不依赖于播放声音。

playsound library 的文档提到，它已经针对 WAV 和 MP3 文件进行了测试，但也可能适用于其他文件格式，其测试由用户决定。playsound 模块只包含一个东西——playsound 功能(也叫 play sound)。

以下是播放文件的代码行:

## 蟒蛇 3

```py
#import the library
from playsound import playsound

playsound('full_path/filename.mp3')
```

**输出:**

<video class="wp-video-shortcode" id="video-537892-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210106104353/1.playsound.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20210106104353/1.playsound.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210106104353/1.playsound.mp4)</video>

**方法二:使用 Simpleaudio。**

**例 1:**

它是一个跨平台的 python 库，用于播放单声道和立体声 WAV 文件，不依赖于音频播放。在 macOS、Windows 和 Linux 上正式支持 Python 3.7 及更高版本。

以下是播放. wav 格式文件的简单代码，尽管与上述库相比，它消耗的代码行更少:

## 蟒蛇 3

```py
# import library
import simpleaudio as sa

# to check all the functions in succession
# to verify the installation
import simpleaudio.functionchecks as fc
fc.run_all()

# Path to file
f_name = 'myfile.wav'

# create WaveObject instances
# directly from WAV files on disk
wave_obj = sa.WaveObject.from_wave_file(f_name)   

# Audio playback
play = wave_obj.play()

# To stop after playing the whole audio
play.wait_done() 
play.stop()
```

**输出:**

<video class="wp-video-shortcode" id="video-537892-2" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210106104928/2.-simpleaudio.mp4?_=2">[https://media.geeksforgeeks.org/wp-content/uploads/20210106104928/2.-simpleaudio.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210106104928/2.-simpleaudio.mp4)</video>

**例 2:**

simpleaudio 可以用来播放 NumPy 和 Python 数组&字节对象使用 simpleaudio.play_buffer() Numpy 数组可以用来存储音频，但是有一些至关重要的要求。如果要存储立体声音频，阵列必须有两列，每列包含一个音频数据通道。它们还必须是带符号的 16 位整数 d 型，因此采样幅度值必须介于-32768 到 32767 之间。下面是生成一个 NumPy 数组并使用 simpleaudio.play_buffer()播放它的代码。

## 蟒蛇 3

```py
import numpy as np
import simplesound as sa
# Note frequencies
first_freq = 400 
nxt_freq = first_freq * 2 ** (7 / 12)

# samples per second
smpl_rate = 44100
# Note duration in seconds
seconds = 3 

# Generate array(timesteps) with
# seconds*sample_rate steps,
# ranging between 0 and seconds
arr = np.linspace(0, seconds, seconds * smpl_rate, False)

# Generate a 400Hz Sine wave
first_note = np.sin(first_freq * arr * 2 * np.pi)
nxt_note = np.sin(nxt_freq * arr * 2 * np.pi)

# merging the notes
tape = np.hstack((first_note,nxt_note))

# normalizing to 16-bit range
# after concatenating the note notes
tape *= 32767 / np.max(np.abs(tape))

# Converting to 16-bit data
tape = tape.astype(np.int16)

# Start audio
play = sa.play_buffer(tape, 1, 2, smpl_rate)

# Wait for audio playback to finish before exiting
play.wait_done()
play.stop()
```

**输出:**

<video class="wp-video-shortcode" id="video-537892-3" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210106105228/2.1-simpleaudio.mp4?_=3">[https://media.geeksforgeeks.org/wp-content/uploads/20210106105228/2.1-simpleaudio.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210106105228/2.1-simpleaudio.mp4)</video>

**方法三:使用** **winsound。**

**例 1:**

它是一个内置模块，用于访问基本的声音播放机制。它只允许你播放 WAV 文件(它不支持任何其他文件格式)或让你的扬声器发出哔哔声，但它只在 Windows 上工作，顾名思义就是 WINsound。它是内置模块，因此不需要额外安装。

## 蟒蛇 3

```py
#Import windound
import winsound

winsound.PlaySound(path_to_file, winsound.SND_FILENAME)
```

**输出:**

<video class="wp-video-shortcode" id="video-537892-4" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210106110137/3.1-winsound.mp4?_=4">[https://media.geeksforgeeks.org/wp-content/uploads/20210106110137/3.1-winsound.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210106110137/3.1-winsound.mp4)</video>

**例 2:**

它也可以用来嘟嘟你的扬声器或播放窗口默认声音。在下面的代码中，5000 赫兹的蜂鸣音在车窗退出声音后播放 1000 毫秒。

## 蟒蛇 3

```py
#Import windound
import winsound

#Beep at frequency = 5000 Hz for duration of 1000 ms
winsound.Beep(5000, 1000) 

#windows exit sound after completion of above
winsound.PlaySound("SystemExit", winsound.SND_ALIAS)
```

**输出:**

<video class="wp-video-shortcode" id="video-537892-5" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210106110140/3.2-winsound.mp4?_=5">[https://media.geeksforgeeks.org/wp-content/uploads/20210106110140/3.2-winsound.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210106110140/3.2-winsound.mp4)</video>

这个库的主要缺点是它只针对 Windows 操作系统用户，也不支持播放任何其他文件而不是 WAV 格式。

**方法 4:使用发声装置。**

这个 Python 模块为 PortAudio 库提供绑定，并提供一些方便的函数来播放和录制包含音频信号的 NumPy 数组。它适用于 Linux、macOS 和 Windows 操作系统。

在下面的代码中，包含“sf.read()”的一行提取出所有原始音频数据以及存储在其 RIFF 头中的文件采样率；“sounddevice.wait()”确保脚本在“sd.play(data，sr)”播放完音频后终止。

## 蟒蛇 3

```py
# Import libraries
import sounddevice as sd
import soundfile as sf

# Extract data and sampling rate from file
array, smp_rt = sf.read(path_of_file, dtype = 'float32') 

# start the playback
sd.play(array, smp_rt)

# Wait until file is done playing
status = sd.wait() 

# stop the sound
sd.stop()
```

**输出:**

<video class="wp-video-shortcode" id="video-537892-6" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210106112410/4.1-sounddevice.mp4?_=6">[https://media.geeksforgeeks.org/wp-content/uploads/20210106112410/4.1-sounddevice.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210106112410/4.1-sounddevice.mp4)</video>

**方法五:使用 pydub。**

即使 pydub 可以轻松地打开和保存 WAV 文件，而没有任何其他依赖关系，但必须预先安装至少一个来自(simpleaudio、pyaudio、ffplay 和 avplay)的音频播放包。它为音频操作提供了纯 python 实现。

下面的代码导入两个库，第一个库用于加载文件，第二个库用于播放加载的文件。此外，还表示了两种加载。wav 文件。

## 蟒蛇 3

```py
from pydub import AudioSegment
from pydub.playback import play

tape = AudioSegment.from_file('path_to_myfile.wav', format='wav')
tape = AudioSegment.from_wav('path_to_myfile.wav')

play(tape)
```

**输出:**

<video class="wp-video-shortcode" id="video-537892-7" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210106112416/5.1-pydub.mp4?_=7">[https://media.geeksforgeeks.org/wp-content/uploads/20210106112416/5.1-pydub.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210106112416/5.1-pydub.mp4)</video>

**方法 6:使用 pyaudio。**

PyAudio 是 Python 的另一个跨平台音频库。虽然它比简单的音频库有更多的功能，例如录制和连续音频流，但它在很大程度上取决于是否有 PortAudio，这导致安装更加复杂。它还为 PortAudio 提供 Python 绑定，Portaudio 是 python-sounddevice 提供的跨平台音频 I/O 库。有了 PyAudio，你可以很容易地使用 Python 在各种平台上播放和录制音频。

## 蟒蛇 3

```py
''' Play a WAVE file '''
import pyaudio
import wave

filename = 'path-to_file.wav'

# Set chunk size of 1024 samples per data frame
chunk = 1024 

# Open the soaudio/sound file
af = wave.open(filename, 'rb')

# Create an interface to PortAudio
pa = pyaudio.PyAudio()

# Open a .Stream object to write the WAV file
# 'output = True' indicates that the
# sound will be played rather than
# recorded and opposite can be used for recording
stream = pa.open(format = pa.get_format_from_width(af.getsampwidth()),
                channels = af.getnchannels(),
                rate = af.getframerate(),
                output = True)

# Read data in chunks
rd_data = af.readframes(chunk)

# Play the sound by writing the audio
# data to the Stream using while loop
while rd_data != '':
    stream.write(rd_data)
    rd_data = af.readframes(chunk)

# Close and terminate the stream
stream.stop_stream()
stream.close()
pa.terminate()
```

**输出:**

<video class="wp-video-shortcode" id="video-537892-8" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210106121909/6.-pyaudio_play.mp4?_=8">[https://media.geeksforgeeks.org/wp-content/uploads/20210106121909/6.-pyaudio_play.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210106121909/6.-pyaudio_play.mp4)</video>

## **录制音频**

现在只是切换到文章的录制模式。上面提到的库很少用于相同的用途，播放和录制都可以一起解释，但是对于许多人来说，这可能会有点混乱。因此，这里首选不同的专用部分。

注意-在使用任何资料库进行录制之前，请确保设备的麦克风已实际连接，并且处于打开状态且未静音。人们可以使用操作系统的特性和设置进行检查。

**方法 1。使用 python-sounddevice**

该库允许您播放(如上所述)和录制包含音频信号信息的 NumPy 阵列。此模块需要 scipy 或 wavio 来保存录制的音频，这意味着在使用此包进行录制之前，scipy 或 wavio 库应与 Numpy 一起预安装。

## 蟒蛇 3

```py
# import required libraries
import sounddevice as sd
from scipy.io.wavfile import write
import wavio as wv

# Sampling frequency
frequency = 44400

# Recording duration in seconds
duration = 3.5

# to record audio from
# sound-device into a Numpy
recording = sd.rec(int(duration * frequency),
                   samplerate = freq, channels = 2)

# Wait for the audio to complete
sd.wait()

# using scipy to save the recording in .wav format
# This will convert the NumPy array
# to an audio file with the given sampling frequency
write("recording0.wav", freq, recording)

# using wavio to save the recording in .wav format
# This will convert the NumPy array to an audio
# file with the given sampling frequency
wv.write("recording1.wav", recording, freq, sampwidth=2)
```

**输出:**

<video class="wp-video-shortcode" id="video-537892-9" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210106114323/1.-record_soundevice.mp4?_=9">[https://media.geeksforgeeks.org/wp-content/uploads/20210106114323/1.-record_soundevice.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210106114323/1.-record_soundevice.mp4)</video>

如音频部分所述，sounddevice 有一个默认选项来指定重复使用的频道和频率。此后，无需在 sd.rec()方法中将此选项作为参数传递。下面的代码表示相同的，并且还可以将记录数组的数据类型从默认类型 float32 更改为其他类型。

## 蟒蛇 3

```py
import sounddevice as sd

sd.default.samplerate = 4400
sd.default.channels = 2

myrecording = sd.rec(int(duration * fs))

# change the data type: pass a new argument in .rec() of dtype
# myrecording = sd.rec(int(duration * fs), dtype='float64')

sd.wait()
```

#### 同时播放和录制

同时播放名为 my_arr 和 Record 的数组。这里的采样率是 smpl_rate

## 蟒蛇 3

```py
import sounddevice as sd
import numpy as np

smpl_rate = 44100

my_arr = np.random.uniform(-1,1,smpl_rate)
recordd= sd.playrec(my_arr, smpl_rate, channels=2)

sd.wait()
```

<video class="wp-video-shortcode" id="video-537892-10" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210101111541/play_rec.mp4?_=10">[https://media.geeksforgeeks.org/wp-content/uploads/20210101111541/play_rec.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210101111541/play_rec.mp4)</video>

**方法二:使用 pyaudio。**

如上所述，我们通过读取 pyaudio 来使用 pyaudio 播放音频。流()。要录制音频，我们必须写入同一个流。下面是录制几秒钟的音频并将其保存到. wav 文件中的代码:

## 蟒蛇 3

```py
import pyaudio
import wave

# Record in chunks of 1024 samples
chunk = 1024 

# 16 bits per sample
sample_format = pyaudio.paInt16 
chanels = 2

# Record at 44400 samples per second
smpl_rt = 44400 
seconds = 4
filename = "path_of_file.wav"

# Create an interface to PortAudio
pa = pyaudio.PyAudio() 

stream = pa.open(format=sample_format, channels=chanels,
                 rate=smpl_rt, input=True,
                 frames_per_buffer=chunk)

print('Recording...')

# Initialize array that be used for storing frames
frames = [] 

# Store data in chunks for 8 seconds
for i in range(0, int(smpl_rt / chunk * seconds)):
    data = stream.read(chunk)
    frames.append(data)

# Stop and close the stream
stream.stop_stream()
stream.close()

# Terminate - PortAudio interface
pa.terminate()

print('Done !!! ')

# Save the recorded data in a .wav format
sf = wave.open(filename, 'wb')
sf.setnchannels(chanels)
sf.setsampwidth(pa.get_sample_size(sample_format))
sf.setframerate(smpl_rt)
sf.writeframes(b''.join(frames))
sf.close()
```

**输出:**

<video class="wp-video-shortcode" id="video-537892-11" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210106121905/2.-record_pyaudio.mp4?_=11">[https://media.geeksforgeeks.org/wp-content/uploads/20210106121905/2.-record_pyaudio.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210106121905/2.-record_pyaudio.mp4)</video>