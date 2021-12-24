# 如何用 Tkinter 播放 Python 中的声音？

> 原文:[https://www . geesforgeks . org/如何使用-tkinter 播放 python 中的声音/](https://www.geeksforgeeks.org/how-to-play-sounds-in-python-with-tkinter/)

当我们想要从用户那里获取数据时，Python GUI tkinter 非常有用。用户从图形用户界面吸引。GUI 在日常生活中非常有帮助。图形用户界面有助于我们让日常工作变得更加轻松和高效。如果你想借助 python GUI tkinter 播放音乐，那么你来对了。要在 python 的帮助下播放声音/音乐，您需要安装所需的模块。这个模块将有助于播放声音。

**有两个模块可以借助 tkinter python 播放声音:**

1.  pygame:是一个跨平台的模块，用来创建游戏和 GUI 的。
2.  playsound:是一个跨平台的模块，功能名为 playsound()

让我们看看如何借助 tkinter python GUI 播放声音/音乐。您必须将您的 mp3 文件保存在保存 python 文件的同一文件夹中，或者您必须给出 mp3 文件的完整路径。这里给出了使用以下方法的 mp3 文件。

<audio class="wp-audio-shortcode" id="audio-539444-1" preload="none" style="width:100%" controls=""><source type="audio/wav" src="https://media.geeksforgeeks.org/wp-content/uploads/20210110085700/1.wav?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20210110085700/1.wav](https://media.geeksforgeeks.org/wp-content/uploads/20210110085700/1.wav)</audio>

**方法 1:(使用播放声音)**

要安装 playsound，请使用以下命令

```py
pip install playsound 
```

**所需步骤**

1.  首先导入所需模块。
2.  初始化 Tk()并将其放入变量中以供进一步使用。
3.  在按钮的帮助下定义一个触发它的函数。
4.  创建一个按钮，在命令的帮助下触发一个功能。

> **语法:**播放声音(声音，块=真)

## 蟒蛇 3

```py
# importing required module
from playsound import playsound
from tkinter import*

root = Tk()
root.title('GeeksforGeeks sound player')  #giving the title for our window
root.geometry("500x400")

# making function
def play():
    playsound('1.mp3')

# title on the screen you can modify it   
title=Label(root,text="GeeksforGeeks",bd=9,relief=GROOVE,
            font=("times new roman",50,"bold"),bg="white",fg="green")
title.pack(side=TOP,fill=X)

# making a button which trigger the function so sound can be playeed
play_button = Button(root, text="Play Song", font=("Helvetica", 32),
                     relief=GROOVE, command=play)
play_button.pack(pady=20)

info=Label(root,text="Click on the button above to play song ",
           font=("times new roman",10,"bold")).pack(pady=20)
root.mainloop()
```

**输出:**

<video class="wp-video-shortcode" id="video-539444-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210115142517/15.01.2021_14.20.15_REC.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20210115142517/15.01.2021_14.20.15_REC.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210115142517/15.01.2021_14.20.15_REC.mp4)</video>

**方法二:(使用 pygame)**

要安装 pygame，请使用以下命令

```py
pip install pygame
```

**所需步骤**

1.  当代码运行时，会有一个窗口打开。
2.  在窗口，有一个按钮。当我们点击它时，会启动一个播放歌曲的功能。
3.  需要在上面定义该功能才能播放声音。
4.  然后制作一个在同一个文件夹中的 mp3 文件，或者当 mp3 文件不在同一个文件夹中时，给出它的完整路径来播放声音。(这个要小心)

> **语法:**mixer . music . load(“song . MP3”)

## 蟒蛇 3

```py
# importing required libraries
from tkinter import *
import pygame

root = Tk()
root.title('GeeksforGeeks sound player')

root.geometry("500x400")

pygame.mixer.init()# initialise the pygame

def play():
    pygame.mixer.music.load("1.mp3")
    pygame.mixer.music.play(loops=0)

title=Label(root,text="GeeksforGeeks",bd=9,relief=GROOVE,
            font=("times new roman",50,"bold"),bg="white",fg="green")
title.pack(side=TOP,fill=X)

play_button = Button(root, text="Play Song", font=("Helvetica", 32), command=play)
play_button.pack(pady=20)
root.mainloop()
```

**输出:**

<video class="wp-video-shortcode" id="video-539444-2" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210115142621/15.01.2021_14.23.27_REC.mp4?_=2">[https://media.geeksforgeeks.org/wp-content/uploads/20210115142621/15.01.2021_14.23.27_REC.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210115142621/15.01.2021_14.23.27_REC.mp4)</video>