# 接受可变长度键值对作为参数的函数

> 原文:[https://www . geesforgeks . org/接受可变长度键值对作为参数的函数/](https://www.geeksforgeeks.org/functions-that-accept-variable-length-key-value-pair-as-arguments/)

为了将变长键值对作为参数传递给函数，Python 提供了一个名为 ****** ***kwargs** 的特性。*
kwarg 代表关键字参数。当人们想要处理函数中的命名参数时，它被证明是一个有效的解决方案。

**语法:**

```
def functionName(**anything):
    statement(s)
```

**注意:**在任何术语中添加“ ****** ”使其成为 kwarg 参数。它接受关键字作为参数。

**示例#1:**

## 蟒蛇 3

```
# using kwargs
# in functions

def printKwargs(**kwargs):
    print(kwargs)

# driver code
if __name__ == "__main__":
    printKwargs(Argument_1='gfg', Argument_2='GFG')
```

**输出:**

```
{'Argument_1': 'gfg', 'Argument_2': 'GFG'}
```

**例 2:**

## 蟒蛇 3

```
# using kwargs
# in functions

def printValues(**kwargs):
    for key, value in kwargs.items():
        print("The value of {} is {}".format(key, value))

# driver code
if __name__ == '__main__':
    printValues(abbreviation="GFG", full_name="geeksforgeeks")
```

**输出:**

```
The value of abbreviation is GFG
The value of full_name is geeksforgeeks
```

**示例#3:**

## 蟒蛇 3

```
# using kwargs
# in functions
# to concatenate

def concatenate(**arguments):
    # initialising empty string
    final_str = ""

    # Iterating over the Python kwargs
    # dictionary
    for elements in arguments.values():
        final_str += elements
    return final_str

# driver code
if __name__ == '__main__':
    print(concatenate(a="g", b="F", c="g"))
```

**输出:**

```
gFg
```

**示例#4:**

## 蟒蛇 3

```
# using kwargs
# to multiply

def multiply(**kwargs):

    # initialising answer
    answer = 1

    # Iterating over the Python kwargs
    # dictionary
    for elements in kwargs.values():
        answer *= elements
    return answer

# driver code
if __name__ == '__main__':
    print(multiply(a=1, b=2, c=3, d=4, e=5))
```

**输出:**

```
120
```