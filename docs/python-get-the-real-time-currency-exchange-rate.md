# Python |获取实时货币汇率

> 原文:[https://www . geesforgeks . org/python-get-the-time-currency-汇率/](https://www.geeksforgeeks.org/python-get-the-real-time-currency-exchange-rate/)

Python 是一种非常通用的编程语言。几乎每种主流技术都在使用 Python，人们可以用它开发任何应用程序。

让我们看一个 Python 程序来实时计算货币汇率。要使用这个服务，必须需要 API 键，可以从[这里](https://www.alphavantage.co/support/#api-key)获取。您可以在这里从[获得货币代码列表。](https://simple.wikipedia.org/wiki/ISO_4217#Official_codes)

我们将使用 **`CURRENCY_EXCHANGE_RATE API`** ，它可以返回任何一对数字货币(如比特币)或实物货币(如美元)的实时汇率。

**所需模块:**

```py
requests
json

```

下面是实现:

```py
# Python program to get the real-time
# currency exchange rate

# Function to get real time currency exchange 
def RealTimeCurrencyExchangeRate(from_currency, to_currency, api_key) :

    # importing required libraries
    import requests, json

    # base_url variable store base url 
    base_url = r"https://www.alphavantage.co/query?function = CURRENCY_EXCHANGE_RATE"

    # main_url variable store complete url
    main_url = base_url + "&from_currency =" + from_currency + 
               "&to_currency =" + to_currency + "&apikey =" + api_key

    # get method of requests module 
    # return response object 
    req_ob = requests.get(main_url)

    # json method return json format
    # data into python dictionary data type.

    # result contains list of nested dictionaries
    result = req_ob.json()

    print(" Result before parsing the json data :\n", result)

    print("\n After parsing : \n Realtime Currency Exchange Rate for",
          result["Realtime Currency Exchange Rate"]
                ["2\. From_Currency Name"], "TO",
          result["Realtime Currency Exchange Rate"]
                ["4\. To_Currency Name"], "is",
          result["Realtime Currency Exchange Rate"]
                ['5\. Exchange Rate'], to_currency)

# Driver code
if __name__ == "__main__" :

    # currency code
    from_currency = "USD"
    to_currency = "INR"

    # enter your api key here 
    api_key = "Your_Api_Key"

    # function calling
    RealTimeCurrencyExchangeRate(from_currency, to_currency, api_key)
```

**输出:**

> 解析 json 数据前的结果:
> {“实时货币汇率”:{“1。From_Currency Code': 'USD '，' 2。From_Currency Name ':'美元'，' 3。To_Currency Code': 'INR '，' 4。To_Currency Name ':'印度卢比'，' 5。汇率:' 71.51500000 '，' 6。上次刷新时间:' ' 2018-12-13 17:40:36 '，' 7。时区':' UTC'}}
> 
> 解析后:
> 美元对印度卢比的实时货币汇率为 71.51500000 印度卢比