# 使用 Python 获取电话号码信息

> 原文:[https://www . geesforgeks . org/get-phone-number-information-use-python/](https://www.geeksforgeeks.org/get-phone-number-information-using-python/)

在本文中，您将学习如何通过编写一个简单的 Python 程序来获取电话号码的信息，例如电话号码所属的国家/地区名称，或者该电话号码的网络服务提供商名称。Python 为这个任务提供了一个模块名**电话号码**。本文是 Python 对谷歌 libphonenumber 库的移植。

**安装**
在命令提示符下使用下面的命令安装软件包`phonenumbers`。

```
pip install phonenumbers
```

**示例 1:** 获取电话号码所属国家名称的 Python 程序:

```
import phonenumbers

# geocoder: to know the specific 
# location to that phone number
from phonenumbers import geocoder

phone_number = phonenumbers.parse("Number with country code") 
# Indian phone number example: +91**********
# Nepali phone number example: +977********** 

# this will print the country name
print(geocoder.description_for_number(phone_number, 
                                      'en'))   
```

**输出:**

```
India
```

**示例 2:** Python 程序获取该电话号码的服务提供商名称

```
import phonenumbers

# carrier: to know the name of 
# service provider of that phone number
from phonenumbers import carrier

service_provider = phonenumbers.parse("Number with country code")
# Indian phone number example: +91**********
# Nepali phone number example: +977**********

# this will print the service provider name
print(carrier.name_for_number(service_provider,
                              'en')) 
```

**输出:**

```
Airtel

```