# 使用硒从刚刚拨号中提取数据

> 原文:[https://www . geesforgeks . org/extract-data-from-just dial-using-selenium/](https://www.geeksforgeeks.org/extract-data-from-justdial-using-selenium/)

让我们看看如何使用 Selenium 和 Python 从 Justdial 中提取数据。Justdial 是一家通过电话、网站和移动应用程序在印度提供不同服务的本地搜索公司。在本文中，我们将提取以下数据:

*   电话号码
*   名字
*   地址

然后，我们可以将数据保存在 CSV 文件中。

**进场:**

1.  从**硒****铬驱动管理器****熊猫****时间**和 **os** 导入以下模块:**网络驱动程序**。
2.  使用 **driver.get()** 方法，传递想要获取信息的链接。
3.  使用**驱动程序. find _ elements _ by _ class _ name()**方法并传递“存储细节”。
4.  实例化空列表来存储值。
5.  迭代存储细节并开始获取所需的单个细节。
6.  创建用户定义函数 **strings_to_number()** 将提取的字符串转换为数字。
7.  显示详细信息，并根据要求保存为 CSV 文件。

## 蟒蛇 3

```py
# importing the modules
from selenium import webdriver
from webdriver_manager.chrome import ChromeDriverManager
driver = webdriver.Chrome(ChromeDriverManager().install())
import pandas as pd
import time
import os

# driver.get method() will navigate to a page given by the URL address
driver.get("https://www.justdial.com/Delhi/Ceiling-Tile-Dealers-Armstrong/nct-11271379")

# the user-defined function
def strings_to_num(argument):

    switcher = {
        'dc': '+',
        'fe': '(',
        'hg': ')',
        'ba': '-',
        'acb': '0',
        'yz': '1',
        'wx': '2',
        'vu': '3',
        'ts': '4',
        'rq': '5',
        'po': '6',
        'nm': '7',
        'lk': '8',
        'ji': '9'
    }
    return switcher.get(argument, "nothing")

# fetching all the store details
storeDetails = driver.find_elements_by_class_name('store-details')

# instantiating empty lists
nameList = []
addressList = []
numbersList = []

# iterating the storeDetails
for i in range(len(storeDetails)):

    # fetching the name, address and contact for each entry
    name = storeDetails[i].find_element_by_class_name('lng_cont_name').text
    address = storeDetails[i].find_element_by_class_name('cont_sw_addr').text
    contactList = storeDetails[i].find_elements_by_class_name('mobilesv')

    myList = []

    for j in range(len(contactList)):

        myString = contactList[j].get_attribute('class').split("-")[1]

        myList.append(strings_to_num(myString))

    nameList.append(name)
    addressList.append(address)
    numbersList.append("".join(myList))

# initialize data of lists.
data = {'Company Name': nameList,
        'Address': addressList,
        'Phone': numbersList}

# Create DataFrame
df = pd.DataFrame(data)
print(df)

# Save Data as .csv
df.to_csv('demo1.csv', mode = 'a', header = False)
```

**输出:**

<video class="wp-video-shortcode" id="video-506760-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20201030191544/user-30-10-2020-19-12-36.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20201030191544/user-30-10-2020-19-12-36.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20201030191544/user-30-10-2020-19-12-36.mp4)</video>