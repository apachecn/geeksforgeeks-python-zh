# Python 中 Uberi/speechecognition 的介绍和安装

> 原文:[https://www . geeksforgeeks . org/introduction-and-installation-of-uberi-speechecognition-in-python/](https://www.geeksforgeeks.org/introduction-and-installation-of-uberi-speechrecognition-in-python/)

Python 中语音识别的最佳库之一，使用各种引擎和应用编程接口在线和离线执行语音识别。

安装
在 cmd 或终端使用此命令，确保 Python 已安装，并且 Python 路径也存储在 pc 中。

```py
pip install speechrecognition
```

**或**
从 [PyPI](https://pypi.org/project/SpeechRecognition/) 下载资源并解压到文件夹中，然后在 cmd 或终端运行以下命令。

```py
python setup.py install
```

#### 先决条件

*   **python**
    确保安装了 Python，并且 Python 的路径也存储在系统中。

*   **2\. PyAudio** 
    PyAudio is need only when the input is from microphone. Make sure PyAudio version is PyAudio version 0.2.11 or above. If not installed, everything in the library will still work, except attempting to instantiate a Microphone object will raise an AttributeError. 

    **安装:**
    **1) Windows:** 在 cmd 中执行以下命令。

```py
pip install pyaudio
```

*   **2) Debian Linux:** 在终端执行下面的命令。

```py
sudo apt-get install python-pyaudio python3-pyaudio
```

*   **针对 Python 的谷歌 api 客户端库**
    谷歌 API 客户端库仅在想要使用谷歌云语音 API 时才需要。
    **安装:**
    **1)窗户:**执行

```py
pip install virtualenv
virtualenv 
\Scripts\activate
\Scripts\pip.exe install google-api-python-client
```

*   在 CMD 中。
    **2) Debian Linux:** 执行

```py
pip install virtualenv
virtualenv 
\Scripts\activate
\Scripts\pip.exe install google-api-python-client
```

*   在一个终端

*   **Flac 编码器**
    需要一个 Flac 编码器对音频数据进行编码发送到 API。如果使用 Windows (x86 或 x86-64)、OS X(仅限英特尔 Macs、OS X 10.6 或更高版本)或 Linux (x86 或 x86-64)，这已经与此库捆绑在一起—您不需要安装任何东西。

*   **pocket Sphinx**
    PocketSphinx-Python 是必需的，前提是您要使用 Sphinx 识别器
    **安装:**
    **1) Windows:** 通过运行下载完整的 pocket Sphinx-Python 源代码

> git 克隆–递归–深度 1 https://github.com/cmusphinx/pocketsphinx-python

*   **注意:**从 GitHub 下载 ZIP 存档将不起作用。
    在 PocketSphinx-Python 源代码文件夹中运行下面的命令来编译和安装 PocketSphinx。

```py
python setup.py install
```

*   **2) Linux:** 针对 Python 2 运行
    ，

```py
pip install pocketsphinx 
```

*   对于 Python 3。

```py
pip3 install pocketsphinx
```