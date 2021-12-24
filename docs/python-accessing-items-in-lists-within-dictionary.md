# Python–访问字典列表中的项目

> 原文:[https://www . geesforgeks . org/python-访问-列表中的项目-在字典中/](https://www.geeksforgeeks.org/python-accessing-items-in-lists-within-dictionary/)

给定一个以值为列表的字典，任务是编写一个 python 程序，可以访问该字典中的列表值项。

## 方法 **1** :手动访问列表中的项目

这是一种简单的方法，其中必须从中提取值的键与特定值的索引一起传递。

**语法:**

> dictionary _ name[键][索引]

**示例:**直接索引

## 蟒蛇 3

```
#  Creating dictionary which contains lists
country = {
    "India": ["Delhi", "Maharastra", "Haryana", 
              "Uttar Pradesh", "Himachal Pradesh"],
    "Japan": ["Hokkaido", "Chubu", "Tohoku", "Shikoku"],
    "United States": ["New York", "Texas", "Indiana", 
                      "New Jersey", "Hawaii", "Alaska"]
}

print(country["India"])
print(country["India"][0])
print(country["India"][1])
print(country["United States"][3])
print(country['Japan'][2])
```

**输出:**

> (德里、马哈拉施特拉邦、哈里亚纳邦、北方邦、喜马偕尔邦)
> 
> 德里
> 
> 马哈拉施特拉邦
> 
> 新泽西州
> 
> 东北町

## 方法 **2** :使用循环

完成给定任务的最简单方法是遍历字典。

**示例:**使用循环

## 蟒蛇 3

```
#  Creating dictionary which contains lists
country = {
    "India": ["Delhi", "Maharastra", "Haryana", 
              "Uttar Pradesh", "Himachal Pradesh"],
    "Japan": ["Hokkaido", "Chubu", "Tohoku", "Shikoku"],
    "United States": ["New York", "Texas", "Indiana", 
                      "New Jersey", "Hawaii", "Alaska"]
}

for key, val in country.items():
    for i in val:
        print("{} : {}".format(key, i))
    print("--------------------")
```

**输出:**

> 印度:德里
> 
> 印度:马哈拉斯特拉
> 
> 印度:哈里亚纳邦
> 
> 印度:北方邦
> 
> 印度:喜马偕尔邦
> 
> ——————–
> 
> 日本:北海道
> 
> 日本:中部
> 
> 日本:东北
> 
> 日本:四国
> 
> ——————–
> 
> 美国:纽约
> 
> 美国:得克萨斯州
> 
> 美国:印第安纳州
> 
> 美国:新泽西州
> 
> 美国:夏威夷
> 
> 美国:阿拉斯加
> 
> ——————–

## 方法 **3** :访问特定的密钥列表

这或多或少是前两种方法的组合，其中使用键迭代值列表。

**示例:**访问特定的密钥列表

## 蟒蛇 3

```
#  Creating dictionary which contains lists
country = {
    "India": ["Delhi", "Maharastra", "Haryana",
              "Uttar Pradesh", "Himachal Pradesh"],
    "Japan": ["Hokkaido", "Chubu", "Tohoku", "Shikoku"],
    "United States": ["New York", "Texas", "Indiana",
                      "New Jersey", "Hawaii", "Alaska"]
}

for i in country['Japan']:
    print(i)

for i in country['India']:
    print(i)

for i in country['United States']:
    print(i)
```

**输出:**

> 北海道
> 
> 中部
> 
> 东北町
> 
> 四国
> 
> 德里
> 
> 马哈拉施特拉邦
> 
> 哈里亚纳邦
> 
> 北方邦(北方邦)
> 
> 喜马偕尔邦
> 
> 纽约
> 
> 得克萨斯州
> 
> 印第安纳
> 
> 新泽西州
> 
> 夏威夷
> 
> 阿拉斯加

## 方法 **4** :使用列表切片

这是第一个方法的修改版本，这里我们传递切片范围，而不是值列表的索引。

**语法:**

> dictionary _ name[key][start _ index:end _ index]

**示例:**使用列表切片

## 蟒蛇 3

```
#  Creating dictionary which contains lists
country = {
    "India": ["Delhi", "Maharastra", "Haryana",
              "Uttar Pradesh", "Himachal Pradesh"],
    "Japan": ["Hokkaido", "Chubu", "Tohoku", "Shikoku"],
    "United States": ["New York", "Texas", "Indiana",
                      "New Jersey", "Hawaii", "Alaska"]
}

# extract the first 3 cities of India
print(country["India"][:3])

# extract last 2 cities from Japan
print(country["Japan"][-2:])

# extract all cities except last 3 cities from india
print(country["India"][:-3])

# extract 2th to 5th cities from us
print(country["United States"][1:5])
```

**输出:**

> ['德里'，'马哈拉斯特拉'，'哈里亚纳邦']
> 
> ['东北'，'四国']
> 
> ['德里'，'马哈拉斯特拉']
> 
> ['德克萨斯'，'印第安纳'，'新泽西'，'夏威夷']