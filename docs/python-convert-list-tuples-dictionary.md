# Python |将元组列表转换为字典

> 原文:[https://www . geesforgeks . org/python-convert-list-元组-dictionary/](https://www.geeksforgeeks.org/python-convert-list-tuples-dictionary/)

有时，您可能需要将一个[元组](https://www.geeksforgeeks.org/tuples-in-python/)转换为[字典](https://www.geeksforgeeks.org/tag/python-dict/)对象，以使其更具可读性。
在本文中，我们将尝试学习如何将元组列表转换为字典。在这里，我们将找到两种方法。
**示例:**

```
Input : [("akash", 10), ("gaurav", 12), ("anand", 14), 
         ("suraj", 20), ("akhil", 25), ("ashish", 30)]
Output : {'akash': [10], 'gaurav': [12], 'anand': [14], 
          'ashish': [30], 'akhil': [25], 'suraj': [20]}

Input : [('A', 1), ('B', 2), ('C', 3)]
Output : {'B': [2], 'A': [1], 'C': [3]}

Input : [("Nakul",93), ("Shivansh",45), ("Samved",65),
             ("Yash",88), ("Vidit",70), ("Pradeep",52)]
Output : {'Nakul': [93], 'Shivansh': [45], 'Samved': [65], 
            'Yash': [88], 'Vidit': [70], 'Pradeep': [52]}

Input : [('Sachin', 10), ('MSD', 7), ('Kohli', 18), ('Rohit', 45)]
Output : {'Sachin': 10, 'MSD': 7, 'Kohli': 18, 'Rohit': 45}

```

**方法 1:使用[set default()](https://www.geeksforgeeks.org/dictionary-methods-in-python-set-2-update-has_key-fromkeys/)T3】**

这里我们使用了字典方法 *setdefault()* 将第一个参数转换为 key，第二个参数转换为字典的值。 *setdefault(key，def_value)* 函数搜索一个键并显示其值，如果该键不存在，则创建一个带有 def_value 的新键。使用 append 函数，我们刚刚将值添加到字典中。

**例 1:**

```
# Python code to convert into dictionary

def Convert(tup, di):
    for a, b in tup:
        di.setdefault(a, []).append(b)
    return di

# Driver Code    
tups = [("akash", 10), ("gaurav", 12), ("anand", 14), 
     ("suraj", 20), ("akhil", 25), ("ashish", 30)]
dictionary = {}
print (Convert(tups, dictionary))
```

输出:

```
{'akash': [10], 'gaurav': [12], 'anand': [14], 
 'ashish': [30], 'akhil': [25], 'suraj': [20]}

```

**例 2:**

```
# Python code to convert into dictionary
list_1=[("Nakul",93), ("Shivansh",45), ("Samved",65),
           ("Yash",88), ("Vidit",70), ("Pradeep",52)]
dict_1=dict()

for student,score in list_1:
    dict_1.setdefault(student, []).append(score)
print(dict_1)
```

输出:

```
{'Nakul': [93], 'Shivansh': [45], 'Samved': [65], 'Yash': [88], 'Vidit': [70], 'Pradeep': [52]}

```

**方法二:使用 dict()方法**

**例 1:**

```
# Python code to convert into dictionary
def Convert(tup, di):
    di = dict(tup)
    return di

# Driver Code 
tups = [("akash", 10), ("gaurav", 12), ("anand", 14), 
    ("suraj", 20), ("akhil", 25), ("ashish", 30)]
dictionary = {}
print (Convert(tups, dictionary))
```

输出:

```
{'anand': 14, 'akash': 10, 'akhil': 25, 
 'suraj': 20, 'ashish': 30, 'gaurav': 12}
```

**例 2:**

```
# Python code to convert into dictionary

print (dict([('Sachin', 10), ('MSD', 7), ('Kohli', 18), ('Rohit', 45)]))
```

输出:

```
{'Sachin': 10, 'MSD': 7, 'Kohli': 18, 'Rohit': 45}

```

这是从列表或元组到字典的简单转换方法。这里我们将一个元组传递给 dict()方法，该方法将元组转换成相应的字典。