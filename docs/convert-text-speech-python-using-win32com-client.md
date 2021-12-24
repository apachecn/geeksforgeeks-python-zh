# 使用 win32com.client 将 Python 中的文本转换为语音

> 原文:[https://www . geesforgeks . org/convert-text-speech-python-using-win 32 com-client/](https://www.geeksforgeeks.org/convert-text-speech-python-using-win32com-client/)

在 python 中，有几种 API 可以将文本转换为语音。python 库中可用的 API 之一，通常称为 win32com 库。它提供了一系列令人兴奋的方法，其中之一就是库的调度方法。调度方法当通过 **SAPI 的论证。SpVoice** 它与微软语音 SDK 交互，说出你从键盘输入的内容。
例子:

```
Input : Hello World
Output : 
<source type="audio/mpeg" src="https://media.geeksforgeeks.org/wp-content/uploads/hello-world.m4a?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/hello-world.m4a](https://media.geeksforgeeks.org/wp-content/uploads/hello-world.m4a)

Input : 121
Output : <source type="audio/mpeg" src="https://media.geeksforgeeks.org/wp-content/uploads/121.m4a?_=2">[https://media.geeksforgeeks.org/wp-content/uploads/121.m4a](https://media.geeksforgeeks.org/wp-content/uploads/121.m4a)

```

**安装**
要安装 win32com.client 模块，打开终端并写入

```
pip install pypiwin32

```

这在 Windows 平台上有效。现在我们都准备编写一个将文本转换为语音的示例程序。

```
# Python program to convert
# text to speech

# import the required module from text to speech conversion
import win32com.client

# Calling the Disptach method of the module which 
# interact with Microsoft Speech SDK to speak
# the given input from the keyboard

speaker = win32com.client.Dispatch("SAPI.SpVoice")

while 1:
    print("Enter the word you want to speak it out by computer")
    s = input()
    speaker.Speak(s)

# To stop the program press
# CTRL + Z
```

输入:

```
 Welcome to geeks for geeks
```

输出:

```
<source type="audio/mpeg" src="https://media.geeksforgeeks.org/wp-content/uploads/audio.m4a?_=3">[https://media.geeksforgeeks.org/wp-content/uploads/audio.m4a](https://media.geeksforgeeks.org/wp-content/uploads/audio.m4a)

```

本文由 **Subhajit Saha** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。