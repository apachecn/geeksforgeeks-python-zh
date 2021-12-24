# 用 Python 自动化 Youtube】

> 原文:[https://www.geeksforgeeks.org/automate-youtube-with-python/](https://www.geeksforgeeks.org/automate-youtube-with-python/)

在本文中，我们将看到如何使用 Python 自动化 **Youtube** 。

## 使用的模块

*   [硒](https://www.geeksforgeeks.org/browser-automation-using-selenium/):通过程序控制网页浏览器
*   [pyttsx3](https://www.geeksforgeeks.org/python-text-to-speech-by-using-pyttsx3/) :是 Python 中的文本到语音转换库
*   [语音识别](https://www.geeksforgeeks.org/speech-recognition-in-python-using-google-speech-api/):语音识别是家庭自动化、人工智能等应用中的一个重要特征
*   [pyaudio](https://www.geeksforgeeks.org/python-convert-speech-to-text-and-text-to-speech/) :用于在各种平台上播放和录制音频

确保您已经记录了 chromedriver 的下载位置(因为它在我们的 python 脚本中使用)。现在下载后提取 zip 文件，请注意提取文件的文件位置，因为我们稍后在 python 代码中需要它。(您可以通过单击属性，然后单击详细信息来找到位置)。

## 方法

*   导入我们安装的库。
*   然后我们必须使用语音识别库接受输入的搜索查询。我们可以通过将语音识别库的一个实例作为 sr.Recognizer()来实现这一点。
*   在此之后，调整阈值频率，并将语音输入转换为字符串。
*   然后，主要部分进入图片，我们已经创建了一个函数 automateYoutube()，它从 Youtube 播放所需的视频。
*   在这个函数中，我们使用函数 webdriver 创建驱动程序实例。Chrome()以 chromedriver 的路径为参数。
*   最后，通过右键单击 inspect 搜索栏和，找到搜索栏和搜索按钮的名称或 id 或类或 CSS 选择器。搜索按钮。
*   现在，只需调用 **automateYoutube()** 函数查看输出。
*   现在，我们必须自动播放/暂停按钮，为此，我们再次使用 selenium 找到播放/暂停按钮的 CSS 选择器。

### 下面是完整的实现

## 蟒蛇 3

```
from selenium import webdriver
from selenium.webdriver.support.ui import WebDriverWait
from selenium.webdriver.support import expected_conditions
from selenium.webdriver.common.by import By
from selenium.webdriver.common.keys import Keys
import speech_recognition as sr
import pyttsx3
import time

def automateYoutube(searchtext):

    # giving the path of chromedriver to selenium webdriver
    path = "C:\\Users\\hp\\Downloads\\chromedriver"

    url = "https://www.youtube.com/"

    # opening the youtube in chromedriver
    driver = webdriver.Chrome(path)
    driver.get(url)

    # find the search bar using selenium find_element function
    driver.find_element_by_name("search_query").send_keys(searchtext)

    # clicking on the search button
    driver.find_element_by_css_selector(
        "#search-icon-legacy.ytd-searchbox").click()

    # For finding the right match search
    WebDriverWait(driver, 0).until(expected_conditions.title_contains(MyText))

    # clicking on the match search having same as in searched query
    WebDriverWait(driver, 30).until(
        expected_conditions.element_to_be_clickable((By.ID, "img"))).click()

    # while(True):
    #     pass

speak = sr.Recognizer()
try:
    with sr.Microphone() as speaky:

        # adjust the energy threshold based on
        # the surrounding noise level
        speak.adjust_for_ambient_noise(speaky, duration=0.2)
        print("listening...")

        # listens for the user's input
        searchquery = speak.listen(speaky)

        # Using ggogle to recognize audio
        MyText = speak.recognize_google(searchquery)
        MyText = MyText.lower()

except sr.RequestError as e:
    print("Could not request results; {0}".format(e))

except sr.UnknownValueError:
    print("unknown error occured")

# Calling thr function
automateYoutube(MyText)
```

**输出:**

<video class="wp-video-shortcode" id="video-685105-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210917201748/Automate-Youtube-Video.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20210917201748/Automate-Youtube-Video.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210917201748/Automate-Youtube-Video.mp4)</video>