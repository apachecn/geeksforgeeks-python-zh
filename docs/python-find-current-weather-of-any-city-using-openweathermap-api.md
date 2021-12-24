# 使用 Python 中的 OpenWeathermap API 查找任意城市的当前天气

> 原文:[https://www . geeksforgeeks . org/python-find-任何城市的当前天气-使用-openweathermap-api/](https://www.geeksforgeeks.org/python-find-current-weather-of-any-city-using-openweathermap-api/)

OpenWeatherMap 是一项服务，为 web 服务和移动应用的开发者提供天气数据，包括当前天气数据、预报和历史数据。

它提供了一个带有 JSON、XML 和 HTML 端点的应用编程接口，以及一个有限的免费使用层。每分钟拨打超过 60 个电话需要每月从*40 美元*开始付费订阅。访问历史数据需要每月 150 美元的订阅费。用户可以请求当前天气信息、扩展预报和图形地图(显示云量、风速、气压和降水量)。

要使用这个当前天气数据 API，必须需要 API 密钥，可以从[这里](https://openweathermap.org/api)获取。

**注意:**用户需要在 openweathermap.org 创建一个账户，然后才可以使用 API。

### **所需模块:**

```
requests
json
```

下面是实现:

## 蟒蛇 3

```
# Python program to find current
# weather details of any city
# using openweathermap api

# import required modules
import requests, json

# Enter your API key here
api_key = "Your_API_Key"

# base_url variable to store url
base_url = "http://api.openweathermap.org/data/2.5/weather?"

# Give city name
city_name = input("Enter city name : ")

# complete_url variable to store
# complete url address
complete_url = base_url + "appid=" + api_key + "&q=" + city_name

# get method of requests module
# return response object
response = requests.get(complete_url)

# json method of response object
# convert json format data into
# python format data
x = response.json()

# Now x contains list of nested dictionaries
# Check the value of "cod" key is equal to
# "404", means city is found otherwise,
# city is not found
if x["cod"] != "404":

    # store the value of "main"
    # key in variable y
    y = x["main"]

    # store the value corresponding
    # to the "temp" key of y
    current_temperature = y["temp"]

    # store the value corresponding
    # to the "pressure" key of y
    current_pressure = y["pressure"]

    # store the value corresponding
    # to the "humidity" key of y
    current_humidity = y["humidity"]

    # store the value of "weather"
    # key in variable z
    z = x["weather"]

    # store the value corresponding
    # to the "description" key at
    # the 0th index of z
    weather_description = z[0]["description"]

    # print following values
    print(" Temperature (in kelvin unit) = " +
                    str(current_temperature) +
          "\n atmospheric pressure (in hPa unit) = " +
                    str(current_pressure) +
          "\n humidity (in percentage) = " +
                    str(current_humidity) +
          "\n description = " +
                    str(weather_description))

else:
    print(" City Not Found ")
```

**输出:**

```
 Enter city name : Delhi
 Temperature (in kelvin unit) = 312.15
 atmospheric pressure (in hPa unit) = 996
 humidity (in percentage) = 40
 description = haze
```

## **方法 2:**

在第二种方法中，我们将使用下面列出的一些模块和功能:

**1。**这是一个 python 中的库，用于从 HTML 和 XML 文件中提取数据，即用于网页抓取目的。它从页面源代码中生成一个解析树，可以用来以更易读和层次化的方式提取数据。要在系统中安装一个漂亮的汤库，请在终端中使用下面的代码

```
-->> pip install beautifulsoup
```

**2。请求:**这里我们将使用 Python 的请求模块进行 HTTP 请求。要进行安装，请在终端中使用以下代码。

```
-->> pip install requests
```

**3。**这里我们使用**报头**，因为报头包含特定于协议的信息，这些信息放在原始消息之前，即从网站上检索到的消息。

**4。**之后，我们将使用 **get()** 功能，并将谷歌搜索连同城市名称一起传递到其中，以从谷歌检索数据。

然后，我们将使用美丽的输出，并从网站解析所需的 HTML 数据。

**5。**然后我们将使用 **select()** 函数来检索特定信息，如时间、信息、位置，将它们存储在某个变量中，并进一步存储它们。

在所有这些之后，我们将最终打印数据，即存储在变量中的数据。

## 蟒蛇 3

```
from bs4 import BeautifulSoup
import requests
headers = {
    'User-Agent': 'Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/58.0.3029.110 Safari/537.3'}

def weather(city):
    city = city.replace(" ", "+")
    res = requests.get(
        f'https://www.google.com/search?q={city}&oq={city}&aqs=chrome.0.35i39l2j0l4j46j69i60.6128j1j7&sourceid=chrome&ie=UTF-8', headers=headers)
    print("Searching...\n")
    soup = BeautifulSoup(res.text, 'html.parser')
    location = soup.select('#wob_loc')[0].getText().strip()
    time = soup.select('#wob_dts')[0].getText().strip()
    info = soup.select('#wob_dc')[0].getText().strip()
    weather = soup.select('#wob_tm')[0].getText().strip()
    print(location)
    print(time)
    print(info)
    print(weather+"°C")

city = input("Enter the Name of City ->  ")
city = city+" weather"
weather(city)
print("Have a Nice Day:)")

# This code is contributed by adityatri
```

**样本输入:**

```
Mahoba
```

**样本输出:**

```
Enter the Name of City ->  Mahoba
Searching...

Mahoba, Uttar Pradesh
Monday, 12:00 am
Cloudy
27°C
Have a Nice Day:)
```