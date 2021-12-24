# pprint:Python 中的数据漂亮打印机

> 原文:[https://www . geesforgeks . org/pprint-data-俏丽-printer-python/](https://www.geeksforgeeks.org/pprint-data-pretty-printer-python/)

本文是关于 Python 中一个非常有用的内置模块 **pprint** 。

**pprint** 模块提供了以格式良好且可读性更强的方式“漂亮打印”任意 Python 数据结构的能力！

让我们考虑一个例子:

```
# A python code without pprint
import requests

def geocode(address):
    url = "https://maps.googleapis.com/maps/api/geocode/json"
    resp = requests.get(url, params = {'address': address})
    return resp.json()

# calling geocode function
data = geocode('India gate')

# printing json response
print(data)
```

上面的代码是用 JSON 格式的谷歌地图 API 获取一个地方的地理编码信息。

上面程序的输出是这样的:

```
{'status': 'OK', 'results': [{'address_components': [{'long_name': 'Rajpath', 'types': ['route'], 
'short_name': 'Rajpath'}, {'long_name': 'India Gate', 'types': ['political', 'sublocality', 
'sublocality_level_1'], 'short_name': 'India Gate'}, {'long_name': 'New Delhi', 'types': 
['locality', 'political'], 'short_name': 'New Delhi'}, {'long_name': 'New Delhi', 
'types': ['administrative_area_level_2', 'political'], 'short_name': 'New Delhi'}, {'long_name': 
'Delhi', 'types': ['administrative_area_level_1', 'political'], 'short_name': 'DL'}, {'long_name': 
'India', 'types': ['country', 'political'], 'short_name': 'IN'}, {'long_name': '110001', 'types': 
['postal_code'], 'short_name': '110001'}], 'geometry': {'location': {'lng': 77.2295097, 'lat': 28.612912}, 
'viewport': {'northeast': {'lng': 77.2308586802915, 'lat': 28.6142609802915}, 'southwest': {'lng': 
77.22816071970848, 'lat': 28.6115630197085}}, 'location_type': 'APPROXIMATE'}, 'types': 
['establishment', 'point_of_interest'], 'formatted_address': 'Rajpath, India Gate, New Delhi, Delhi 110001, 
India', 'place_id': 'ChIJC03rqdriDDkRXT6SJRGXFwc'}]}
```

如您所见，该输出没有正确缩进，这影响了嵌套数据结构的可读性。

现在，考虑下面的代码:

```
# A python code with pprint
import requests
from pprint import pprint

def geocode(address):
    url = "https://maps.googleapis.com/maps/api/geocode/json"
    resp = requests.get(url, params = {'address': address})
    return resp.json()

# calling geocode function
data = geocode('India gate')

# pretty-printing json response
pprint(data)
```

上面代码的输出看起来是这样的:

```
{'results': [{'address_components': [{'long_name': 'Rajpath',
                                      'short_name': 'Rajpath',
                                      'types': ['route']},
                                     {'long_name': 'India Gate',
                                      'short_name': 'India Gate',
                                      'types': ['political',
                                                'sublocality',
                                                'sublocality_level_1']},
                                     {'long_name': 'New Delhi',
                                      'short_name': 'New Delhi',
                                      'types': ['locality', 'political']},
                                     {'long_name': 'New Delhi',
                                      'short_name': 'New Delhi',
                                      'types': ['administrative_area_level_2',
                                                'political']},
                                     {'long_name': 'Delhi',
                                      'short_name': 'DL',
                                      'types': ['administrative_area_level_1',
                                                'political']},
                                     {'long_name': 'India',
                                      'short_name': 'IN',
                                      'types': ['country', 'political']},
                                     {'long_name': '110001',
                                      'short_name': '110001',
                                      'types': ['postal_code']}],
              'formatted_address': 'Rajpath, India Gate, New Delhi, Delhi '
                                   '110001, India',
              'geometry': {'location': {'lat': 28.612912, 'lng': 77.2295097},
                           'location_type': 'APPROXIMATE',
                           'viewport': {'northeast': {'lat': 28.6142609802915,
                                                      'lng': 77.2308586802915},
                                        'southwest': {'lat': 28.6115630197085,
                                                      'lng': 77.22816071970848}}},
              'place_id': 'ChIJC03rqdriDDkRXT6SJRGXFwc',
              'types': ['establishment', 'point_of_interest']}],
 'status': 'OK'} 
```

如您所见，输出现在格式良好，可读性更强。

我们所做的只是导入 **pprint** 模块的 **pprint** 功能。并且使用 **pprint()** 功能而不是**打印**功能！

本博客由[尼克尔·库马尔](https://www.facebook.com/nikhilksingh97)投稿。如果你喜欢极客博客并想投稿，你也可以用 write.geeksforgeeks.org 写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。