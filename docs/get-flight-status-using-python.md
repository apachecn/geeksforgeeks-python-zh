# 使用 Python 获取飞行状态

> 原文:[https://www . geesforgeks . org/get-flight-status-use-python/](https://www.geeksforgeeks.org/get-flight-status-using-python/)

**先决条件** [**使用**](https://www.geeksforgeeks.org/implementing-web-scraping-python-beautiful-soup/) 在 Python 中实现网页抓取

在本文中，我们将编写一个 python 脚本来获取飞行状态。

**所需模块:**

*   **bs4:** 美人汤(bs4)是一个从 HTML 和 XML 文件中拉出数据的 Python 库。这个模块没有内置 Python。要安装此软件，请在终端中键入以下命令。

```
pip install bs4
```

*   **请求:** Request 让你可以极其轻松地发送 HTTP/1.1 请求。该模块也没有内置 Python。要安装此软件，请在终端中键入以下命令。

```
pip install requests
```

**进场:**

*   导入模块
*   创建一个网址获取功能
*   现在将信息合并到网址中，并将网址传递给 getdata()函数，并将该数据转换为 HTML 代码。
*   现在从 HTML 代码中找到所需的标签，并遍历结果

**实施:**

## 蟒蛇 3

```
# import module
import requests
from bs4 import BeautifulSoup

# UDF for get HTML code
# from URL

def get_html(Airline_code, Flight_number, Date, Month, Year):
    def getdata(url):
        r = requests.get(url)
        return r.text

    # url
    url = "https://www.flightstats.com/v2/flight-tracker/"+Airline_code + \
        "/"+Flight_number+"?year="+Year+"&month="+Month+"&date="+Date

    # pass the url
    # into getdata function
    htmldata = getdata(url)
    soup = BeautifulSoup(htmldata, 'html.parser')
    return(soup)

# Get Flight number
# from Html code

def flight_no(soup):
    Flight_no = ""

    # Find div tag with
    # unique class name
    for i in soup.find("div", class_="ticket__FlightNumberContainer-s1rrbl5o-4 hgbvHg"):
        Flight_no = Flight_no + (i.get_text()) + " "
    return (Flight_no)

# Get Airport name
# from HTML code

def airport(soup):
    Airport_name = []
    # Find div tag with
    # unique class name
    for i in soup.find_all("div", class_="text-helper__TextHelper-s8bko4a-0 CPamx"):
        Airport_name.append(i.get_text())
    return (Airport_name)

# get status
# from HTML code

def status(soup, Airport_list):
    Time_status = []
    Airport_List = []
    Status_str = []
    Gate = []
    Gate_no = []

    # Find div tag with
    # unique class name
    # to get Gate number
    for data in soup.find_all("div", class_="ticket__TGBLabel-s1rrbl5o-15 gcbyEH text-helper__TextHelper-s8bko4a-0 dfeqpK"):
        Gate.append(data.get_text())
    for data in soup.find_all("div", class_="ticket__TGBValue-s1rrbl5o-16 icyRae text-helper__TextHelper-s8bko4a-0 cCfBRT"):
        Gate_no.append(data.get_text())

    # Get status from
    # html code
    for i in soup.find_all("div", class_="text-helper__TextHelper-s8bko4a-0 bcmzUJ"):
        Status_str.append(i.get_text())
    for i in soup.find_all("div", class_="text-helper__TextHelper-s8bko4a-0 cCfBRT"):
        Time_status.append(i.get_text())

    # traverse the Data
    # from scraping data
    for item in range(4):
        if item == 0:
            print(Airport_list[0])
        if item == 2:
            print("")
            print(Airport_list[1])
        print(Status_str[item] + " : " + Time_status[item])
        print(Gate[item] + " : " + Gate_no[item])
    for item in range(len(Gate)):
        print(Gate[item] + " : " + Gate_no[item])

# Driver code
if __name__ == '__main__':
    # Input Data from geek
    Airline_code = 'G8'
    Flight_number = '134'
    Date = '23'
    Month = '10'
    Year = '2020'

    # Calling the get_html
    # with argument
    # function calling
    soup = get_html(Airline_code, Flight_number, Date, Month, Year)
    print("Flight number : ", flight_no(soup))
    Airport_list = airport(soup)
    status(soup, Airport_list)
```

**输出:**

```
Flight number :  G8 134 GoAir 
Jay Prakash Narayan International Airport
Scheduled : 21:00 IST
Terminal : N/A
Estimated : 21:00 IST
Gate : N/A

Indira Gandhi International Airport
Scheduled : 22:40 IST
Terminal : T2
Estimated : 22:40 IST
Gate : 205
Terminal : N/A
Gate : N/A
Terminal : T2
Gate : 205
```