# Python |使用谷歌地理编码 API 计算地点的地理坐标

> 原文:[https://www . geesforgeks . org/python-计算-地理坐标-地点-使用-谷歌-地理编码-api/](https://www.geeksforgeeks.org/python-calculate-geographic-coordinates-places-using-google-geocoding-api/)

地理编码是将地址转换为地理坐标(如纬度和经度)的过程，可用于在地图上标记位置。

要使用谷歌地图地理编码应用编程接口，必须需要一个应用编程接口密钥，可以从这里的获得。

**所需模块:**

```
import requests
import json 
```

下面是实现:

```
# Python program to calculate geographic
# coordinates of places using google
# geocoding API

# importing required modules
import requests, json

# enter your api key here
api_key = 'Your_api_key'

# url variable store url
url = 'https://maps.googleapis.com/maps/api/geocode/json?'

# take place as input
place = input()

# get method of requests module
# return response object
res_ob = requests.get(url + 'address =' +
                place + '&key =' + api_key)

# json method of response object
# convert json format data 
# into python format data.
x = res_ob.json()

# print the vale of x
print(x)
```

**输出:**

```
*Dehradun*

{'results': [{'address_components': [{'long_name': 'Dehradun', 'short_name': 'Dehradun', 'types': ['locality', 'political']}, {'long_name': 'Dehradun', 'short_name': 'Dehradun', 'types': ['administrative_area_level_2', 'political']}, {'long_name': 'Uttarakhand', 'short_name': 'UK', 'types': ['administrative_area_level_1', 'political']}, {'long_name': 'India', 'short_name': 'IN', 'types': ['country', 'political']}], 'formatted_address': 'Dehradun, Uttarakhand, India', 'geometry': {'bounds': {'northeast': {'lat': 30.4041936, 'lng': 78.1089305}, 'southwest': {'lat': 30.2466633, 'lng': 77.92533879999999}}, 'location': {'lat': 30.3164945, 'lng': 78.03219179999999}, 'location_type': 'APPROXIMATE', 'viewport': {'northeast': {'lat': 30.4041936, 'lng': 78.1089305}, 'southwest': {'lat': 30.2466633, 'lng': 77.92533879999999}}}, 'place_id': 'ChIJr4jIVsMpCTkRmYdRMsBiNUw', 'types': ['locality', 'political']}], 'status': 'OK'}

```