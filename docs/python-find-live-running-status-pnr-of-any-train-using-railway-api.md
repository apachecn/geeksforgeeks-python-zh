# 使用 Python 中的铁路 API 查询列车实时运行状态和 PNR

> 原文:[https://www . geesforgeks . org/python-find-live-running-status-pnr-of-any-train-use-railway-API/](https://www.geeksforgeeks.org/python-find-live-running-status-pnr-of-any-train-using-railway-api/)

铁路应用编程接口是围绕获取请求组织的。人们可以使用这个基于 JSON 的应用编程接口从印度铁路获得关于实时列车状态、PNR 状态、列车时刻表、车站详细信息和其他信息。

要使用这个 API，必须要有 API 密钥，可以从[这里](https://railwayapi.com/register)得到

**注意:**用户需要在 railwayapi.com 创建一个账户才能使用 API。

**所需模块:**

```
requests
json
```

### 实时运行状态:

下面是实现:

## 蟒蛇 3

```
# Python program to find live train
# status using RAILWAY API

# import required modules
import requests , json

# enter your api key here
api_key = "Your_API_Key"

# base_url variable to store url
base_url = "https://api.railwayapi.com/v2/live/train/"

# enter train_number here
train_number = "12056"

# enter current date in dd-mm-yyyy format
current_date = "20-06-2018"

# complete_url variable to
# store complete url address
complete_url = base_url + train_number + "/date/" + current_date + "/apikey/" + api_key + "/"

# get method of requests module
# return response object
response_ob = requests.get(complete_url)

# json method of response object convert
# json format data into python format data
result = response_ob.json()

# Now result contains a list of nested dictionaries
# Check the value of "response_code" key is equal
# to "200" or not if equal that means record is
# found otherwise record is not found
if result["response_code"] == 200 :

    # train name is extracting from
    # the result variable data    
    train_name = result["train"]["name"]

    # store the value or data of
    # "route" key in variable y
    temp = result["route"]

    # source station name is extracting
    # from the y variable data
    source_station = temp[0]["station"]["name"]

    # destination station name is
    # extracting from the y variable data
    destination_station = temp[-1]["station"]["name"]

    # store the value of "position"
    # key in variable position
    position = result["position"]

    # print details
    print(" train name : " + str(train_name)
        + "\n source station : " + str(source_station)
        + "\n destination station : "+ str(destination_station)
        + "\n current status : " + str(position) )

else :
    print("Record not Found")
```

**输出:**

```
 train name : NEWDELHI JAN SHATABDI EXP
 source station : DEHRADUN
 destination station : NEW DELHI
 current status : Train has reached Destination and late by 15 minutes.
```

### 直播 PNR 状态:

## 蟒蛇 3

```
# Python program to find PNR
# status using RAILWAY API

# import required modules
import requests, json

# Enter API key here
api_key = "Your_API_key"

# base_url variable to store url
base_url = "https://api.railwayapi.com/v2/pnr-status/pnr/"

# Enter valid pnr_number
pnr_number = "6515483790"

# Stores complete url address
complete_url = base_url + pnr_number + "/apikey/" + api_key + "/"

# get method of requests module
# return response object
response_ob = requests.get(complete_url)

# json method of response object convert
# json format data into python format data
result = response_ob.json()

# now result contains list
# of nested dictionaries
if result["response_code"] == 200:

    # train name is extracting
    # from the result variable data
    train_name = result["train"]["name"]

    # train number is extracting from
    # the result variable data
    train_number = result["train"]["number"]

    # from station name is extracting
    # from the result variable data
    from_station = result["from_station"]["name"]

    # to_station name is extracting from
    # the result variable data
    to_station = result["to_station"]["name"]

    # boarding point station name is
    # extracting from the result variable data
    boarding_point = result["boarding_point"]["name"]

    # reservation upto station name is
    # extracting from the result variable data
    reservation_upto = result["reservation_upto"]["name"]

    # store the value or data of "pnr"
    # key in pnr_num variable
    pnr_num = result["pnr"]

    # store the value or data of "doj" key
    # in variable date_of_journey variable
    date_of_journey = result["doj"]

    # store the value or data of
    # "total_passengers" key in variable
    total_passengers = result["total_passengers"]

    # store the value or data of "passengers"
    # key in variable passengers_list
    passengers_list = result["passengers"]

    # store the value or data of
    # "chart_prepared" key in variable
    chart_prepared = result["chart_prepared"]

    # print following values
    print(" train name : " + str(train_name)
          + "\n train number : " + str(train_number)
          + "\n from station : " + str(from_station)
          + "\n to station : " + str(to_station)
          + "\n boarding point : " + str(boarding_point)
          + "\n reservation upto : " + str(reservation_upto)
          + "\n pnr number : " + str(pnr_num)
          + "\n date of journey : " + str(date_of_journey)
          + "\n total no. of passengers: " + str(total_passengers)
          + "\n chart prepared : " + str(chart_prepared))

    # looping through passenger list
    for passenger in passengers_list:

        # store the value or data
        # of "no" key in variable
        passenger_num = passenger["no"]

        # store the value or data of
        # "current_status" key in variable
        current_status = passenger["current_status"]

        # store the value or data of
        # "booking_status" key in variable
        booking_status = passenger["booking_status"]

        # print following values
        print(" passenger number : " + str(passenger_num)
              + "\n current status : " + str(current_status)
              + "\n booking_status : " + str(booking_status))

else:
    print("Record Not Found")
```

**输出:**

```
 train name : DOON EXPRESS
 train number : 13009
 from station : LUCKNOW
 to station : DEHRADUN
 boarding point : LUCKNOW
 reservation upto : DEHRADUN
 pnr number : 6515483790
 date of journey : 01-07-2018
 total no. of passengers: 1
 chart prepared : False
 passenger number : 1
 current status : RLWL/-/16/GN
 booking_status : RLWL/-/23/GN
```