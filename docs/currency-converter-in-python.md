# Python 中的货币转换器

> 原文:[https://www.geeksforgeeks.org/currency-converter-in-python/](https://www.geeksforgeeks.org/currency-converter-in-python/)

Python 是一种非常通用的编程语言。几乎每种主流技术都在使用 Python，人们可以用它开发任何应用程序。让我们看一个 Python 程序，将一个国家的货币转换成另一个国家的货币。要使用该服务，必须需要 API 密钥，可以从[这里的](https://fixer.io/)获取。
我们将使用`fixer API`获取实时转换率并转换相应的金额。

#### 所需模块:

**请求:**这个模块没有内置 python。要安装它，请在终端或 cmd 中键入以下命令。

```py
pip install requests

```

下面是实现:

```py
# Python program to convert the currency
# of one country to that of another country 

# Import the modules needed
import requests

class Currency_convertor:
    # empty dict to store the conversion rates
    rates = {} 
    def __init__(self, url):
        data = requests.get(url).json()

        # Extracting only the rates from the json data
        self.rates = data["rates"] 

    # function to do a simple cross multiplication between 
    # the amount and the conversion rates
    def convert(self, from_currency, to_currency, amount):
        initial_amount = amount
        if from_currency != 'EUR' :
            amount = amount / self.rates[from_currency]

        # limiting the precision to 2 decimal places
        amount = round(amount * self.rates[to_currency], 2)
        print('{} {} = {} {}'.format(initial_amount, from_currency, amount, to_currency))

# Driver code
if __name__ == "__main__":

    # YOUR_ACCESS_KEY = 'GET YOUR ACCESS KEY FROM fixer.io'
    url = str.__add__('http://data.fixer.io/api/latest?access_key=', YOUR_ACCESS_KEY)  
    c = Currency_convertor(url)
    from_country = input("From Country: ")
    to_country = input("TO Country: ")
    amount = int(input("Amount: "))

    c.convert(from_country, to_country, amount)
```

**输入:**

```py
From Country: USD 
TO Country: INR 
Amount: 1 

```

**输出:**

```py
1 USD = 70.69 INR

```