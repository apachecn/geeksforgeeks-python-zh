# 如何使用 Python 跟踪 ISS(国际空间站)？

> 原文:[https://www . geesforgeks . org/how-track-ISS-international-space-station-use-python/](https://www.geeksforgeeks.org/how-to-track-iss-international-space-station-using-python/)

在本文中，我们将讨论如何跟踪 **ISS(国际空间站)**的当前位置，然后绘制位置图。我们将编写一个脚本，显示国际空间站的当前位置以及船上机组人员的姓名。它在应用编程接口上工作，以经纬度的形式获取国际空间站的当前位置，然后在地图上定位该值。它每 5 秒钟从网站上获取一次值，然后更新纬度和经度的值，因此也移动了**世界地图**上的国际空间站图标。可见的运动很少，但你可以注意到下面 gif 中的运动。这可以通过使用 python 的一些模块来实现，比如 JSON、urllib.requests、Webbrowser、Geocoder 等。许多函数被用来创建这个脚本。

## **所需模块:**

*   **JSON** ***:*** 它是 JavaScript Object notification，python 通过一个名为 JSON 的内置包支持 JSON。它只是类似于 python 中的字典。要使用该模块的功能，请将 JSON 模块导入脚本。

```
pip install jsonlib
```

*   [**海龟**](https://www.geeksforgeeks.org/turtle-programming-python/) **:** 巨蟒海龟库包含了创建我们的设计和图像的所有必要方法和功能。

```
pip install turtle
```

*   [**URL lib**](https://www.geeksforgeeks.org/python-urllib-module/)**:**URL lib . request 是一个用于获取**URL**(统一资源定位符)的 python 模块。这个模块以 urlopen 函数的形式提供了一个非常简单的界面。它结合了几个模块对网址进行预处理，能够使用各种不同的协议获取网址。

```
pip install urllib3
```

*   **时间:**该模块执行多种与时间相关的功能。有关相关功能，请参见日期时间和日历模块。

```
pip install times
```

*   **Webbrowser:** 用户可以使用 Webbrowser 模块查看基于 Web 的文档，该模块提供了高级界面。该模块包括交互式浏览器应用程序的网址打开功能。

```
pip install pycopy-webbrowser
```

*   **地理编码器:**该模块将各种地名描述转换为地球表面的位置。因为每个地理编码提供者都有自己的 JSON 模式，所以有时很难解析它们。在这里，这个模块将帮助我们只使用简单的函数来检索纬度和经度。

```
pip install geocoder
```

## 入门指南

所以现在跟踪国际空间站有一个问题，因为它的速度几乎是 28000 公里/小时。因此，它只需要 90 分钟就可以完成绕地球一周的旋转。以这样的速度，锁定准确的坐标变得相当困难。因此，解决这个问题的应用编程接口来了。API 充当网站和程序之间的中间体，从而为程序提供当前的时间数据。

在我们的案例中，API 将为我们提供国际空间站在地球轨道上的当前位置，因此访问下面的链接作为宇航员信息的 API 链接。

```
url = "http://api.open-notify.org/astros.json" 
```

## **访问数据:**

使用 urllib.request.urlopen()函数打开应用编程接口 url 和 json.loads()。函数从 url 中读取数据。

## 蟒 3

```
import json  
import turtle
import urllib.request 
import time 
import webbrowser 
import geocoder

url = "http://api.open-notify.org/astros.json" 
response = urllib.request.urlopen(url) 
result = json.loads(response.read())
result
```

**输出:**

```
{'people': [{'name': 'Mark Vande Hei', 'craft': 'ISS'},
  {'name': 'Oleg Novitskiy', 'craft': 'ISS'},
  {'name': 'Pyotr Dubrov', 'craft': 'ISS'},
  {'name': 'Thomas Pesquet', 'craft': 'ISS'},
  {'name': 'Megan McArthur', 'craft': 'ISS'},
  {'name': 'Shane Kimbrough', 'craft': 'ISS'},
  {'name': 'Akihiko Hoshide', 'craft': 'ISS'},
  {'name': 'Nie Haisheng', 'craft': 'Tiangong'},
  {'name': 'Liu Boming', 'craft': 'Tiangong'},
  {'name': 'Tang Hongbo', 'craft': 'Tiangong'}],
 'number': 10,
 'message': 'success'}
```

**为宇航员创建. txt 文件信息:**在写入模式下使用 open()函数创建 iss.text 文件，并将结果(宇航员姓名&编号)作为数据写入文件。

## 蟒 3

```
file = open("iss.txt", "w") 
file.write(
  "There are currently " + str(result["number"]) + 
  " astronauts on the ISS: \n\n")

people = result["people"]
for p in people:
    file.write(p['name'] + " - on board" + "\n")
```

## **用户当前纬度&经度:**

使用 geocoder.ip('me ')了解您在纬度和经度方面的当前位置，然后使用将数据写入文件，然后使用 file.close()函数关闭文件。

## 蟒 3

```
# print long and lat
g = geocoder.ip('me') 
file.write("\nYour current lat / long is: " + str(g.latlng))
file.close()
webbrowser.open("iss.txt")
```

## **设置世界地图:**

使用 **turtle.screen()** 功能进入屏幕，然后使用 **screen.setup()** 设置输出窗口的大小和位置。使用**screen . setworld coordinates()**功能设置 x、y 轴上所有 4 个角的坐标，以便当 iss 从 reach 伸出时，它们从另一条边再次出现。

## 蟒蛇 3

```
screen = turtle.Screen()
screen.setup(1280, 720)
screen.setworldcoordinates(-180, -90, 180, 90)
```

使用 **screen.bgpic()** 功能将地图设置为背景图片，使用 **screen.register_shape()** 功能将 iss 图像设置为龟形。将其用作对象，并使用 **iss.shape()函数将其指定为形状，**然后使用 **iss.setheading()** 函数设置形状的角度。**ISS . penip()**功能表示自己的图纸。于是，乌龟停了下来。

**文件可下载:**

*   [地图。gif〔t1〕](https://media.geeksforgeeks.org/wp-content/uploads/20210702113812/map.gif)
*   T8 号房。毒药吗

**代号:**

## 蟒 3

```
# load the world map image
screen.bgpic("images\map.gif")
screen.register_shape("images\iss.gif")
iss = turtle.Turtle()
iss.shape("images\iss.gif")
iss.setheading(45)
iss.penup()
```

使用下面的应用编程接口访问国际空间站的当前状态:

```
 url = "http://api.open-notify.org/iss-now.json"
```

从上面的 API 中提取当前国际空间站的经纬度位置。下面这个脚本在 while 循环中运行，所以你可以看到 ISS 的更新位置和移动，直到你停止程序。

## 蟒 3

```
# load the current status of the ISS in real-time
url = "http://api.open-notify.org/iss-now.json"
response = urllib.request.urlopen(url)
result = json.loads(response.read())

# Extract the ISS location
location = result["iss_position"]
lat = location['latitude']
lon = location['longitude']

# Output lon and lat to the terminal in the 
# float format
lat = float(lat)
lon = float(lon)
print("\nLatitude: " + str(lat))
print("\nLongitude: " + str(lon))
```

通过从 API 刷新经纬度值，每 5 秒更新一次 ISS 的位置。

## 蟒 3

```
# Update the ISS location on the map
iss.goto(lon, lat)

# Refresh each 5 seconds
time.sleep(5)
```