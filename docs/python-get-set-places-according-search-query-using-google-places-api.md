# Python |使用 Google Places API

根据搜索查询获取一组地点

> 原文:[https://www . geesforgeks . org/python-get-set-places-resident-search-query-use-Google-places-API/](https://www.geeksforgeeks.org/python-get-set-places-according-search-query-using-google-places-api/)

**谷歌地点应用编程接口网络服务**允许用户查询各种类别的地点信息，如机构、主要兴趣点、地理位置等。人们可以通过邻近或文本字符串来搜索地点。地点搜索返回地点列表以及每个地点的摘要信息；通过“地点详细信息”查询可以获得更多信息。

这里使用的是 Google Places Api 的文本搜索服务，这是一个基于字符串返回一组地点信息的 web 服务。例如“德里的酒店”或“奥沙瓦附近的鞋店”。该服务以匹配文本字符串和任何已设置的位置偏差的位置列表作为响应。

要使用这项服务，用户必须需要一个应用编程接口密钥，这个密钥可以从[这里的](https://developers.google.com/places/web-service/get-api-key)获得。

让我们尝试使用 Python 来使用这个 API 服务。将要使用的模块是`requests` 和`json`。

下面是实现:

```py
# Python program to get a set of 
# places according to your search 
# query using Google Places API

# importing required modules
import requests, json

# enter your api key here
api_key = 'Your_API_key'

# url variable store url
url = "https://maps.googleapis.com/maps/api/place/textsearch/json?"

# The text string on which to search
query = input('Search query: ')

# get method of requests module
# return response object
r = requests.get(url + 'query=' + query +
                        '&key=' + api_key)

# json method of response object convert
#  json format data into python format data
x = r.json()

# now x contains list of nested dictionaries
# we know dictionary contain key value pair
# store the value of result key in variable y
y = x['results']

# keep looping upto length of y
for i in range(len(y)):

    # Print value corresponding to the
    # 'name' key at the ith index of y
    print(y[i]['name'])
```

**输出:**

```py
Search query: Hotels in delhi

ITC Maurya
Le Meridien New Delhi
The Imperial New Delhi
Radisson Blu Hotel New Delhi Paschim Vihar
The Lalit New Delhi
Crowne Plaza New Delhi Rohini
Shangri-La's Eros Hotel, New Delhi
Pride Plaza Hotel Aerocity, New Delhi
The Claridges
The Leela Ambience Convention Hotel, Delhi
Radisson Blu Plaza Delhi Airport
Hotel City Park
Radisson Blu New Delhi Dwarka
The Ashok Hotel
Novotel New Delhi Aerocity
Mapple Emerald
The Metropolitan Hotel and Spa
The Umrao
Pullman New Delhi Aerocity
Welcome Hotel Dwarka

```