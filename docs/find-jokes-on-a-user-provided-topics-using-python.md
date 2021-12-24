# 使用 Python 查找用户提供主题的笑话

> 原文:[https://www . geesforgeks . org/find-用户提供的话题上的笑话-使用-python/](https://www.geeksforgeeks.org/find-jokes-on-a-user-provided-topics-using-python/)

**先决条件:**

*   [Http 请求方法–Python 请求](https://www.geeksforgeeks.org/http-request-methods-python-requests/)
*   [pyfigures](https://www.geeksforgeeks.org/python-ascii-art-using-pyfiglet-module/)

Python [请求](https://www.geeksforgeeks.org/http-request-methods-python-requests/#:~:text=Related%20Articles&text=Python%20requests%20module%20has%20several,between%20a%20client%20and%20server.)模块帮助我们对指定的 URL 进行 Http 请求。在本文中，我们将对以下 url 发出 json 请求:[https://icanhazdadjoke.com/](https://icanhazdadjoke.com/)并开发一个项目，其中用户输入任何单词，输出将是与该单词相关的笑话。

我们将使用应用编程接口(库请求)使用用户输入的关键字搜索笑话，如果我们在输入的关键字上获得多个结果，那么其中一个笑话将随机显示。

### 使用的模块

*   **请求**模块允许我们使用 python 发送 Https 请求
*   **pyfiglet** 模块将 ASCII 文本转换为 ASCII 艺术字体
*   **终端颜色**模块帮助我们格式化输出终端的颜色
*   **随机数**模块在 Python 中生成随机数

### 方法

*   导入模块
*   添加标题，在 for 中指定，是要存储的数据，默认情况下是 html 文本(这里，我们以 JSON 格式获取数据)
*   要求用户输入
*   将输入作为搜索元素传递，以从网址中检索数据
*   打印检索到的数据。

**程序:**

## 蟒蛇 3

```
import requests
import pyfiglet
import termcolor
from random import choice

header = pyfiglet.figlet_format("Find a joke!")
header = termcolor.colored(header, color="white")
print(header)

term = input("Let me tell you a joke! Give me a topic: ")

response_json = requests.get("https://icanhazdadjoke.com/search",
                             headers={"Accept": "application/json"}, params={"term": term}).json()

results = response_json["results"]

total_jokes = response_json["total_jokes"]
print(total_jokes)

if total_jokes > 1:
    print(f"I've got {total_jokes} jokes about {term}. Here's one:\n", choice(
        results)['joke'])

elif total_jokes == 1:
    print(f"I've got one joke about {term}. Here it is:\n", results[0]['joke'])

else:
    print(f"Sorry, I don't have any jokes about {term}! Please try again.")
```

**输出**

![](img/b6608c257d08581e33d6900b76a9e968.png)

关键词是香蕉，相关的笑话之一就显示出来了