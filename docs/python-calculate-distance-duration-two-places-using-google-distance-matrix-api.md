# 使用 Python 中的 google 距离矩阵 API 计算两地之间的距离和时长

> 原文:[https://www . geesforgeks . org/python-compute-distance-duration-two-places-using-Google-distance-matrix-API/](https://www.geeksforgeeks.org/python-calculate-distance-duration-two-places-using-google-distance-matrix-api/)

谷歌地图距离矩阵应用编程接口是一项提供旅行距离和到达目的地所需时间的服务。此应用编程接口返回出发地和目的地之间的推荐路线(未详细说明)，该路线由每对路线的持续时间和距离值组成。

要使用这个 API，必须需要 *API 键*，可以从[这里](https://developers.google.com/maps/documentation/distance-matrix/get-api-key)获取。

**所需模块:**

```py
import requests
import json
```

下面是实现:

```py
# importing required libraries
import requests, json

# enter your api key here
api_key ='Your_api_key'

# Take source as input
source = input()

# Take destination as input
dest = input()

# url variable store url 
url ='https://maps.googleapis.com/maps/api/distancematrix/json?'

# Get method of requests module
# return response object
r = requests.get(url + 'origins = ' + source +
                   '&destinations = ' + dest +
                   '&key = ' + api_key)

# json method of response object
# return json format result
x = r.json()

# by default driving mode considered

# print the value of x
print(x)
```

**输出:**

```py
dehradun
haridwar

{'destination_addresses': ['Haridwar, Uttarakhand, India'], 
'origin_addresses': ['Dehradun, Uttarakhand, India'], 'rows': 
[{'elements': [{'distance': {'text': '56.3 km', 'value': 56288}, 
'duration': {'text': '1 hour 40 mins', 'value': 5993},
'status': 'OK'}]}], 'status': 'OK'}

```

#### 使用`googlemaps`模块:

两地距离也可以使用*谷歌地图*模块计算。

命令安装*谷歌地图*模块:

```py
pip install googlemaps
```

```py
# importing googlemaps module
import googlemaps

# Requires API key
gmaps = googlemaps.Client(key='Your_API_key')

# Requires cities name
my_dist = gmaps.distance_matrix('Delhi','Mumbai')['rows'][0]['elements'][0]

# Printing the result
print(my_dist)
```

**输出:**

```py
{'distance': {'text': '1,415 km', 'value': 1415380}, 'duration': {'text': '23 hours 42 mins', 'value': 85306}, 'status': 'OK'}
```

感谢 **[艾西瓦娅. 27](https://auth.geeksforgeeks.org/user/aishwarya.27/articles)** 贡献了这个方法。