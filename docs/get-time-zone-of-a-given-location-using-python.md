# 使用 Python 获取给定位置的时区

> 原文:[https://www . geeksforgeeks . org/get-给定位置的时区-使用-python/](https://www.geeksforgeeks.org/get-time-zone-of-a-given-location-using-python/)

在本文中，我们将了解如何从给定位置获取时区。**时区查找器**模块能够离线查找地球上任意一点(坐标)的时区。在开始之前，我们需要安装这个模块。

### 需要的模块

1.  **时区查找器:**这个模块没有内置 Python。要安装此软件，请在终端中键入以下命令。

```py
pip install timezonefinder

```

*   **地质:**。geopy 使 Python 开发人员可以轻松定位世界各地的地址、城市、国家和地标的坐标。要安装 Geopy 模块，请在您的终端中运行以下命令。

```py
pip install geopy

```

**我们用**一步一步来理解这个模块

**步骤 1:** 导入时区查找器模块

## 蟒蛇 3

```py
from timezonefinder import TimezoneFinder
```

**第二步:**制作一个时区查找器的对象。

## 蟒蛇 3

```py
# object creation
obj = TimezoneFinder()
```

**步骤 3:** 在 timezone_at()方法中传递纬度和经度，并返回给定位置的时区。

## 蟒蛇 3

```py
# pass the longitude and latitude
# in timezone_at and
# it return time zone 
latitude = 25.6093239
longitude = 85.1235252
obj.timezone_at(lng=latitude, lat=longitude)
```

**输出:**

```py
'Asia/Kolkata'

```

**现在让我们编写一个脚本来获取具有特定位置的时区。**

**进场:**

*   导入模块
*   初始化 Indigm API 以从输入字符串中获取位置。
*   使用 geo cator . geo code()函数获取经纬度。
*   在 timezone_at()方法中传递纬度和经度，它会返回给定位置的时区。

**代码:**

## 蟒蛇 3

```py
# importing module
from geopy.geocoders import Nominatim
from timezonefinder import TimezoneFinder

# initialize Nominatim API
geolocator = Nominatim(user_agent="geoapiExercises")

# input as a geek
lad = "Dhaka"
print("Location address:", lad)

# getting Latitude and Longitude
location = geolocator.geocode(lad)

print("Latitude and Longitude of the said address:")
print((location.latitude, location.longitude))

# pass the Latitude and Longitude
# into a timezone_at
# and it return timezone
obj = TimezoneFinder()

# returns 'Europe/Berlin'
result = obj.timezone_at(lng=location.longitude, lat=location.latitude)
print("Time Zone : ", result)
```

**输出:**

```py
Location address: Dhaka
Latitude and Longitude of the said address:
(23.810651, 90.4126466)
Time Zone :  Asia/Dhaka

```