# Python:将语音转换为文本，将文本转换为语音

> 原文:[https://www . geesforgeks . org/python-convert-speech-to-text-text-to-speech/](https://www.geeksforgeeks.org/python-convert-speech-to-text-and-text-to-speech/)

语音识别是家庭自动化、人工智能等应用中的一个重要特征。本文旨在介绍如何使用 Python 的`SpeechRecognition`和`pyttsx3`库。

**安装要求:**

*   **Python 语音识别模块:**

    ```
    pip install speechrecognition
    ```

*   **PyAudio:** Use the following command for linux users

    ```
    sudo apt-get install python3-pyaudio

    ```

    Windows 用户可以通过在终端中执行以下命令来安装 pyaudio

    ```
    pip install pyaudio

    ```

*   **Python pyttsx3 模块:**

    ```
    pip install pyttsx3

    ```

**使用麦克风的语音输入和语音到文本的翻译**

*   **允许调节环境噪音:**由于周围的噪音变化，我们必须允许程序一秒钟或更长时间来调节录制的能量阈值，以便根据外部噪音水平进行调节。
*   **语音转文本翻译:**这是在谷歌语音识别的帮助下完成的。这需要一个活跃的互联网连接才能工作。然而，有一些离线识别系统，如 PocketSphinx，但是有一个非常严格的安装过程，需要几个依赖项。谷歌语音识别是最容易使用的方法之一。

**语音到文本的翻译:**

首先，我们需要导入库，然后使用`init()`函数进行初始化。这个函数可能需要 2 个参数。

```
init(driverName string, debug bool)

```

*   **驱动程序名称:**【可用驱动程序名称】Windows 上的 sapi5 | MacOS 上的 nsss
*   调试:启用或禁用调试输出

初始化后，我们将使用 `say()` 功能使程序朗读文本。
这个方法也可以带 2 个参数。

```
say(text unicode, name string)

```

*   **文字:**任何你想听的文字。
*   **名称:**为本次演讲设置名称。(可选)

最后，为了运行演讲，我们使用`runAndWait()`除非翻译遇到`runAndWait()`，否则不会说所有的 say()文本。

下面是实现。

```
# Python program to translate
# speech to text and text to speech

import speech_recognition as sr
import pyttsx3 

# Initialize the recognizer 
r = sr.Recognizer() 

# Function to convert text to
# speech
def SpeakText(command):

    # Initialize the engine
    engine = pyttsx3.init()
    engine.say(command) 
    engine.runAndWait()

# Loop infinitely for user to
# speak

while(1):    

    # Exception handling to handle
    # exceptions at the runtime
    try:

        # use the microphone as source for input.
        with sr.Microphone() as source2:

            # wait for a second to let the recognizer
            # adjust the energy threshold based on
            # the surrounding noise level 
            r.adjust_for_ambient_noise(source2, duration=0.2)

            #listens for the user's input 
            audio2 = r.listen(source2)

            # Using ggogle to recognize audio
            MyText = r.recognize_google(audio2)
            MyText = MyText.lower()

            print("Did you say "+MyText)
            SpeakText(MyText)

    except sr.RequestError as e:
        print("Could not request results; {0}".format(e))

    except sr.UnknownValueError:
        print("unknown error occured")
```

```
Input: voice speech (Hi buddy how are you)  

Output: Did you say hi buddy how are you

```

<audio class="wp-audio-shortcode" id="audio-366839-1" preload="none" style="width:100%" controls=""><source type="audio/mpeg" src="https://contribute.geeksforgeeks.org/wp-content/uploads/hey-buddy-how-are-you.mp3?_=1">[https://contribute.geeksforgeeks.org/wp-content/uploads/hey-buddy-how-are-you.mp3](https://contribute.geeksforgeeks.org/wp-content/uploads/hey-buddy-how-are-you.mp3)</audio>