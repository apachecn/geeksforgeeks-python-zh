# Python |获取字典中最大值的关键字

> 原文:[https://www . geesforgeks . org/python-获得字典中最大值的密钥/](https://www.geeksforgeeks.org/python-get-key-with-maximum-value-in-dictionary/)

给定一个字典，任务是找到具有最大值的键。
**例:**

```py
Input : {'Audi':100, 'BMW':1292, 'Jaguar': 210000, 'Hyundai' : 88}
Output : Jaguar

Input:  {'Geeks':1900, 'for':1292, 'geek' : 88}
Output:  Geeks
```

**方法#5:** 使用 max()功能

## 蟒蛇 3

```py
# Python code to find key with Maximum value in Dictionary

# Dictionary Initialization
Tv = {'BreakingBad':100, 'GameOfThrones':1292, 'TMKUC' : 88}

Keymax = max(zip(Tv.values(), Tv.keys()))[1]
print(Keymax)
```

**Output:** 

```py
GameOfThrones
```