# 使用 Python 的亚马逊产品可用性检查器

> 原文:[https://www . geesforgeks . org/Amazon-product-availability-checker-use-python/](https://www.geeksforgeeks.org/amazon-product-availability-checker-using-python/)

众所周知，Python 是一种多用途语言，广泛用于脚本编写。它的用途不仅仅局限于解决复杂的计算，还包括日常生活任务的自动化。假设我们想跟踪任何*亚马逊产品可用性*并在产品可用性发生变化时抓住交易，并通过电子邮件通知用户可用性。为此编写一个 Python 脚本将会非常有趣。
**注意:**运行脚本前安装所需的库(按照代码)。此外，请注意，如果产品目前不可用，则不会向用户发送电子邮件。 *Asin Id* 应该由用户为他想要跟踪的产品提供。

> **所用各模块的工作:**
> **- >请求:**用于发出 HTTP get 和 post 请求
> **- >时间:**用于查找当前时间，等待，休眠
> **- >调度:**用于调度某个功能在间隔后再次运行。它类似于 JavaScript 中的“setInterval”功能。
> **- > smptlib:** 用于使用 Python 发送邮件。

**以下是上述项目的实施:**

## 蟒蛇 3

```py
# Python script for Amazon product availability checker
# importing libraries
from lxml import html
import requests
from time import sleep
import time
import schedule
import smtplib

# Email id for who want to check availability
receiver_email_id = "EMAIL_ID_OF_USER"

def check(url):
    headers = {'User-Agent': 'Mozilla/5.0 (X11; Linux x86_64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/42.0.2311.90 Safari/537.36'}

    # adding headers to show that you are
    # a browser who is sending GET request
    page = requests.get(url, headers = headers)
    for i in range(20):
        # because continuous checks in
        # milliseconds or few seconds
        # blocks your request
        sleep(3)

        # parsing the html content
        doc = html.fromstring(page.content)

        # checking availability
        XPATH_AVAILABILITY = '//div[@id ="availability"]//text()'
        RAw_AVAILABILITY = doc.xpath(XPATH_AVAILABILITY)
        AVAILABILITY = ''.join(RAw_AVAILABILITY).strip() if RAw_AVAILABILITY else None
        return AVAILABILITY

def sendemail(ans, product):
    GMAIL_USERNAME = "YOUR_GMAIL_ID"
    GMAIL_PASSWORD = "YOUR_GMAIL_PASSWORD"

    recipient = receiver_email_id
    body_of_email = ans
    email_subject = product + ' product availability'

    # creates SMTP session
    s = smtplib.SMTP('smtp.gmail.com', 587)

    # start TLS for security
    s.starttls()

    # Authentication
    s.login(GMAIL_USERNAME, GMAIL_PASSWORD)

    # message to be sent
    headers = "\r\n".join(["from: " + GMAIL_USERNAME,
                        "subject: " + email_subject,
                        "to: " + recipient,
                        "mime-version: 1.0",
                        "content-type: text/html"])

    content = headers + "\r\n\r\n" + body_of_email
    s.sendmail(GMAIL_USERNAME, recipient, content)
    s.quit()

def ReadAsin():
    # Asin Id is the product Id which
    # needs to be provided by the user
    Asin = 'B077PWK5BT'
    url = "http://www.amazon.in/dp/" + Asin
    print ("Processing: "+url)
    ans = check(url)
    arr = [
        'Only 1 left in stock.',
        'Only 2 left in stock.',
        'In stock.']
    print(ans)
    if ans in arr:
        # sending email to user if
        # in case product available
        sendemail(ans, Asin)

# scheduling same code to run multiple
# times after every 1 minute
def job():
    print("Tracking....")
    ReadAsin()

schedule.every(1).minutes.do(job)

while True:

    # running all pending tasks/jobs
    schedule.run_pending()
    time.sleep(1)
```

**输出:**

```py
Tracking....
Processing: http://www.amazon.in/dp/B077PWK5BT
Only 1 left in stock.
Tracking....
Processing: http://www.amazon.in/dp/B077PWK5BT
Only 1 left in stock.
Tracking....
Processing: http://www.amazon.in/dp/B077PWK5BT
Only 1 left in stock.
```

请注意，该程序在向用户发送邮件时可能会引发错误(严重安全警报/登录尝试被阻止)，这可以通过修改您正在使用的邮件应用程序中的安全设置来处理。