# 使用 Python 获取 Tkinter 的金银价格

> 原文:[https://www . geeksforgeeks . org/get-金银价 in-tkinter-using-python/](https://www.geeksforgeeks.org/get-silver-and-gold-price-in-tkinter-using-python/)

**先决条件:** [美丽组](https://www.geeksforgeeks.org/implementing-web-scraping-python-beautiful-soup/)[请求](https://www.geeksforgeeks.org/python-requests-tutorial/)[时间](https://www.geeksforgeeks.org/python-gui-tkinter/)[日期时间](https://www.geeksforgeeks.org/python-datetime-module-with-examples/)

在本文中，我们将讨论如何在 Tkinter 中使用 Python 获得印度的金银价格。价格会随着时间的推移而变化，黄金和白银的价格是由供给、需求和投资者行为共同决定的。

我们将使用 [goodreturns](https://www.goodreturns.in/) 网站获取金银价格。我们将为不同的操作创建多个功能:

*   **silver_price():** 此功能用于获取白银价格。对于白银，我们将使用这个[网址](https://www.goodreturns.in/silver-rates/#Today+24+Carat+Gold+Rate+Per+Gram+in+India+%28INR%29)。
*   **gold_price():** 此功能用于获取黄金价格。对于黄金，我们将使用这个[网址](https://www.goodreturns.in/gold-rates/#Today+24+Carat+Gold+Rate+Per+Gram+in+India+%28INR%29)。
*   **get _ number _ from _ string():**此函数用于从字符串中提取整数或浮点数。
*   **change_price():** 此功能用于获取特定重量的黄金或白银价格。**T3】**

### **分步方法:**

**步骤 1#**

导入所需的库。

## 蟒蛇 3

```py
# Import Required library
from bs4 import BeautifulSoup
import requests
from tkinter import *
from datetime import date
from tkinter import ttk
```

**步骤 2#**

获得白银和黄金价格。

## 蟒蛇 3

```py
# method to get the price of silver
def silver_price():

    # getting the request from url
    data = requests.get(
        "https://www.goodreturns.in/silver-rates/#Today+24+Carat+Gold+Rate+Per+Gram+in+India+%28INR%29")

    # converting the text
    soup = BeautifulSoup(data.text, 'html.parser')

    # finding metha info for the current price
    price = soup.find("div", class_="gold_silver_table right-align-content").find(
        "tr", class_="odd_row").findAll("td")

    # returning the price in text
    return price[1].text

# method to get the price of gold
def gold_price():

    # getting the request from url
    data = requests.get(
        "https://www.goodreturns.in/gold-rates/#Today+24+Carat+Gold+Rate+Per+Gram+in+India+%28INR%29")

    # converting the text
    soup = BeautifulSoup(data.text, 'html.parser')

    # finding metha info for the current price
    price = soup.find("div", class_="gold_silver_table right-align-content").find(
        "tr", class_="odd_row").findAll("td")

    # returning the price in text
    return price[1].text
```

**步骤 3#**

从字符串中获取整数值或浮点值。

## 蟒蛇 3

```py
# Extract Integer or Float from String
def get_number_from_string(string):
    return float(''.join([x for x in string if x.isdigit() or x == '.']))
```

**步骤 4#**

获取特定重量的金银价格。

## 蟒蛇 3

```py
# Get price for a particular weight
def change_price(weight_value):

    g_price = float(weight_value)*get_number_from_string(gold_price())
    s_price = float(weight_value)*get_number_from_string(silver_price())

    silver_price_label.config(text=f"{s_price} Rs")
    gold_price_label.config(text=f"{g_price} Rs")
```

**以下是基于上述方法的实现:**

## 蟒蛇 3

```py
# Import Required library
from bs4 import BeautifulSoup
import requests
from tkinter import *
from datetime import date
from tkinter import ttk

# Extract Integer or Float from String
def get_number_from_string(string):
    return float(''.join([x for x in string if x.isdigit() or x == '.']))

# Returns the current local date
today = date.today()

# method to get the price of silver
def silver_price():

    # getting the request from url
    data = requests.get(
        "https://www.goodreturns.in/silver-rates/#Today+24+Carat+Gold+Rate+Per+Gram+in+India+%28INR%29")

    # converting the text
    soup = BeautifulSoup(data.text, 'html.parser')

    # finding metha info for the current price
    price = soup.find("div", class_="gold_silver_table right-align-content").find(
        "tr", class_="odd_row").findAll("td")

    # returning the price in text
    return price[1].text

# method to get the price of gold
def gold_price():

    # getting the request from url
    data = requests.get(
        "https://www.goodreturns.in/gold-rates/#Today+24+Carat+Gold+Rate+Per+Gram+in+India+%28INR%29")

    # converting the text
    soup = BeautifulSoup(data.text, 'html.parser')

    # finding metha info for the current price
    price = soup.find("div", class_="gold_silver_table right-align-content").find(
        "tr", class_="odd_row").findAll("td")

    # returning the price in text
    return price[1].text

# Get price for a particular weight
def change_price(weight_value):

    g_price = float(weight_value)*get_number_from_string(gold_price())
    s_price = float(weight_value)*get_number_from_string(silver_price())

    silver_price_label.config(text=f"{s_price} Rs")
    gold_price_label.config(text=f"{g_price} Rs")

# Create Object
root = Tk()

# Set Geometry
root.geometry("400x400")

# Create Label
Label(root, text="SILVER AND GOLD PRICE", font=(
    "Helvetica 15 bold"), fg="blue").pack()

# Frame1
frame1 = Frame(root)
frame1.pack(pady=20)

Label(frame1, text="Today Date:- ", font=("Helvetica 15 bold")).pack(side=LEFT)
Label(frame1, text=today, font=("Helvetica 15")).pack()

# Frame2
frame2 = Frame(root)
frame2.pack(pady=20)

# Set Variable
variable = StringVar(root)
variable.set("1")

Label(frame2, text="Select Weight:- ",
      font=("Helvetica 15 bold")).pack(side=LEFT)
w = OptionMenu(frame2, variable, "1", "8", "100",
               "500", "1000", command=change_price)
w.pack(side=LEFT)
Label(frame2, text="gm", font=("Helvetica 15")).pack(side=LEFT)

# Frame3
frame3 = Frame(root)
frame3.pack()

Label(frame3, text="Silver Price:- ", font=("Helvetica 15 bold")).pack(side=LEFT)
silver_price_label = Label(frame3, text="", font=("Helvetica 15"))
silver_price_label.pack(pady=20)

# Frame4
frame4 = Frame(root)
frame4.pack()

Label(frame4, text="Gold Price:- ", font=("Helvetica 15 bold")).pack(side=LEFT)
gold_price_label = Label(frame4, text="", font=("Helvetica 15"))
gold_price_label.pack(pady=20)

# Execute Tkinter
root.mainloop()
```

**输出:**

<video class="wp-video-shortcode" id="video-539161-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210107194615/FreeOnlineScreenRecorderProject8.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20210107194615/FreeOnlineScreenRecorderProject8.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210107194615/FreeOnlineScreenRecorderProject8.mp4)</video>