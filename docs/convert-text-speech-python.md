# 在 Python 中将文本转换为语音

> 原文:[https://www.geeksforgeeks.org/convert-text-speech-python/](https://www.geeksforgeeks.org/convert-text-speech-python/)

在 Python 中，有几种可用于将文本转换为语音的 API。其中一个应用编程接口是谷歌文本到语音应用编程接口，通常被称为 gTTS 应用编程接口。gTTS 是一个非常容易使用的工具，它将输入的文本转换成音频，可以保存为 mp3 文件。

gTTS API 支持多种语言，包括英语、印地语、泰米尔语、法语、德语等。语音可以用两种音频速度中的任何一种来传递，快或慢。但是，从最新更新开始，无法更改生成的音频的声音。

### **安装**

要安装 gTTS 应用编程接口，打开终端并编写

```py
pip install gTTS

```

这适用于任何平台。
现在我们都准备写一个将文本转换为语音的示例程序。

```py
# Import the required module for text 
# to speech conversion
from gtts import gTTS

# This module is imported so that we can 
# play the converted audio
import os

# The text that you want to convert to audio
mytext = 'Welcome to geeksforgeeks!'

# Language in which you want to convert
language = 'en'

# Passing the text and language to the engine, 
# here we have marked slow=False. Which tells 
# the module that the converted audio should 
# have a high speed
myobj = gTTS(text=mytext, lang=language, slow=False)

# Saving the converted audio in a mp3 file named
# welcome 
myobj.save("welcome.mp3")

# Playing the converted file
os.system("mpg321 welcome.mp3")
```

### **输出**

```py
The output of the above program should be a 
voice saying, 'Welcome to geeksforgeeks!'

```

本文由**阿基尔·戈埃尔**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。