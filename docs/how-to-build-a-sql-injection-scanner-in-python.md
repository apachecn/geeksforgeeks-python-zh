# 如何用 Python 构建一个 SQL 注入扫描程序？

> 原文:[https://www . geesforgeks . org/如何构建一个 sql 注入式 python 扫描仪/](https://www.geeksforgeeks.org/how-to-build-a-sql-injection-scanner-in-python/)

一般来说，SQLi 是最普遍和最危险的代码插入技术。SQL 攻击意在向数据库服务器发送恶意的 SqL 命令。最常见的攻击目标是知识的批量提取。攻击者可以转储包含数千条客户记录的数据库表。根据环境的不同，SQL 注入还可能被利用来切换或删除数据、执行任意操作系统命令或发起拒绝服务(DoS)攻击。

## **用 Python 构建 SQL 注入扫描器**

使用下面的方法，我们将首先提取网络表单，因为 SQL 注入是通过用户输入实现的。然后，我们将检查网页中是否有 SQL 错误，这在检查 SQL 注入攻击时会很有用，最后，我们将在 HTML 表单上测试它。

为此，我们将需要请求和美丽的包。

### 方法

*   导入模块
*   现在，初始化 HTTP 会话，并为您的浏览器设置最新的用户代理
*   现在我们将提取网页表单。
    *   为此，首先，我们将编写一个函数，该函数在给出一个网址后，将向该页面发出请求，并从中提取所有的 HTML 表单标签
    *   然后将这些标签作为列表返回。
    *   之后我们可以使用这个列表。
*   现在，我们将从响应输出中检查获得的页面是否有任何 SQL 漏洞。
*   如果它有任何语法错误，页面是脆弱的。虽然有很多数据库错误，但我们将搜索有限的数据库错误，即 Oracle 和 SQL Server 错误，因为这两个是最常用的。
*   现在，我们将对 HTML 网页中的所有表单应用这种搜索方法来查找错误
*   我们的脚本已经准备好了，现在我们将测试它。
    *   我们将传递我们必须检测 SQL 注入的网址。
    *   因此，我们将通过命令行传递 URL 参数。

**程序:**

## 蟒蛇 3

```py
import requests
from bs4 import BeautifulSoup
import sys
from urllib.parse import urljoin

s = requests.Session()
s.headers["User-Agent"] = "Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/87.0.4280.88 Safari/537.36"

def get_forms(url):
    soup = BeautifulSoup(s.get(url).content, "html.parser")
    return soup.find_all("form")

def form_details(form):
    detailsOfForm = {}
    action = form.attrs.get("action").lower()
    method = form.attrs.get("method", "get").lower()
    inputs = []

    for input_tag in form.find_all("input"):
        input_type = input_tag.attrs.get("type", "text")
        input_name = input_tag.attrs.get("name")
        input_value = input_tag.attrs.get("value", "")
        inputs.append(
            {"type": input_type, "name": input_name, "value": input_value}
        )

    detailsOfForm["action"] = action
    detailsOfForm["method"] = method
    detailsOfForm["inputs"] = inputs
    return detailsOfForms

def vulnerable(response):
    errors = {"quoted string not properly terminated",
              "unclosed quotation mark after the character string", 
              "you have an error in your sql syntax;"}

    for error in errors:
        if error in response.content.decode().lower():
            return True
    return False

def sql_injection_scan(url):
    forms = get_forms(url)
    print(f"[+] Detected {len(forms)} forms on {url}.")

    for form in forms:
        details = form_details(form)

        for c in "\"'":
            data = {}

            for input_tag in details["inputs"]:
                if input_tag["type"] == "hidden" or input_tag["value"]:
                    data[input_tag["name"]] = input_tag["value"] + c
                elif input_tag["type"] != "submit":
                    data[input_tag["name"]] = f"test{c}"
            url = urljoin(url, form_details["action"])

            if details["method"] == "post":
                res = session.post(url, data=data)
            elif details["method"] == "get":
                res = session.get(url, params=data)
            if vulnerable(res):
                print("SQL Injection attack vulnerability detected in link:", url)
            else:
                print("No SQL Injection vulnerability detected")
                break

if __name__ == "__main__":
    url_arg = "https://www.geeksforgeeks.org/python-programming-language/"
    sql_injection_scan(url_arg)
```

**输出:**

> [+]在[https://www.geeksforgeeks.org/python-programming-language/.](https://www.geeksforgeeks.org/python-programming-language/)检测到 0 个表单