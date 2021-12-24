# 使用 PyAudio 和 SpeechRecognition 列出 Python 中所有连接到系统的麦克风

> 原文:[https://www . geesforgeks . org/list-所有麦克风-使用 pyaudio 和 speechrecognition 连接到 python 系统/](https://www.geeksforgeeks.org/list-all-the-microphones-connected-to-system-in-python-using-pyaudio-and-speechrecognition/)

在本文中，我们将获取系统附带的麦克风的列表标识和索引。在 Python 程序中处理麦克风时，应该了解麦克风标识。因此，为了获得系统附带的麦克风列表，我们需要以下库。

*   语音识别
*   PyAudio(音频)

### 装置

*   **SpeechRecognition:** This module does not comes built-in with Python. There are two ways to install this module.
    1) Type the below command in the terminal.

    ```py
    pip install SpeechRecognition
    ```

    2)从 [PyPI](https://pypi.org/project/SpeechRecognition/) 下载资源并解压到一个文件夹中，然后在 cmd 或终端运行以下命令。

    ```py
    python setup.py install
    ```

*   **PyAudio:**
    **1) Windows:** Run the following command in the CMD.

    ```py
    pip install pyaudio
    ```

    **2) Linux:** 在终端运行以下命令。

    ```py
    sudo apt-get install python-pyaudio python3-pyaudio
    ```

### 列出所有连接的麦克风

首先，将语音识别实例导入为“sr”

```py
import speech_recognition as sr

```

现在`list_microphone_names()`方法将向系统返回已连接麦克风的阵列/列表。

```py
sr.Microphone.list_microphone_names()

```

**完整代码:**

```py
import speechrecognition as sr

print(sr.Microphone.list_microphone_names())
```

**输出:**

> [' hda Intel PCH:ALC 255 analog(HW:0.0)'，hda Intel PCH:HDMI 0(HW:0.3)'，hda Intel PCH:HDMI 1(HW:0.7)'，hda Intel PCH:HDMI 2(HW:0.8)'，hda Intel PCH:HDMI 3(HW:0.9)'，hda Intel PCH:HDMI 4(HW:0.10)'，sysdefault '、front '、surround40 '、surround51 '、surround71 '、HDMI '、pulse '，' dmix '”