# 使用 Python 打开应用程序

> 原文:[https://www . geesforgeks . org/open-applications-use-python/](https://www.geeksforgeeks.org/open-applications-using-python/)

在本文中，我们将使用 Python3 创建一个系统应用程序菜单。我们将在菜单中包括以下应用程序:

*   谷歌浏览器
*   MS EDGE
*   MS EXCEL
*   MS POWERPOINT
*   微软 WORD
*   VLC 玩家
*   笔记本
*   插图画家
*   用计算机修改（图片或照片）
*   电报

你可以和它聊天，或者输入要打开的应用程序的数量，或者简单地，你也可以输入软件名称或它的缩写，比如

```
'Photoshop' -> 'PS'
```

### 需要的模块

*   **pyttsx3:** 是 Python 中的文本到语音转换库。与替代库不同，它脱机工作，并且兼容 Python 2 和 3。应用程序调用 pyttsx3.init()工厂函数来获取对 pyttsx3 的引用。引擎实例。这是一个非常容易使用的工具，可以将输入的文本转换成语音。可以使用以下命令安装:

```
pip install pyttsx3
```

下面的代码片段展示了上述模块的使用:

## 蟒蛇 3

```
# create object
engine = pyttsx3.init()

# assign voice
voices = engine.getProperty('voices')

#changing index changes voices but only 0 and 1 are working here
engine.setProperty('voice', voices[1].id)

# run tool
engine.runAndWait()

print("")
```

*   **os:**python 中的 OS 模块提供了与操作系统交互的功能。操作系统，属于 Python 的标准实用程序模块。该模块提供了一种使用操作系统相关功能的可移植方式。

下面是使用 Python 创建应用程序菜单的程序

## 蟒蛇 3

```
# import required module
import pyttsx3
import os

# driver code

# create object and assign voice
engine = pyttsx3.init()
voices = engine.getProperty('voices')

# changing index changes voices but only
# 0 and 1 are working here
engine.setProperty('voice', voices[1].id)
engine.runAndWait()
print("")
print("")

# introduction
print("  =============================================== Hello World!! ================================================")
engine.say('Hello World!!')

print("")
print("    My name is Divy Shah,I make this tool With this help of tool you can open below things.......")

print("\n\t 1.MICROSOFT WORD \t 2.MICROSOFT POWERPOINT \n\t 3.MICROSOFT EXCEL \t 4.GOOGLE CHROME \n\t 5.VLC PLAYER     \t 6.ADOBE ILLUSTRATOR \n\t 7.ADOBE PHOTOSHOP \t 8.MICROSOFT EDGE \n\t 9.NOTEPAD        \t 10.TELEGRAM \n\n\t\t     0\. FOR EXIT")

print("\n        (YOU CAN USE NUMBER OR YOU CAN DO CHAT LIKE 'OPEN NOTEBOOK' etc....)")

print("\n  ============================================ Welcome To My Tools ============================================")
pyttsx3.speak("Welcome to my tools")
print("")
print("")

pyttsx3.speak("chat with me with your requirements")

while True:
    # take input
    print("    CHAT WITH ME WITH YOUR REQUIREMENTS : ", end='')
    p = input()
    p = p.upper()
    print(p)

    if ("DONT" in p) or ("DON'T" in p) or ("NOT" in p):
        pyttsx3.speak("Type Again")
        print(".")
        print(".")
        continue

    # assignements for diffenet applications in the menu
    elif ("GOOGLE" in p) or ("SEARCH" in p) or ("WEB BROWSER" in p) or ("CHROME" in p) or ("BROWSER" in p) or ("4" in p):
        pyttsx3.speak("Opening")
        pyttsx3.speak("GOOGLE CHROME")
        print(".")
        print(".")
        os.system("chrome")

    elif ("IE" in p) or ("MSEDGE" in p) or ("EDGE" in p) or ("8" in p):
        pyttsx3.speak("Opening")
        pyttsx3.speak("MICROSOFT EDGE")
        print(".")
        print(".")
        os.system("msedge")

    elif ("NOTE" in p) or ("NOTES" in p) or ("NOTEPAD" in p) or ("EDITOR" in p) or ("9" in p):
        pyttsx3.speak("Opening")
        pyttsx3.speak("NOTEPAD")
        print(".")
        print(".")
        os.system("Notepad")

    elif ("VLCPLAYER" in p) or ("PLAYER" in p) or ("VIDEO PLAYER" in p) or ("5" in p):
        pyttsx3.speak("Opening")
        pyttsx3.speak("VLC PLAYER")
        print(".")
        print(".")
        os.system("VLC")

    elif ("ILLUSTRATOR" in p) or ("AI" in p) or ("6" in p):
        pyttsx3.speak("Opening")
        pyttsx3.speak("ADOBE ILLUSTRATOR")
        print(".")
        print(".")
        os.system("illustrator")

    elif ("PHOTOSHOP" in p) or ("PS" in p) or ("PHOTOSHOP CC" in p) or ("7" in p):
        pyttsx3.speak("Opening")
        pyttsx3.speak("ADOBE PHOTOSHOP")
        print(".")
        print(".")
        os.system("photoshop")

    elif ("TELEGRAM" in p) or ("TG" in p) or ("10" in p):
        pyttsx3.speak("Opening")
        pyttsx3.speak("TELEGRAM")
        print(".")
        print(".")
        os.system("telegram")

    elif ("EXCEL" in p) or ("MSEXCEL" in p) or ("SHEET" in p) or ("WINEXCEL" in p) or ("3" in p):
        pyttsx3.speak("Opening")
        pyttsx3.speak("MICROSOFT EXCEL")
        print(".")
        print(".")
        os.system("excel")

    elif ("SLIDE" in p) or ("MSPOWERPOINT" in p) or ("PPT" in p) or ("POWERPNT" in p) or ("2" in p):
        pyttsx3.speak("Opening")
        pyttsx3.speak("MICROSOFT POWERPOINT")
        print(".")
        print(".")
        os.system("powerpnt")

    elif ("WORD" in p) or ("MSWORD" in p) or ("1" in p):
        pyttsx3.speak("Opening")
        pyttsx3.speak("MICROSOFT WORD")
        print(".")
        print(".")
        os.system("winword")

    # close the program
    elif ("EXIT" in p) or ("QUIT" in p) or ("CLOSE" in p) or ("0" in p):
        pyttsx3.speak("Exiting")
        break

    # for invalid input
    else:
        pyttsx3.speak(p)
        print("Is Invalid,Please Try Again")
        pyttsx3.speak("is Invalid,Please try again")
        print(".")
        print(".")
```

**输出:**

<video class="wp-video-shortcode" id="video-510724-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20201105233227/Personal-Assistant-by-Divyshah.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20201105233227/Personal-Assistant-by-Divyshah.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20201105233227/Personal-Assistant-by-Divyshah.mp4)</video>