# Python 中的 Phonenumbers 模块

> 原文:[https://www . geesforgeks . org/phone numbers-python 中的模块/](https://www.geeksforgeeks.org/phonenumbers-module-in-python/)

Python 是一种非常强大的语言，在库方面也非常丰富。**电话号码**是提供众多功能的模块之一，如提供电话号码的基本信息、验证电话号码等。在这里，我们将通过编写简单的 Python 程序来学习如何使用 phonenumbers 模块。这是谷歌 libphonenumber 库的一个 Python 端口。

### **安装**

通过在命令提示符下键入以下命令来安装 phonenumbers 模块。

```py
pip install phonenumbers

```

### 入门指南

**1。将字符串转换为电话号码格式:**为了探索电话号码模块的功能，我们需要以电话号码格式获取用户的电话号码。这里我们将看到如何将用户电话号码转换为 phone number 格式。输入必须是字符串类型，并且必须在电话号码之前添加国家/地区代码。

## 蟒蛇 3

```py
# Program to convert input to
# phonenumber format

import phonenumbers

# Parsing String to Phone number
# Phone number format: (+Countrycode)xxxxxxxxxx
phoneNumber = phonenumbers.parse("+919876543210")

# This will print the phone number and 
# it's basic details.
print(phoneNumber)
```

**输出:**

```py
Country Code: 91 National Number: 9876543210

```

**2。获取时区:**下面是使用 phonenumbers 模块获取电话号码时区的简单 Python 程序。首先，我们将字符串输入解析为 phonenumber 格式，然后使用内置函数获取用户的时区。它只给出有效数字的输出。

## 蟒蛇 3

```py
# Program to get timezone a phone number

import phonenumbers
from phonenumbers import timezone

# Parsing String to Phone number
phoneNumber = phonenumbers.parse("+919876543210")

# Pass the parsed phone number in below function
timeZone = timezone.time_zones_for_number(phoneNumber)

# It print the timezone of a phonenumber
print(timeZone)
```

**输出:**

```py
('Asia/Calcutta',)

```

**3。从文本中提取电话号码:**我们可以使用此模块提取文本/段落中存在的电话号码。您可以遍历它来检索一系列电话号码。为此， **PhoneNumberMatcher** 对象提供了相关功能。

## 蟒蛇 3

```py
# Program to extract phone numbers from a text
import phonenumbers

# Text Input
text = "Contact us at +919876543210 or +14691234567"

# Pass the text and country code to the below function
numbers = phonenumbers.PhoneNumberMatcher(text, "IN")

# Printing the phone numbers matched with country code
# and also the indexes of the phone numbers in the string input
for number in numbers:
    print(number)
```

**输出:**

```py
PhoneNumberMatch [14,27) +919876543210

```

**4。电话号码的运营商和地区:**这里我们将学习如何使用本模块的地理编码器和运营商功能来查找电话号码的运营商和地区。

## 蟒蛇 3

```py
# Program to find carrier and region
# of a phone number
import phonenumbers
from phonenumbers import geocoder, carrier

# Parsing String to Phone number
phoneNumber = phonenumbers.parse("+919876543210")

# Getting carrier of a phone number
Carrier = carrier.name_for_number(phoneNumber, 'en')

# Getting region information
Region = geocoder.description_for_number(phoneNumber, 'en')

# Printing the carrier and region of a phone number
print(Carrier)
print(Region)
```

**输出:**

```py
Airtel
India

```

**5。电话号码的验证:**一个简单的 python 程序，用于检查给定的电话号码是否有效(例如，它在指定的交换机中)，以及检查给定的电话号码是否可能(例如，它有正确的位数)。

## 蟒蛇 3

```py
# Program to check whether a phone number is
# valid or not
import phonenumbers

# Parsing String to Phone number
phone_number = phonenumbers.parse("+91987654321")

# Validating a phone number
valid = phonenumbers.is_valid_number(phone_number)

# Checking possibility of a number
possible = phonenumbers.is_possible_number(phone_number)

# Printing the output
print(valid)
print(possible)
```

**输出:**

```py
False
True
```