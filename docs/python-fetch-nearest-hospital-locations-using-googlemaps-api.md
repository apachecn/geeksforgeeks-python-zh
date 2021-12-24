# Python |使用谷歌地图 API 获取最近的医院位置

> 原文:[https://www . geesforgeks . org/python-fetch-最近的医院-位置-使用-谷歌地图-api/](https://www.geeksforgeeks.org/python-fetch-nearest-hospital-locations-using-googlemaps-api/)

如果你想知道如何使用你当前的位置获取最近的地方(餐馆、医院、实验室、咖啡馆等)，这可以使用 Python 和谷歌地图应用编程接口来实现。在本文中，我们将使用谷歌地图应用编程接口，使用 Python 查找最近的医院位置。
可以使用谷歌开发者控制台[生成 API Key。](https://cloud.google.com/maps-platform/places/?apis=places)那么你应该按照那里的步骤制作一个应用编程接口密钥。

**实施:**

*   在运行代码之前安装所需的 python 库:googleplaces、requests
*   创建一个谷歌地图应用编程接口键到这个[链接](https://cloud.google.com/maps-platform/places/?apis=places)。
*   将 Google Places 构造函数初始化为:*Google _ Places = Google Places(API _ KEY)*
*   调用这个函数*Google _ places . near _ search*参数如纬度、经度、半径和类型:{医院、赌场、酒吧、咖啡馆等}并将输出存储在一个变量中。用户可以在参数中给出自己的经纬度。
*   搜索结果将属于“googleplaces”类。地方。
*   属性的值可以像经度、纬度、名称

下面是实现代码:

## 蟒蛇 3

```py
# Importing required libraries
from googleplaces import GooglePlaces, types, lang
import requests
import json

# This is the way to make api requests
# using python requests library

# send_url = 'http://freegeoip.net/json'
# r = requests.get(send_url)
# j = json.loads(r.text)
# print(j)
# lat = j['latitude']
# lon = j['longitude']

# Generate an API key by going to this location
# https://cloud.google.com /maps-platform/places/?apis =
# places in the google developers

# Use your own API key for making api request calls
API_KEY = 'Your_API_Key'

# Initialising the GooglePlaces constructor
google_places = GooglePlaces(API_KEY)

# call the function nearby search with
# the parameters as longitude, latitude,
# radius and type of place which needs to be searched of
# type can be HOSPITAL, CAFE, BAR, CASINO, etc
query_result = google_places.nearby_search(
        # lat_lng ={'lat': 46.1667, 'lng': -1.15},
        lat_lng ={'lat': 28.4089, 'lng': 77.3178},
        radius = 5000,
        # types =[types.TYPE_HOSPITAL] or
        # [types.TYPE_CAFE] or [type.TYPE_BAR]
        # or [type.TYPE_CASINO])
        types =[types.TYPE_HOSPITAL])

# If any attributions related
# with search results print them
if query_result.has_attributions:
    print (query_result.html_attributions)

# Iterate over the search results
for place in query_result.places:
    # print(type(place))
    # place.get_details()
    print (place.name)
    print("Latitude", place.geo_location['lat'])
    print("Longitude", place.geo_location['lng'])
    print()
```

**输出:**

```py
Sarvodaya Hospital
Latitude 28.4222361
Longitude 77.3167904

Metro Heart Institute with Multispeciality
Latitude 28.4060327
Longitude 77.31803429999999

Asian Institute of Medical Sciences
Latitude 28.4260095
Longitude 77.29998359999999

Rawat Medical Store
Latitude 28.3928114
Longitude 77.30199

Sparsh Hospital
Latitude 28.4449953
Longitude 77.31859759999999

..more results 
```