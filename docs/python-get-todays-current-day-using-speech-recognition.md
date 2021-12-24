# Python–使用语音识别获得今天的当前日期

> 原文:[https://www . geesforgeks . org/python-get-today-current-day-use-语音识别/](https://www.geeksforgeeks.org/python-get-todays-current-day-using-speech-recognition/)

由于我们正在做的大量工作，我们经常不记得日期。因此，这里有一个 Python 程序，在它的帮助下，我们只需用笔记本电脑或手机进行简单的聊天，就可以找到日期。

### 需要的模块

*   [**DateTime:**](https://www.geeksforgeeks.org/python-datetime-module-with-examples/) 这是 Python 中的一个库，借助它我们可以操纵日期和时间。它预装了 python，所以我们不必安装。
*   **pyttsx3:** 这是文本到语音转换库。它有助于与用户沟通。这个模块没有内置 Python。要安装它，请在终端中键入以下命令。

```py
pip install pyttsx3
```

*   **语音识别:**有助于语音识别。语音识别是将音频转换为文本的过程。该模块没有内置 Python。要安装它，请在终端中键入以下命令。

```py
pip install SpeechRecognition
```

现在让我们用语音识别的方法来编码这个程序。

**第一步:**制定取命令的方法。这样我们的程序就可以接受我们的命令。

## 蟒蛇 3

```py
import datetime
import pyttsx3
import speech_recognition as sr

def take_commands():

    # Making the use of Recognizer and Microphone
    # Method from Speech Recognition for taking
    # commands
    r = sr.Recognizer()

    with sr.Microphone() as source:
        print('Listening')

        # seconds of non-speaking audio before
        # a phrase is considered complete
        r.pause_threshold = 0.7
        audio = r.listen(source)
        try:
            print("Recognizing")

            # for listening the command in indian english
            Query = r.recognize_google(audio, language='en-in')

            # for printing the query or the command that we give
            print("the query is printed='", Query, "'")
        except Exception as e:

            # this method is for handling the exception
            # and so that assistant can ask for telling
            # again the command
            print(e) 
            print("Say that again sir")
            return "None"

    return Query
```

**第二步:**制作 Speak 方法，这样我们的程序就可以对我们说话了。

## 蟒蛇 3

```py
def Speak(audio):

    # initial constructor of pyttsx3
    engine = pyttsx3.init()

    # getter and setter method
    voices = engine.getProperty('voices')
    engine.setProperty('voice', voices[1].id)
    engine.say(audio)
    engine.runAndWait()
```

**第三步:**讲述日法

## 蟒蛇 3

```py
def tellDay():

    # the weekday method is a method from datetime
    # library which helps us to an integer
    # corresponding to the day of the week
    # this dictionary will help us to map the
    # integer with the day and we will check for
    # the condition and if the condition is true
    # it will return the day
    day = datetime.datetime.today().weekday() + 1

    Day_dict = {1: 'Monday', 2: 'Tuesday', 3: 'Wednesday',
                4: 'Thursday', 5: 'Friday', 6: 'Saturday',
                7: 'Sunday'}

    if day in Day_dict.keys():
        day_of_the_week = Day_dict[day]
        print(day_of_the_week)
        Speak("The day is " + day_of_the_week)
```

**第四步:**帮助我们执行程序的主要方法

## 蟒蛇 3

```py
if __name__ == '__main__':
    command=take_commands()

    if "day" in command:
        tellDay()
```

**整个程序:**

## 蟒蛇 3

```py
import datetime
import pyttsx3
import speech_recognition as sr

def take_commands():

    # Making the use of Recognizer and Microphone
    # Method from Speech Recognition for taking
    # commands
    r = sr.Recognizer()

    with sr.Microphone() as source:
        print('Listening')

        # seconds of non-speaking audio before
        # a phrase is considered complete
        r.pause_threshold = 0.7
        audio = r.listen(source)
        try:
            print("Recognizing")

            # for listening the command in indian english
            Query = r.recognize_google(audio, language='en-in')

            # for printing the query or the command that we give
            print("the query is printed='", Query, "'")
        except Exception as e:

            # this method is for handling the exception
            # and so that assistant can ask for telling
            # again the command
            print(e) 
            print("Say that again sir")
            return "None"

    return Query

def Speak(audio):

    # initial constructor of pyttsx3
    engine = pyttsx3.init()

    # getter and setter method
    voices = engine.getProperty('voices')
    engine.setProperty('voice', voices[1].id)
    engine.say(audio)
    engine.runAndWait()

def tellDay():

    # the weekday method is a method from datetime
    # library which helps us to an integer
    # corresponding to the day of the week
    # this dictionary will help us to map the
    # integer with the day and we will check for
    # the condition and if the condition is true
    # it will return the day
    day = datetime.datetime.today().weekday() + 1

    Day_dict = {1: 'Monday', 2: 'Tuesday', 3: 'Wednesday',
                4: 'Thursday', 5: 'Friday', 6: 'Saturday',
                7: 'Sunday'}

    if day in Day_dict.keys():
        day_of_the_week = Day_dict[day]
        print(day_of_the_week)
        Speak("The day is " + day_of_the_week)

# Driver Code
if __name__ == '__main__':
    command=take_commands()

    if "day" in command:
        tellDay()
```

**输出:**

```py
Listening
Recognizing
the query is printed=' today's day '
Wednesday
```

**注意:**还会创建语音生成的输出。