# Python 词典

> 原文:[https://www.geeksforgeeks.org/python-dictionary/](https://www.geeksforgeeks.org/python-dictionary/)

**Python 中的 Dictionary** 是一个无序的数据值集合，用于像地图一样存储数据值，与其他只保存单个值作为元素的数据类型不同，Dictionary 保存**键:值**对。字典中提供了键值，以使其更加优化。

**注意–**字典中的键不允许多态性。

> **disparamer:**需要注意的是，随着 Python 3.7 的发布，字典已经被修改以保持插入顺序，因此它们现在是数据值的有序集合。

## 创建词典

在 Python 中，可以通过将一系列元素放在花括号 **{}** 中来创建字典，用“逗号”分隔。字典保存成对的值，一个是键，另一个对应的成对元素是它的**键:值**。字典中的值可以是任何数据类型并且可以重复，而关键字不能重复并且必须是*不可变的*。

**注意–**字典键区分大小写，同名但不同大小写的键将被区别对待。

## 蟒蛇 3

```py
# Creating a Dictionary
# with Integer Keys
Dict = {1: 'Geeks', 2: 'For', 3: 'Geeks'}
print("\nDictionary with the use of Integer Keys: ")
print(Dict)

# Creating a Dictionary
# with Mixed keys
Dict = {'Name': 'Geeks', 1: [1, 2, 3, 4]}
print("\nDictionary with the use of Mixed Keys: ")
print(Dict)
```

**输出:**

```py
Dictionary with the use of Integer Keys: 
{1: 'Geeks', 2: 'For', 3: 'Geeks'}

Dictionary with the use of Mixed Keys: 
{1: [1, 2, 3, 4], 'Name': 'Geeks'}
```

字典也可以由内置函数 dict()创建。只需将置于花括号{}中，就可以创建一个空字典。

## 蟒蛇 3

```py
# Creating an empty Dictionary
Dict = {}
print("Empty Dictionary: ")
print(Dict)

# Creating a Dictionary
# with dict() method
Dict = dict({1: 'Geeks', 2: 'For', 3:'Geeks'})
print("\nDictionary with the use of dict(): ")
print(Dict)

# Creating a Dictionary
# with each item as a Pair
Dict = dict([(1, 'Geeks'), (2, 'For')])
print("\nDictionary with each item as a pair: ")
print(Dict)
```

**输出:**

```py
Empty Dictionary: 
{}

Dictionary with the use of dict(): 
{1: 'Geeks', 2: 'For', 3: 'Geeks'}

Dictionary with each item as a pair: 
{1: 'Geeks', 2: 'For'}
```

### 嵌套词典:

![](img/8fbfbb7068ca887dd8d75e51be048a1f.png)

## 蟒蛇 3

```py
# Creating a Nested Dictionary
# as shown in the below image
Dict = {1: 'Geeks', 2: 'For',
        3:{'A' : 'Welcome', 'B' : 'To', 'C' : 'Geeks'}}

print(Dict)
```

**输出:**

```py
{1: 'Geeks', 2: 'For', 3: {'A': 'Welcome', 'B': 'To', 'C': 'Geeks'}}
```

## 向词典中添加元素

在 Python 字典中，元素的添加可以通过多种方式完成。一次一个值可以通过定义值和关键字添加到字典中，例如字典[关键字] =“值”。使用内置的 **update()** 方法可以更新字典中的现有值。嵌套键值也可以添加到现有字典中。

**注意-** 添加值时，如果键值已经存在，该值将被更新，否则带有该值的新键值将被添加到字典中。

## 蟒蛇 3

```py
# Creating an empty Dictionary
Dict = {}
print("Empty Dictionary: ")
print(Dict)

# Adding elements one at a time
Dict[0] = 'Geeks'
Dict[2] = 'For'
Dict[3] = 1
print("\nDictionary after adding 3 elements: ")
print(Dict)

# Adding set of values
# to a single Key
Dict['Value_set'] = 2, 3, 4
print("\nDictionary after adding 3 elements: ")
print(Dict)

# Updating existing Key's Value
Dict[2] = 'Welcome'
print("\nUpdated key value: ")
print(Dict)

# Adding Nested Key value to Dictionary
Dict[5] = {'Nested' :{'1' : 'Life', '2' : 'Geeks'}}
print("\nAdding a Nested Key: ")
print(Dict)
```

**输出:**

```py
Empty Dictionary: 
{}

Dictionary after adding 3 elements: 
{0: 'Geeks', 2: 'For', 3: 1}

Dictionary after adding 3 elements: 
{0: 'Geeks', 2: 'For', 3: 1, 'Value_set': (2, 3, 4)}

Updated key value: 
{0: 'Geeks', 2: 'Welcome', 3: 1, 'Value_set': (2, 3, 4)}

Adding a Nested Key: 
{0: 'Geeks', 2: 'Welcome', 3: 1, 5: {'Nested': {'1': 'Life', '2': 'Geeks'}}, 'Value_set': (2, 3, 4)}
```

## 从字典中访问元素

为了访问字典的条目，请参考它的关键字名称。键可以用在方括号内。

## 蟒蛇 3

```py
# Python program to demonstrate 
# accessing a element from a Dictionary

# Creating a Dictionary
Dict = {1: 'Geeks', 'name': 'For', 3: 'Geeks'}

# accessing a element using key
print("Accessing a element using key:")
print(Dict['name'])

# accessing a element using key
print("Accessing a element using key:")
print(Dict[1])
```

**输出:**

```py
Accessing a element using key:
For

Accessing a element using key:
Geeks
```

还有一种叫做 [**get()**](https://www.geeksforgeeks.org/get-method-dictionaries-python/) 的方法，也有助于从字典中访问元素。

## 蟒蛇 3

```py
# Creating a Dictionary
Dict = {1: 'Geeks', 'name': 'For', 3: 'Geeks'}

# accessing a element using get()
# method
print("Accessing a element using get:")
print(Dict.get(3))
```

**输出:**

```py
Accessing a element using get:
Geeks
```

### 访问嵌套字典的元素

要访问嵌套字典中任何键的值，请使用 indexing []语法。

## 蟒蛇 3

```py
# Creating a Dictionary
Dict = {'Dict1': {1: 'Geeks'},
        'Dict2': {'Name': 'For'}}

# Accessing element using key
print(Dict['Dict1'])
print(Dict['Dict1'][1])
print(Dict['Dict2']['Name'])
```

**输出:**

```py
{1: 'Geeks'}
Geeks
For
```

## 从字典中删除元素

### 使用 del 关键字

在 Python 字典中，可以通过使用 **del** 关键字来删除键。使用 del 关键字，可以删除字典和整个字典中的特定值。通过使用 del 关键字并提供要从嵌套字典中删除的特定嵌套键和特定键，也可以删除嵌套字典中的项目。

**注意:**T2 字典将删除整个字典，因此删除后打印它会产生错误。

## 蟒蛇 3

```py
# Initial Dictionary
Dict = { 5 : 'Welcome', 6 : 'To', 7 : 'Geeks',
        'A' : {1 : 'Geeks', 2 : 'For', 3 : 'Geeks'},
        'B' : {1 : 'Geeks', 2 : 'Life'}}
print("Initial Dictionary: ")
print(Dict)

# Deleting a Key value
del Dict[6]
print("\nDeleting a specific key: ")
print(Dict)

# Deleting a Key from
# Nested Dictionary
del Dict['A'][2]
print("\nDeleting a key from Nested Dictionary: ")
print(Dict)
```

**输出:**

```py
Initial Dictionary: 
{'A': {1: 'Geeks', 2: 'For', 3: 'Geeks'}, 'B': {1: 'Geeks', 2: 'Life'}, 5: 'Welcome', 6: 'To', 7: 'Geeks'}

Deleting a specific key: 
{'A': {1: 'Geeks', 2: 'For', 3: 'Geeks'}, 'B': {1: 'Geeks', 2: 'Life'}, 5: 'Welcome', 7: 'Geeks'}

Deleting a key from Nested Dictionary: 
{'A': {1: 'Geeks', 3: 'Geeks'}, 'B': {1: 'Geeks', 2: 'Life'}, 5: 'Welcome', 7: 'Geeks'}
```

### 使用 pop()方法

[Pop(](https://www.geeksforgeeks.org/python-dictionary-pop-method/) )方法用于返回和删除指定键的值。

## 蟒蛇 3

```py
# Creating a Dictionary
Dict = {1: 'Geeks', 'name': 'For', 3: 'Geeks'}

# Deleting a key
# using pop() method
pop_ele = Dict.pop(1)
print('\nDictionary after deletion: ' + str(Dict))
print('Value associated to poped key is: ' + str(pop_ele))
```

**输出:**

```py
Dictionary after deletion: {3: 'Geeks', 'name': 'For'}
Value associated to poped key is: Geeks
```

### 使用 popitem()方法

popitem()从字典中返回并移除任意元素(键、值)对。

## 蟒蛇 3

```py
# Creating Dictionary
Dict = {1: 'Geeks', 'name': 'For', 3: 'Geeks'}

# Deleting an arbitrary key
# using popitem() function
pop_ele = Dict.popitem()
print("\nDictionary after deletion: " + str(Dict))
print("The arbitrary pair returned is: " + str(pop_ele))
```

**输出:**

```py
Dictionary after deletion: {3: 'Geeks', 'name': 'For'}
The arbitrary pair returned is: (1, 'Geeks')
```

### 使用 clear()方法

使用 **clear()** 方法可以一次删除字典中的所有项目。

## 蟒蛇 3

```py
# Creating a Dictionary
Dict = {1: 'Geeks', 'name': 'For', 3: 'Geeks'}

# Deleting entire Dictionary
Dict.clear()
print("\nDeleting Entire Dictionary: ")
print(Dict)
```

**输出:**

```py
Deleting Entire Dictionary: 
{}
```

## 词典方法

<figure class="table">

| 方法 | 描述 |
| [副本()](https://www.geeksforgeeks.org/python-dictionary-copy/) | 方法返回字典的一个浅拷贝。 |
| [晴()](https://www.geeksforgeeks.org/python-dictionary-clear/) | clear()方法从字典中移除所有项目。 |
| [pop()](https://www.geeksforgeeks.org/python-dictionary-pop-method/) | 从字典中移除并返回具有给定键的元素。 |
| [灰分()](https://www.geeksforgeeks.org/python-dictionary-popitem-method/) | 从字典中移除任意键值对，并将其作为元组返回。 |
| [get()](https://www.geeksforgeeks.org/get-method-dictionaries-python/) | 这是访问键值的常规方法。 |
| [dictionary_name.values()](https://www.geeksforgeeks.org/python-dictionary-values/) | 返回给定字典中所有可用值的列表。 |
| str() | 生成字典的可打印字符串表示形式。 |
| [更新()](https://www.geeksforgeeks.org/python-dictionary-update-method/) | 将字典字典字典字典 2 的键值对添加到字典中 |
| [集合默认值（）](https://www.geeksforgeeks.org/python-dictionary-setdefault-method/) | 如果密钥不在 dict 中，则设置 dict[key]=默认值 |
| [键()](https://www.geeksforgeeks.org/python-dictionary-keys-method/) | 返回字典字典关键字的列表 |
| [项()](https://www.geeksforgeeks.org/python-dictionary-items-method/) | 返回 dict(键、值)元组对的列表 |
| [has_key()](https://www.geeksforgeeks.org/python-dictionary-has_key/) | 如果关键字在字典字典字典中，则返回 true，否则返回 false |
| [fromkeys()](https://www.geeksforgeeks.org/python-dictionary-fromkeys-method/) | 用 seq 中的键和设置为 value 的值创建新字典。 |
| [型()](https://www.geeksforgeeks.org/python-type-function/) | 返回传递的变量的类型。 |
| CMP() | 比较两个字典的元素。 |

</figure>

[Python 词典近期文章](https://www.geeksforgeeks.org/tag/python-dict/)

https://youtu.be/z7z_e5

> **更多 Python 词典视频:**
> [Python 词典集 2](https://youtu.be/2snBklr3Ovo)
> [Python 词典集 3](https://youtu.be/Bn1ror5wRKg)

**字典程序**

*   词典方法–[第 1 集](https://www.geeksforgeeks.org/dictionary-methods-in-python-set-1-cmp-len-items/)、[第 2 集](https://www.geeksforgeeks.org/dictionary-methods-in-python-set-2-update-has_key-fromkeys/)
*   [字典的 Get()方法](https://www.geeksforgeeks.org/get-method-dictionaries-python/)
*   [处理字典丢失的键](https://www.geeksforgeeks.org/handling-missing-keys-python-dictionaries/)
*   [有序词典](https://www.geeksforgeeks.org/program-print-distinct-elements-given-integer-array-python-ordered-dictionary/)
*   [orderDict()](https://www.geeksforgeeks.org/ordereddict-in-python/)
*   [链目录](https://www.geeksforgeeks.org/chainmap-in-python/)
*   [多数元素](https://www.geeksforgeeks.org/python-counter-majority-element/)
*   [Python 中的字典和计数器查找选举获胜者](https://www.geeksforgeeks.org/dictionary-counter-python-find-winner-election/)
*   [如何用 Python3 实现字典](https://www.geeksforgeeks.org/implement-dictionary-python3/)
*   [Python 中使用给定字符的可能单词](https://www.geeksforgeeks.org/possible-words-using-given-characters-python/)
*   [Python 字典，设置并计数检查频率是否可以相同](https://www.geeksforgeeks.org/python-dictionary-set-counter-check-frequencies-can-become/)
*   [Python 字典交集](https://www.geeksforgeeks.org/python-dictionary-intersection-find-common-elements-three-sorted-arrays/)
*   [Python 中的 OrderedDict()](https://www.geeksforgeeks.org/using-ordereddict-python-check-order-characters-string/)
*   [检查两个数字的二进制表示是否是字谜](https://www.geeksforgeeks.org/python-dictionary-check-binary-representations-two-numbers-anagram/)
*   [Python 计数器查找字谜单词最大子集的大小](https://www.geeksforgeeks.org/python-counter-find-size-largest-subset-anagram-words/)
*   [使用列表和字典一起打印 Python 中的字谜](https://www.geeksforgeeks.org/print-anagrams-together-python-using-list-dictionary/)
*   [将元组列表转换成字典](https://www.geeksforgeeks.org/python-convert-list-tuples-dictionary/)
*   [查找字符串中所有重复的字符](https://www.geeksforgeeks.org/python-counter-find-duplicate-characters-string/)
*   [删除给定句子中所有重复的单词](https://www.geeksforgeeks.org/python-remove-duplicates-words-given-sentence/)
*   [Python 字典查找字符串中的镜像字符](https://www.geeksforgeeks.org/python-dictionary-find-mirror-characters-string/)
*   [Python 计数器和字典交集示例(使用删除和重排制作字符串)](https://www.geeksforgeeks.org/python-counter-dictionary-intersection-example-make-string-using-deletion-rearrangement/)
*   [Python 中序列中重复次数第二多的单词](https://www.geeksforgeeks.org/second-repeated-word-sequence-python/)
*   [Python 词典理解](https://www.geeksforgeeks.org/python-dictionary-comprehension/)
*   [Python 中使用列表理解和排序的第 K 个非重复字符](https://www.geeksforgeeks.org/kth-non-repeating-character-python-using-list-comprehension-ordereddict/)
*   [使用 Python 在字典中抓取和查找有序单词](https://www.geeksforgeeks.org/scraping-and-finding-ordered-words-in-a-dictionary-using-python/)
*   [在 Python 中根据值对字典列表进行排序的方法–使用 itemgetter](https://www.geeksforgeeks.org/ways-sort-list-dictionaries-values-python-using-itemgetter/)
*   [合并两本词典](https://www.geeksforgeeks.org/python-merging-two-dictionaries/)

**有用链接**

*   [Python 词典近期文章](https://www.geeksforgeeks.org/tag/python-dict/)
*   [Python 程序输出–字典](https://www.geeksforgeeks.org/output-python-programs-set-24-dictionary/)
*   [Python 程序输出–字典](https://www.geeksforgeeks.org/output-python-program-set-14-dictionary/)
*   [编码实践平台](https://practice.geeksforgeeks.org/)
*   [选择题–Python](https://www.geeksforgeeks.org/python-multiple-choice-questions/)
*   [Python 类别的所有文章](https://www.geeksforgeeks.org/category/python/)