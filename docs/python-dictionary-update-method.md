# Python 字典更新()方法

> 原文:[https://www . geesforgeks . org/python-dictionary-update-method/](https://www.geeksforgeeks.org/python-dictionary-update-method/)

**Python Dictionary update()方法**使用另一个字典对象或一组键/值对中的元素更新字典。

> **语法:**dict . update([其他])
> 
> **参数:**该方法以字典或键/值对(一般为元组)的可迭代对象作为参数。
> 
> **返回:**它不返回任何值，但使用字典对象或键/值对的可迭代对象中的元素更新字典。

## Python 词典更新()示例

### **示例#1:** 用另一个字典更新

## 蟒蛇 3

```
# Python program to show working
# of update() method in Dictionary

# Dictionary with three items
Dictionary1 = {'A': 'Geeks', 'B': 'For', }
Dictionary2 = {'B': 'Geeks'}

# Dictionary before Updation
print("Original Dictionary:")
print(Dictionary1)

# update the value of key 'B'
Dictionary1.update(Dictionary2)
print("Dictionary after updation:")
print(Dictionary1)
```

**输出:**

```
Original Dictionary:
{'A': 'Geeks', 'B': 'For'}

Dictionary after updation:
{'A': 'Geeks', 'B': 'Geeks'}
```

### **示例#2:** 使用可迭代更新

## 蟒蛇 3

```
# Python program to show working
# of update() method in Dictionary

# Dictionary with single item
Dictionary1 = {'A': 'Geeks'}

# Dictionary before Updation
print("Original Dictionary:")
print(Dictionary1)

# update the Dictionary with iterable
Dictionary1.update(B='For', C='Geeks')
print("Dictionary after updation:")
print(Dictionary1)
```

**输出:**

```
Original Dictionary:
{'A': 'Geeks'}

Dictionary after updation:
{'C': 'Geeks', 'B': 'For', 'A': 'Geeks'}
```

### 示例#3:如果键存在，Python 字典更新值

## 蟒蛇 3

```
def checkKey(dict, key):

    if key in dict.keys():
        print("Key exist, ", end =" ")
        dict.update({'m':600})
        print("value updated =", 600)
    else:
        print("Not Exist")
dict = {'m': 700, 'n':100, 't':500}

key = 'm'
checkKey(dict, key)
print(dict)
```

**输出:**

```
Key exist,  value updated = 600
{'m': 600, 'n': 100, 't': 500}
```