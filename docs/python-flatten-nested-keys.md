# Python–展平嵌套键

> 原文:[https://www.geeksforgeeks.org/python-flatten-nested-keys/](https://www.geeksforgeeks.org/python-flatten-nested-keys/)

有时，在处理 Python 数据时，我们可能会遇到一个问题，即我们需要对嵌套列表记录中的某些键执行展平。数据预处理时会出现这种问题。让我们讨论执行这项任务的某些方法。

**方法#1:使用循环**
这是执行这个任务的蛮力方法。在这种情况下，我们通过分配基键来构造新的字典，然后使用嵌套循环来执行内部键元素的展平。

```py
# Python3 code to demonstrate working of 
# Flatten Nested Keys
# Using loop

# initializing list
test_list = [{'Gfg' :  1, 'id' : 1, 'data' : [{'rating' : 7, 'price' : 4},
             {'rating' : 17, 'price' : 8}]}, 
             {'Gfg' :  1, 'id' : 2, 'data' : [{'rating' : 18, 'price' : 19}]}]

# printing original list
print("The original list is : " + str(test_list))

# Flatten Nested Keys
# Using loop
res = []
for sub in test_list:
    temp1 = {
      'Gfg': sub['Gfg'],
      'id': sub['id']
    }
    for data in sub.get('data', []):
        res.append({
            **temp1,
            'rating': data['rating'],
            'price': data['price']})

# printing result 
print("The flattened list : " + str(res)) 
```

**Output :**

> 原始列表为:[{'data': [{'rating': 7，' price': 4}，{'rating': 17，' price': 8}]，' id': 1，' Gfg': 1}，{'data': [{'rating': 18，' price': 19}]，' id': 2，' Gfg': 1}]
> 展平列表为:[{'price': 4，' rating': 7，' id': 1，' Gfg': 1}，{'price': 8，' rating': 17，' id': 1，' Gfg': 1}，{ '