# 创建 Python 脚本通知休息

> 原文:[https://www . geesforgeks . org/create-a-python-script-通知休息一下/](https://www.geeksforgeeks.org/create-a-python-script-notifying-to-take-a-break/)

当我们使用笔记本电脑或个人电脑时，我们通常不会休息。它可能会影响我们的视力和思维。因此，使用 Python，我们可以制作一个程序，当用户再次开始在笔记本电脑上工作时，它会通知我们必须休息一段时间后再次开始。

### 需要的模块

*   **pyttsx3–**它是 Python 中的文本到语音转换库。应用程序调用 pyttsx3.init()工厂函数来获取对 pyttsx3 的引用。这是一个非常容易使用的工具，可以将输入的文本转换成语音。要安装该模块，请在终端中键入以下命令。

```py
pip install pyttsx3
```

*   **普利特–**普利特模块用于访问硬件的功能。这个模块没有内置 Python。我们需要从外部安装它。要安装此模块，请在终端中键入以下命令。

```py
pip install plyer 
```

当我们启动笔记本电脑或个人电脑时，我们只需运行 Python 程序，我们将安排操作，比如每 50 分钟后，我们的电脑或笔记本电脑会通知我们，并告诉我们休息一下。很多时候，我们只是忽略给我们的通知，但是笔记本电脑会提醒我们必须休息一下。

**创建说话方法:**

## 蟒蛇 3

```py
import pyttsx3
from plyer import notification
import time

# Speak method
def Speak(self, audio):

    # Calling the initial constructor 
    # of pyttsx3
    engine = pyttsx3.init('sapi5')

    # Calling the getter method
    voices = engine.getProperty('voices')

    # Calling the setter method
    engine.setProperty('voice', voices[1].id)

    engine.say(audio)
    engine.runAndWait()
```

**创建 Take_break 方法，该方法将为我们的窗口创建一个弹出通知**

## 蟒蛇 3

```py
def Take_break():

    Speak("Do you want to start sir?")
    question = input()

    if "yes" in question:
        Speak("Starting Sir")

    if "no" in question:
        Speak("We will automatically start after 5 Mins Sir.")
        time.sleep(5*60)
        Speak("Starting Sir")

    # A notification we will held that 
    # Let's Start sir and with a message of
    # will tell you to take a break after 45
    # mins for 10 seconds
    while(True):
        notification.notify(title="Let's Start sir",
        message="will tell you to take a break after 45 mins",
        timeout=10)

        # For 45 min the will be no notification but 
        # after 45 min a notification will pop up.
        time.sleep(0.5*60)

        Speak("Please Take a break Sir")

        notification.notify(title="Break Notification",
        message="Please do use your device after sometime as you have"
        "been continuously using it for 45 mins and it will affect your eyes",
        timeout=10)

# Driver's Code        
if __name__ == '__main__':
    Take_break()
```

**下面是完整的代码**

## 蟒蛇 3

```py
import pyttsx3
from plyer import notification
import time

# Speak method
def Speak(self, audio):

    # Calling the initial constructor 
    # of pyttsx3
    engine = pyttsx3.init('sapi5')

    # Calling the getter method
    voices = engine.getProperty('voices')

    # Calling the setter method
    engine.setProperty('voice', voices[1].id)

    engine.say(audio)
    engine.runAndWait()

def Take_break():

    Speak("Do you want to start sir?")
    question = input()

    if "yes" in question:
        Speak("Starting Sir")

    if "no" in question:
        Speak("We will automatically start after 5 Mins Sir.")
        time.sleep(5*60)
        Speak("Starting Sir")

    # A notification we will held that 
    # Let's Start sir and with a message of
    # will tell you to take a break after 45
    # mins for 10 seconds
    while(True):
        notification.notify(title="Let's Start sir",
        message="will tell you to take a break after 45 mins",
        timeout=10)

        # For 45 min the will be no notification but 
        # after 45 min a notification will pop up.
        time.sleep(0.5*60)

        Speak("Please Take a break Sir")

        notification.notify(title="Break Notification",
        message="Please do use your device after sometime as you have"
        "been continuously using it for 45 mins and it will affect your eyes",
        timeout=10)

# Driver's Code        
if __name__ == '__main__':
    Take_break()
```

**输出:**

<video class="wp-video-shortcode" id="video-462446-1" width="640" height="360" preload="metadata" controls=""><source type="video/webm" src="https://media.geeksforgeeks.org/wp-content/cdn-uploads/20200730204140/python-break-notification.webm?_=1">[https://media.geeksforgeeks.org/wp-content/cdn-uploads/20200730204140/python-break-notification.webm](https://media.geeksforgeeks.org/wp-content/cdn-uploads/20200730204140/python-break-notification.webm)</video>

**注意:**还会产生一个语音命令。