# 使用 Python 自动搜索堆栈溢出代码中的错误

> 原文:[https://www . geesforgeks . org/auto-search-stackoverflow-for-errors-in-code-use-python/](https://www.geeksforgeeks.org/auto-search-stackoverflow-for-errors-in-code-using-python/)

有没有遇到过复制你被卡住的错误，打开浏览器，粘贴，打开正确的堆栈溢出答案的巨大困难？别担心，这是解决办法！我们要做的是编写一个 Python 脚本，它会自动从代码中检测错误，在 Stack Overflow 上搜索该错误，并打开与我们的错误相关的几个选项卡，这些选项卡之前也已经得到了回答。

## 使用的模块

*   **子流程模块**用于通过创建新流程，通过 Python 代码运行新的应用程序或程序。创建子流程模块的目的是替换操作系统模块中可用的几种方法，这些方法被认为效率不高。
*   [**请求模块**](https://www.geeksforgeeks.org/python-requests-tutorial/) 允许你使用 Python 发送 HTTP 请求。
*   **网页浏览器模块**允许我们启动网页浏览器。

**方法:**我们将脚本分为三部分，即我们将创建如下三个函数:

1.  **execute_return(cmd)** :在第一个函数上，我们要写代码来读取和运行 python 文件，并存储它的输出或错误。
2.  **mak_req(错误):**这个函数将使用 Stack Overflow API 和我们从第一个函数得到的错误进行 HTTP 请求，最后返回 JSON 文件。
3.  **get_urls(json_dict):** 该函数从第二个函数中获取 json，并获取和存储那些被 StackOverflow 标记为“已应答”的解决方案的 URL。最后在浏览器上打开包含 StackOverflow 答案的标签。

**注意:**还有一点，在我们跳转到代码之前，你要清楚[剥离](https://www.geeksforgeeks.org/python-string-strip/)和[拆分](https://www.geeksforgeeks.org/python-string-split/)功能的概念。

## 蟒蛇 3

```
# Import dependencies
from subprocess import Popen, PIPE
import requests
import webbrowser

# We are going to write code to read and run python
# file, and store its output or error.
def execute_return(cmd):
    args = cmd.split()
    proc = Popen(args, stdout=PIPE, stderr=PIPE)
    out, err = proc.communicate()
    return out, err

# This function will make an HTTP request using StackOverflow
# API and the error we get from the 1st function and finally
# returns the JSON file.
def mak_req(error):
    resp = requests.get("https://api.stackexchange.com/" +
                        "/2.2/search?order=desc&tagged=python&sort=activity&intitle={}&site=stackoverflow".format(error))
    return resp.json()

# This function takes the JSON from the 2nd function, and
# fetches and stores the URLs of those solutions which are
# marked as "answered" by StackOverflow. And then finally
# open up the tabs containing answers from StackOverflow on
# the browser.
def get_urls(json_dict):
    url_list = []
    count = 0

    for i in json_dict['items']:
        if i['is_answered']:
            url_list.append(i["link"])
        count += 1
        if count == 3 or count == len(i):
            break

    for i in url_list:
        webbrowser.open(i)

# Below line will go through the provided python file
# And stores the output and error.
out, err = execute_return("python C:/Users/Saurabh/Desktop/test.py")

# This line is used to store that part of error we are interested in.
error = err.decode("utf-8").strip().split("\r\n")[-1]
print(error)

# A simple if condition, if error is found then execute 2nd and
# 3rd function, otherwise print "No error".
if error:
    filter_error = error.split(":")
    json1 = mak_req(filter_error[0])
    json2 = mak_req(filter_error[1])
    json = mak_req(error)
    get_urls(json1)
    get_urls(json2)
    get_urls(json)

else:
    print("No error")
```

**输出:**

<video class="wp-video-shortcode" id="video-563355-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210215111934/Auto-error-Checking-and-get-answered-solution-from-Stack-Overflow-using-Python.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20210215111934/Auto-error-Checking-and-get-answered-solution-from-Stack-Overflow-using-Python.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210215111934/Auto-error-Checking-and-get-answered-solution-from-Stack-Overflow-using-Python.mp4)</video>