# 使用 Python 将 HTML 源代码转换为 JSON 对象

> 原文:[https://www . geesforgeks . org/convert-html-source-code-to-JSON-object-use-python/](https://www.geeksforgeeks.org/convert-html-source-code-to-json-object-using-python/)

在这篇文章中，我们将看到如何将一个 HTML 源代码转换成一个 JSON 对象。JSON 对象可以很容易地传输，并且它们得到了大多数现代编程语言的支持。我们可以从 Javascript 中读取 JSON，并轻松地将其解析为 Javascript 对象。Javascript 可以用来为你的网页制作 HTML。

我们将在这篇文章中使用 **xmltojson** 模块。这个模块的解析函数以 HTML 为输入，返回解析后的 JSON 字符串。

> **语法:** xmltojson.parse(xml_input，xml_attribs=True，item_depth=0，item_callback)
> 
> **参数:**
> 
> *   **xml_input** 可以是文件，也可以是字符串。
> *   **如果设置为真，xml_attribs** 将包括属性。否则，如果设置为“假”，则忽略它们。
> *   **item_depth** 是找到 item_callback 函数时调用的子对象的深度。
> *   **item_callback** 是一个回调函数

**环境设置:**

安装所需的模块:

```py
pip install xmltojson
pip install requests
```

**步骤:**

*   导入库

## 蟒蛇 3

```py
import xmltojson
import json
import requests
```

*   获取 HTML 代码并将其保存到文件中。

## 蟒蛇 3

```py
# Sample URL to fetch the html page
url = "https://geeksforgeeks-example.surge.sh"

# Headers to mimic the browser
headers = {
    'User-Agent': 'Mozilla/5.0 (Macintosh; Intel Mac OS X 10_10_1) AppleWebKit/537.36 \
    (KHTML, like Gecko) Chrome/39.0.2171.95 Safari/537.36'
}

# Get the page through get() method
html_response = requests.get(url=url, headers = headers)

# Save the page content as sample.html
with open("sample.html", "w") as html_file:
    html_file.write(html_response.text)
```

*   使用解析函数将这个 HTML 转换成 JSON。打开 HTML 文件，使用 **xmltojson** 模块的解析功能。

## 蟒蛇 3

```py
with open("sample.html", "r") as html_file:
    html = html_file.read()
    json_ = xmltojson.parse(html)
```

*   **json_** 变量包含一个我们可以打印或转储到文件中的 json 字符串。

## 蟒蛇 3

```py
with open("data.json", "w") as file:
    json.dump(json_, file)
```