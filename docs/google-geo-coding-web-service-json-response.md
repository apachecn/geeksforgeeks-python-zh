# 谷歌地理编码 Web 服务(JSON 响应)

> 原文:[https://www . geesforgeks . org/Google-geo-coding-web-service-JSON-response/](https://www.geeksforgeeks.org/google-geo-coding-web-service-json-response/)

先决条件:[Python 中的 JSON 格式](https://www.geeksforgeeks.org/json-formatting-python/)
谷歌有一个优秀的网络服务，允许我们利用他们庞大的地理信息数据库。在这里，我们将使用谷歌地图应用编程接口。在过去，这个地图应用编程接口是免费的，每天有 2500 个请求，但现在他们已经做到了，它的一部分在应用编程接口键后面，你开始不得不使用 OAuth 之类的东西。我们可以向他们的地理编码应用编程接口提交一个地理搜索字符串，比如“Ann Arbor，MI”，并让谷歌返回它对我们可能在地图上哪里找到我们的搜索字符串的最佳猜测，并告诉我们附近的地标。

地理编码服务是免费的，但费率有限，因此您不能在商业应用程序中无限制地使用该应用编程接口。但是如果您有一些最终用户在自由格式输入框中输入位置的调查数据，您可以使用这个应用编程接口很好地清理您的数据。

*当你使用像谷歌地理编码 API 这样的免费 API 时，你需要尊重地使用这些资源。如果太多人滥用这项服务，谷歌可能会放弃或大幅削减其免费服务。*

您可以阅读该服务的在线文档，但它非常简单，您甚至可以通过在浏览器中键入以下网址来使用浏览器进行测试:
[http://maps.googleapis.com/maps/api/geocode/json?地址=安+阿伯%2C+MI](http://maps.googleapis.com/maps/api/geocode/json?address=Ann+Arbor%2C+MI)

在将网址粘贴到浏览器之前，请确保打开网址并删除网址中的任何空格。

下面是一个简单的应用程序，提示用户输入搜索字符串，调用谷歌地理编码应用编程接口，并从返回的 JSON 中提取信息。

```
# Libraries used to grab the URL web stuff and import json
import urllib.request, urllib.parse, urllib.error
import json

# Note that Google is increasingly requiring keys
# for this API
# service URL for Google Maps API
serviceurl = 'http://maps.googleapis.com/maps/api/geocode/json?'

while True:
    address = input('Enter location: ')
    if len(address) < 1: break

    # Concatenate the serviceurl and urllib.parse.urlencode
    # which give a dictonary of address equal and this bit 
    # right here
    url = serviceurl + urllib.parse.urlencode(
        {'address': address})

    print('Retrieving', url)

    # urlopen() to get a handle
    uh = urllib.request.urlopen(url)
    # Read the whole document in UTF-8
    data = uh.read().decode()
    print('Retrieved', len(data), 'characters')

    # Load internal strings
    try:
        js = json.loads(data)
    except:
        js = None
    # If false then quit and print data
    if not js or 'status' not in js or js['status'] != 'OK':
        print('==== Failure To Retrieve ====')
        print(data)
        continue

    # Call json dump and print it with an indent of four
    print(json.dumps(js, indent = 4))

    # Parsing and printing
    lat = js["results"][0]["geometry"]["location"]["lat"]
    lng = js["results"][0]["geometry"]["location"]["lng"]
    print('lat', lat, 'lng', lng)
    location = js['results'][0]['formatted_address']
    print(location)
```

输出:

```

Enter location: Dehradun
Retrieving http://maps.googleapis.com/maps/api/geocode/json?address=dehradun
Retrieved 1743 characters
{
    "results": [
        {
            "address_components": [
                {
                    "long_name": "Dehradun",
                    "short_name": "Dehradun",
                    "types": [
                        "locality",
                        "political"
                    ]
                },
                {
                    "long_name": "Dehradun",
                    "short_name": "Dehradun",
                    "types": [
                        "administrative_area_level_2",
                        "political"
                    ]
                },
                {
                    "long_name": "Uttarakhand",
                    "short_name": "UK",
                    "types": [
                        "administrative_area_level_1",
                        "political"
                    ]
                },
                {
                    "long_name": "India",
                    "short_name": "IN",
                    "types": [
                        "country",
                        "political"
                    ]
                }
            ],
            "formatted_address": "Dehradun, Uttarakhand, India",
            "geometry": {
                "bounds": {
                    "northeast": {
                        "lat": 30.4041936,
                        "lng": 78.1089305
                    },
                    "southwest": {
                        "lat": 30.2466633,
                        "lng": 77.92533879999999
                    }
                },
                "location": {
                    "lat": 30.3164945,
                    "lng": 78.03219179999999
                },
                "location_type": "APPROXIMATE",
                "viewport": {
                    "northeast": {
                        "lat": 30.4041936,
                        "lng": 78.1089305
                    },
                    "southwest": {
                        "lat": 30.2466633,
                        "lng": 77.92533879999999
                    }
                }
            },
            "place_id": "ChIJr4jIVsMpCTkRmYdRMsBiNUw",
            "types": [
                "locality",
                "political"
            ]
        }
    ],
    "status": "OK"
}
lat 30.3164945 lng 78.03219179999999
Dehradun, Uttarakhand, India

```

该程序获取搜索字符串，并使用搜索字符串作为正确编码的参数构建一个 URL，然后使用 urllib 从 Google 地理编码 API 中检索文本。与固定的网页不同，我们获得的数据取决于我们发送的参数和存储在谷歌服务器中的地理数据。
一旦我们检索到 json 数据，我们就用 JSON 库解析它，并做一些检查，以确保我们收到了良好的数据，然后提取我们正在寻找的信息。