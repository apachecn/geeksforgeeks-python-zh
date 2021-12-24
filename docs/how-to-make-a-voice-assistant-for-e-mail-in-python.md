# 如何用 Python 制作电子邮件语音助手？

> 原文:[https://www . geesforgeks . org/如何用 python 制作电子邮件语音助手/](https://www.geeksforgeeks.org/how-to-make-a-voice-assistant-for-e-mail-in-python/)

众所周知，电子邮件对于沟通来说非常重要，因为每个专业的沟通都可以通过电子邮件来完成，收发邮件的最佳服务是众所周知的 **GMAIL** 。Gmail 是谷歌开发的免费电子邮件服务。用户可以在网络上使用第三方程序访问 Gmail，这些程序通过 POP 或 IMAP 协议同步电子邮件内容。

要连接 Gmail 和语音助手，我们必须使用 Gmail 应用编程接口。在本文中，我们将看到如何通过发出语音命令来发送和检查电子邮件。Gmail 应用编程接口允许您查看和管理 Gmail 邮箱数据，如线程、邮件和标签。更多关于 Gmail API 的信息可以在这里找到- [Gmail API](https://developers.google.com/gmail/api/reference/rest) 。

**要求:**

*   Python(3 或更高版本)
*   Gmail 账户
*   谷歌应用编程接口客户端
*   pyttsx 3 模块
*   语音识别模块

**安装:**

通过运行以下命令安装库:

> pip 安装 Google API python 客户端 Google auth-httplib 2 Google auth-oathlib

运行这个或 pyttsx3:

```py
pip install pyttsx3
```

运行此程序进行语音识别:

```py
pip install SpeechRecognition
```

现在需要设置一个谷歌云控制台来与 Gmail 应用编程接口交互。这很容易做到。你可以找到如何设置[谷歌云控制台的信息。](https://www.geeksforgeeks.org/how-to-read-emails-from-gmail-using-gmail-api-in-python/)

设置好谷歌云控制台后，我们只需要制定一个方法来构建一个语音助手来大声说出电子邮件。

方法:

*   导入所需模块。
*   创建以下功能:
    *   speak():此功能将帮助我们的助理大声说话。
    *   get_audio():该功能将帮助助手获取用户的输入。
    *   check _ mails():此功能用于检查收件箱主要部分的未读邮件。
*   调用上面创建的函数。

**下面是 Python 中的实现。**

## 蟒蛇 3

```py
from __future__ import print_function
import datetime
import pickle
import os.path
from googleapiclient.discovery import build
from google_auth_oauthlib.flow import InstalledAppFlow
from google.auth.transport.requests import Request
import os
import pyttsx3
import speech_recognition as sr
from datetime import date

# If modifying these scopes, delete the file token.pickle .
# if you run this for the firs
# t time it will take you to gmail to choose your account
SCOPES = ["https://www.googleapis.com/auth/gmail.readonly"]

def speak(text):
    engine=pyttsx3.init()
    voices = engine.getProperty('voices')
    engine.setProperty('voice', voices[1].id)
    rate = engine.getProperty('rate')

    engine.setProperty('rate', rate-20)

    engine.say(text)
    engine.runAndWait()

speak("Welcome to mail service")

def get_audio():
    r=sr.Recognizer()
    with sr.Microphone() as source:
        r.pause_threshold = 1
        r.adjust_for_ambient_noise(source, duration=1)
        audio=r.listen(source)
        said=""

    try:
        said=r.recognize_google(audio)
        print(said)

    except:
        speak("Didn't get that")

    return said.lower()

def authenticate_gmail():
    """Shows basic usage of the Gmail API.
    Lists the user's Gmail labels.
    """
    creds = None

    # The file token.pickle stores the user's 
    # access and refresh tokens, and is
    # created automatically when the authorization 
    # flow completes for the first
    # time.
    if os.path.exists('token.pickle'):
        with open('token.pickle', 'rb') as token:
            creds = pickle.load(token)

    # If there are no (valid) credentials available,
    # let the user log in.
    if not creds or not creds.valid:
        if creds and creds.expired and creds.refresh_token:
            creds.refresh(Request())
        else:
            flow = InstalledAppFlow.from_client_secrets_file(
                'credentials.json', SCOPES)
            creds = flow.run_local_server(port = 0)

        # Save the credentials for the next run
        with open('token.pickle', 'wb') as token:
            pickle.dump(creds, token)

    service = build('gmail', 'v1', credentials=creds)
    return service

def check_mails(service):

    # fetching emails of today's date
    today = (date.today())  

    today_main = today.strftime('%Y/%m/%d')

    # Call the Gmail API
    results = service.users().messages().list(userId = 'me',
                                              labelIds=["INBOX","UNREAD"],
                                              q="after:{0} and category:Primary".format(today_main)).execute()
    # The above code will get emails from primary 
    # inbox which are unread
    messages = results.get('messages',[])

    if not messages:

        # if no new emails
        print('No messages found.')   
        speak('No messages found.')
    else:
        m=""

        # if email found
        speak("{} new emails found".format(len(messages)))  

        speak("if you want to read any particular email just type read ")
        speak("and for not reading type leave ")
        for message in messages:

            msg=service.users().messages().get(userId='me',
                                               id = message['id'], format = 'metadata').execute() 

            for add in msg['payload']['headers']:
                if add['name']=="From":

                    # fetching sender's email name
                    a=str(add['value'].split("<")[0])
                    print(a)

                    speak("email from"+a)
                    text=input()

                    if text == "read":  

                        print(msg['snippet'])

                        # speak up the mail
                        speak(msg['snippet']) 

                    else:
                        speak("email passed")

SERVICE2=authenticate_gmail()
check_mails(SERVICE2)
```

**输出:**

<video class="wp-video-shortcode" id="video-580115-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210323095652/My-Video.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20210323095652/My-Video.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210323095652/My-Video.mp4)</video>