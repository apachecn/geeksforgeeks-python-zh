# 使用 Python 中的硒检查 CBSE 结果

> 原文:[https://www . geesforgeks . org/check-cbse-result-use-selenium in-python/](https://www.geeksforgeeks.org/check-cbse-result-using-selenium-in-python/)

**先决条件:** [硒蟒](https://www.geeksforgeeks.org/selenium-python-tutorial/)

在本文中，我们将从他们的网站上抓取 CBSE 结果，并将结果存储在 CSV 文件中。CSV 文件将包含以下信息。

1.  候选人姓名
2.  通过或失败状态
3.  获得的分数

### 需要安装

*   转到命令提示符，并输入:

```
pip install selenium
```

*   完成后，下载一个用于自动化的网络驱动程序。这里，我们将使用来自[http://chromedriver.chromium.org/](http://chromedriver.chromium.org/)的 chromedriver

**进场:**

1.  先去第 12 个网站跟着这个[链接](http://resultsarchives.nic.in/cbseresults/cbseresults2014/class12/cbse122014_total.htm)(这是给 CBSE 板第 12 个成绩 2014 的通行证)。
2.  然后通过紧急 ctrl + shift + I 或进入浏览器设置并手动点击调查细节来点击调查元素。
3.  然后导航到填充辊号的框，然后复制 x_path。
4.  然后导航视图提交按钮，然后复制 x_path。
5.  我们希望将结果存储在 CSV 文件中，然后还导航学生姓名、未通过状态、获得的分数，然后通过脚本自动填写卷号转到下一页查找学生姓名的 x_path、未通过状态、获得分数。

**给出一些截图，按照这个指令一步一步来:**

**第一步:**

![](img/87db658cfbe6d04b3dfa8d97dd5dd60c.png)

**第二步:**

![](img/7d208131582157669a777183b70c388f.png)

**第三步:**

![](img/7e276897707460c0f0ea9ef56ed7a927.png)

**第四步:**

![](img/2a18e2cd1d2c1c3ed7f91a4ffd5e1074.png)

**第五步:**

![](img/081f26a4eeb04839e927bbcd14f0b852.png)

**第六步:**

![](img/6f4a022aca6825b3f6245a6b7199114f.png)

**跟随同样的左三科目**

**下面是实现:**

## 蟒蛇 3

```
from selenium import webdriver
from selenium.webdriver.common.keys import Keys
from selenium.webdriver.support.ui import Select
from selenium.common.exceptions import NoSuchElementException
import csv
import time

# creating csv file
filename = "cbse.csv"

# open csv file to write
f = open(filename, 'w')

# creat header in file
header = "NAME,STATUS,NUM\n"
f.write(header)

# put range of rollnumber
for i in range(9639428, 9639432):

    # use try and exception because if any
    # rollnumber is invalid then whole
    # program is not stop.
    try:
        driver = webdriver.Chrome()

        # link is given above copy and paste
        driver.get(
            "http://resultsarchives.nic.in/cbseresults/cbseresults2014/class12/cbse122014_total.htm")

        # put rollnumber
        driver.find_element_by_xpath(
            '/html/body/table[3]/tbody/tr/td/font/center[2]/form/div[1]/center/p/input[1]').send_keys(i)

        # view result xpath
        driver.find_element_by_xpath(
            '/html/body/table[3]/tbody/tr/td/font/center[2]/form/div[1]/center/p/input[2]').click()

        # student name
        name = driver.find_element_by_xpath(
            '/html/body/div[2]/table[2]/tbody/tr[2]/td[2]/font/b').text

        # status pass or fail
        status = driver.find_element_by_xpath(
            '/html/body/div[2]/div/center/table/tbody/tr[12]/td[2]/b[1]/font').text

        # first subject find xpath then next 4 subject
        m1 = driver.find_element_by_xpath(
            '/html/body/div[2]/div/center/table/tbody/tr[2]/td[5]/font').text
        m2 = driver.find_element_by_xpath(
            '/html/body/div[2]/div/center/table/tbody/tr[3]/td[5]/font').text
        m3 = driver.find_element_by_xpath(
            '/html/body/div[2]/div/center/table/tbody/tr[4]/td[5]/font').text
        m4 = driver.find_element_by_xpath(
            '/html/body/div[2]/div/center/table/tbody/tr[5]/td[5]/font').text
        m5 = driver.find_element_by_xpath(
            '/html/body/div[2]/div/center/table/tbody/tr[6]/td[5]/font').text

        # sum all marks
        num = str(int(m1)+int(m2)+int(m3)+int(m4)+int(m5))

        # all details fill into file
        f.write(name+","+status[9:]+","+num+"\n")
        driver.close()

    except NoSuchElementException as exception:
        continue

f.close()
```

**输出:**

![](img/c0fde3b4cd36bb674e7577bc0d3810d5.png)