# Python |使用酒店价格比较 API

查找酒店价格

> 原文:[https://www . geesforgeks . org/python-find-hotel-prices-use-hotel-price-comparison-API/](https://www.geeksforgeeks.org/python-find-hotel-prices-using-hotel-price-comparison-api/)

**`Makcorps hotel API`** 用于获取 JSON 数据，比较酒店价格、评级和来自 200 多个网站的评论，包括；Agoda.com、Hotels.com、Expedia 等等。它是围绕获取请求组织的。人们可以免费使用这个应用编程接口获取任何酒店或任何城市的价格、评级、评论、历史价格和许多其他信息。

要使用这个 API，必须要有 API 键，可以从[这里](https://www.makcorps.com)得到

**注意:**用户需要在**makcorps.com**上创建一个账户，然后才可以使用 API。

## 所需模块:

**请求**

```py
pip install requests

```

#### 履行

这个 API 会根据城市名称进行搜索。让我们假设如果搜索一个城市伦敦，那么输出 JSON 将是来自不同供应商的该城市不同酒店的价格比较以及它们的名称。根据供应商的价格，也将显示最佳价格。

下面是实现:

```py
# Python program to find live hotel prices  
# Python program to find live hotel prices
# status using Makcorps Hotel API

# import required modules
import requests, json

# base_url variable to store url
base_url = "https://api.makcorps.com/free/"

# enter city name here
city = "london"

# complete_url variable to
# store complete url address
complete_url = base_url + city

# Declaring headers needed
headers = {
    'Authorization': 'JWT your_API_id',
}

# get method of requests module
# return response object
response_ob = requests.get(complete_url, headers=headers)

# json method of response object convert
# json format data into python format data
result = response_ob.json()

# Now check the value of status_code is equal
# to "200" or not, if equal that means record is
# found otherwise record is not found
if response_ob.status_code == 200:

    #  name is extracting from
    # the result variable data
    print("price comparison data for a random date of city london is:")
    print(result)
else:
    print("record is not found for given request")
```

**输出:**

```py
price comparison data for a random date of city london is:
{'comparison':
  [
    {
     'vendor1-price': 'US$217',
     'vendor3-price': 'US$246',
     'vendor2-price': 'US$217',
     'vendor3': 'travelup.com',
     'vendor1': 'Travelocity',
     'Hotel': 'Park Plaza Westminster Bridge London',
     'Best-price': 'US$\xa0246US$\xa0215Booking.com',
     'vendor2': 'Orbitz.com'
    }, 

    {
     'vendor1-price': '',
     'vendor3-price': '',
     'vendor2-price': '',
     'vendor3': 'Travelocity',
     'vendor1': 'Expedia.com',
     'Hotel': 'Travelodge London Covent Garden',
     'Best-price': 'US$\xa074Travelodge',
     'vendor2': 'Hotels.com'
    }, 

    {
     'vendor1-price': 'US$167',
     'vendor3-price': 'US$183',
     'vendor2-price': 'US$171',
     'vendor3': 'Nustay.com', 
     'vendor1': 'ParkGrandLondon',
     'Hotel': 'Park Grand London Kensington',
     'Best-price': 'US$\xa0170Booking.com', 
     'vendor2': 'Travelocity'
    }, 

    {
     'vendor1-price': '',
     'vendor3-price': '',
     'vendor2-price': '',
     'vendor3': 'Orbitz.com',
     'vendor1': 'Expedia.com',
     'Hotel': 'Travelodge London City hotel',
     'Best-price': 'US$\xa056Travelodge',
     'vendor2': 'Nustay.com'
    }, 

    {
     'vendor1-price': 'US$205',
     'vendor3-price': 'US$232',
     'vendor2-price': 'US$185',
     'vendor3': 'ZenHotels.com', 
     'vendor1': 'Booking.com',
     'Hotel': 'The Tower Hotel',
     'Best-price': 'US$\xa0206Orbitz.com',
     'vendor2': 'Trip.com'
    },

    {
     'vendor1-price': 'US$77',
     'vendor3-price': 'US$94',
     'vendor2-price': 'US$87',
     'vendor3': 'Nustay.com', 
     'vendor1': 'Official Site',
     'Hotel': 'Point A Hotel, London Kings Cross St Pancras',
     'Best-price': 'US$\xa087Orbitz.com',
     'vendor2': 'Booking.com'
    },

    {
     'vendor1-price': 'US$224',
     'vendor3-price': 'US$242',
     'vendor2-price': 'US$217',
     'vendor3': 'travelup.com', 
     'vendor1': 'Orbitz.com',
     'Hotel': 'Strand Palace Hotel',
     'Best-price': 'US$\xa0223Booking.com',
     'vendor2': 'ZenHotels.com'
    }
  ]
}

```