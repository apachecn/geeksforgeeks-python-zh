# 使用 Python 从经纬度获取城市、州和国家名称

> 原文:[https://www . geesforgeks . org/从使用 python 的经纬度获取城市、州和国家名称/](https://www.geeksforgeeks.org/get-the-city-state-and-country-names-from-latitude-and-longitude-using-python/)

在本文中，我们将编写一个 python 脚本，通过使用 geopy 模块使用纬度和经度来获取城市、州和国家的名称。Geopy 使 Python 开发人员能够轻松定位世界各地的地址、城市、国家和地标的坐标。

要安装 Geopy 模块，请在您的终端中运行以下命令。

```
pip install geopy

```

**进场:**

*   导入地理模块
*   初始化 Indigm API 以从输入字符串中获取位置。
*   使用 geolocator.reverse()函数获取位置。
*   现在从位置实例中提取数据

**我们一步一步来实施:**

**步骤#1:** 导入模块。

## 蟒蛇 3

```
# import module
from geopy.geocoders import Nominatim
```

**步骤#2:** 制作一个 nominam 对象，用 geoapiExercises 参数初始化 Nominatim API。

## 计算机编程语言

```
# initialize Nominatim API 
geolocator = Nominatim(user_agent="geoapiExercises")
```

**步骤#3:** 现在将纬度和经度分配给地理定位器。反向()方法。反向()方法需要参数查询，并且至少接受参数 True _ one，默认情况下为 True。

## 蟒蛇 3

```
# Latitude & Longitude input
Latitude = "25.594095"
Longitude = "85.137566"

location = geolocator.reverse(Latitude+","+Longitude)

# Display
print(location)
```

**输出:**

> 【地点(印度比哈尔邦巴特那农村巴特那拉金德拉纳加尔(25.594023552508407，85.13756080147536，0.0))】

**步骤#4:** 现在从给定的列表中获取信息，并用 raw 函数()解析成字典。

## 蟒蛇 3

```
address = location.raw['address']
print(address)
```

**输出:**

```
{'suburb': 'Rajendra Nagar',
 'city': 'Patna',
 'county': 'Patna Rural',
 'state_district': 'Patna',
 'state': 'Bihar',
 'postcode': '800001',
 'country': 'India',
 'country_code': 'in'}

```

**第 5 步:**现在遍历城市、州和国家名称。

## 蟒蛇 3

```
city = address.get('city', '')
state = address.get('state', '')
country = address.get('country', '')
code = address.get('country_code')
zipcode = address.get('postcode')
print('City : ',city)
print('State : ',state)
print('Country : ',country)
print('Zip Code : ', zipcode)
```

**输出:**

```
City :  Patna
State :  Bihar
Country :  India
Zip Code :  800001

```

**全面实施:**

## 蟒蛇 3

```
# import module
from geopy.geocoders import Nominatim

# initialize Nominatim API
geolocator = Nominatim(user_agent="geoapiExercises")

# Latitude & Longitude input
Latitude = "25.594095"
Longitude = "85.137566"

location = geolocator.reverse(Latitude+","+Longitude)

address = location.raw['address']

# traverse the data
city = address.get('city', '')
state = address.get('state', '')
country = address.get('country', '')
code = address.get('country_code')
zipcode = address.get('postcode')
print('City : ', city)
print('State : ', state)
print('Country : ', country)
print('Zip Code : ', zipcode)
```

**输出:**

```
City :  Patna
State :  Bihar
Country :  India
Zip Code :  800001

```