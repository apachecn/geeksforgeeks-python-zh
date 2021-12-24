# Python 中带有自定义谓词的 Heapq】

> 原文:[https://www . geesforgeks . org/heapq-with-custom-述语-in-python/](https://www.geeksforgeeks.org/heapq-with-custom-predicate-in-python/)

**先决条件:** [堆料模块](https://www.geeksforgeeks.org/heap-queue-or-heapq-in-python/)

heapq 模块有几个函数将列表作为参数，并以最小堆顺序排列。这些函数的问题在于，它们期望一个列表或元组列表作为参数。它们不支持任何其他可迭代对象或对象之间的比较。例如，考虑一个必须在堆中维护的字典。

## 蟒蛇 3

```
import heapq as hq

my_dict={'a':'apple', 'b':'ball', 'c': 'cat'}
hq.heapify(my_dict)

print(my_dict)
```

**输出**

```
TypeError: heap argument must be a list
```

heapify()函数要求参数是一个列表。因此，如果我们考虑字典列表，看看下面发生了什么。

## 蟒蛇 3

```
import heapq as hq

my_dict=[{'a':'apple'}, {'b':'ball'}, {'c': 'cat'}]

hq.heapify(my_dict)

print(my_dict)
```

**输出:**

> 类型错误:“”

因此，我们不能使用 heapq 模块来比较两本词典。有时我们可能需要比较一个类的对象，并在堆中维护它们。用这个模块来比较这些对象也是不可行的。

## 蟒蛇 3

```
#import module
import heapq as hq

# the dictionary to be as heap
my_dict = {'z': 'zebra', 'b': 'ball', 'w': 'whale',
           'a': 'apple', 'm': 'monkey', 'c': 'cat'}

# conversion to tuple
my_list = [(k, v) for k, v in my_dict.items()]

print("Before organizing as heap :", my_list)

# arrange as min-heap
hq.heapify(my_list)

print("After organizing as heap :", my_list)

# re convert to dictionary
my_dict = dict(my_list)

print("Resultant dictionary :", my_dict)
```

本文讨论如何克服上述问题。

## 在 heapq 中自定义排序

heapq 模块函数可以将项目列表或元组列表作为参数。因此，有两种方法可以自定义排序过程:

1.  **将可迭代表转换为元组列表/列表进行比较。**
2.  **编写一个覆盖“<”运算符的包装类。**

### **转换为物品清单**

该方法简单，可用于解决字典比较问题。字典项可以转换成元组列表，然后传递给 heapify 方法。

**例 1:简单字典**

## 蟒蛇 3

```
#import module
import heapq as hq

# the dictionary to be as heap
my_dict = {'z': 'zebra', 'b': 'ball', 'w': 'whale',
           'a': 'apple', 'm': 'monkey', 'c': 'cat'}

# conversion to tuple
my_list = [(k, v) for k, v in my_dict.items()]

print("Before organizing as heap :", my_list)

# arrange as min-heap
hq.heapify(my_list)

print("After organizing as heap :", my_list)

# re convert to dictionary
my_dict = dict(my_list)

print("Resultant dictionary :", my_dict)
```

**输出:**

> 在组织为堆之前:[('z '，'斑马')，(' b '，'球')，(' w '，'鲸鱼')，(' a '，'苹果')，(' m '，'猴子')，(' c '，'猫')]
> 在组织为堆之后:[('a '，'苹果'，' b '，'球'，(' c '，'猫')，(' z '，'斑马'，(' m '，'猴子'，' w '，'鲸鱼')]
> 结果词典:{'a ':'苹果'，' b ':'球'，' c ':'猫'，' z ':'斑马':

**例 2:字典列表**

## 蟒蛇 3

```
#import module
import heapq as hq

# the list of dictionaries to be as heap
my_dict = [{'z': 'zebra'}, {'b': 'ball'}, {'w': 'whale'},
           {'a': 'apple'}, {'m': 'monkey'}, {'c': 'cat'}]

# conversion to tuple
my_list = [(k, v) for i in my_dict for k, v in i.items()]

print("Before organizing as heap :", my_list)

# arrange as min-heap
hq.heapify(my_list)

print("After organizing as heap :", my_list)

# re convert to dictionary
my_dict = dict(my_list)

print("Resultant dictionary :", my_dict)
```

**输出:**

> 在组织为堆之前:[('z '，'斑马')，(' b '，'球')，(' w '，'鲸鱼')，(' a '，'苹果')，(' m '，'猴子')，(' c '，'猫')]
> 在组织为堆之后:[('a '，'苹果'，' b '，'球'，(' c '，'猫')，(' z '，'斑马'，(' m '，'猴子'，' w '，'鲸鱼')]
> 结果词典:{'a ':'苹果'，' b ':'球'，' c ':'猫'，' z ':'斑马':

上述方法可用于任何数据类型的字典。

### 使用包装类

考虑一种情况，一个类的对象必须在最小堆中维护。例如，让我们考虑一个具有属性的类，如“**名称**”、“**名称**”、“ **yos** ”(服务年限)、“**工资**”。该类的对象必须基于“ **yos** ”(服务年限)在最小堆中维护。

这里，我们覆盖关系运算符“ **<** ”，这样它会比较每个员工的服务年限，并返回真或假。基于返回的布尔值，heapq 模块以最小堆顺序排列对象。

## 蟒蛇 3

```
# import required module
import heapq as hq

# class definition
class employee:

  # constructor
    def __init__(self, n, d, yos, s):
        self.name = n
        self.des = d
        self.yos = yos
        self.sal = s

  # function for customized printing
    def print_me(self):
        print("Name :", self.name)
        print("Designation :", self.des)
        print("Years of service :", str(self.yos))
        print("salary :", str(self.sal))

   # override the comparison operator
    def __lt__(self, nxt):
        return self.yos < nxt.yos

# creating objects
e1 = employee('Anish', 'manager', 3, 24000)
e2 = employee('kathy', 'programmer', 2, 15000)
e3 = employee('Rina', 'Analyst', 5, 30000)
e4 = employee('Vinay', 'programmer', 1, 10000)

# list of employee objects
emp = [e1, e2, e3, e4]

# converting to min-heap
# based on yos
hq.heapify(emp)

# printing the results
for i in range(0, len(emp)):
    emp[i].print_me()
    print()
```

**Output**

```
Name : Vinay
Designation : programmer
Years of service : 1
salary : 10000

Name : kathy
Designation : programmer
Years of service : 2
salary : 15000

Name : Rina
Designation : Analyst
Years of service : 5
salary : 30000

Name : Anish
Designation : manager
Years of service : 3
salary : 24000
```