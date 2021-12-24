# Python Else 循环

> 原文:[https://www.geeksforgeeks.org/python-else-loop/](https://www.geeksforgeeks.org/python-else-loop/)

Else with loop 与 while 和 for loop 一起使用。else 块在循环结束时执行意味着当给定的循环条件为假时，则执行 else 块。让我们看看下面 while 循环和 for 循环的例子。

## 否则使用 While 循环

考虑下面的例子。

## 蟒蛇 3

```
i=0

while i<5:
  i+=1
  print("i =",i)

else:
  print("else block is executed")
```

**输出:**

```
i = 1
i = 2
i = 3
i = 4
i = 5
else block is executed
```

#### 说明

*   声明 i=0
*   在给定条件为真之前，我们知道 while 循环是活动的。我们检查 i<5，直到 I 的值为 4。
*   I+= I 的 1 个增量，因为我们不想无限次地执行 while 循环。
*   打印 I 的值
*   当 I 的值为 5 时，else 块执行。

## 带 For 循环的 Else

考虑下面的例子。

## 蟒蛇 3

```
l = [1, 2, 3, 4, 5]

for a in l:
    print(a)

else:
    print("else block is executed")
```

**输出:**

```
1
2
3
4
5
else block is executed
```

#### **解释**

*   声明一个列表 l=[1，2，3，4，5]
*   对于循环打印 a。
*   当 for 循环读取列表的最后一个元素时，执行 else 块。

## 否则用 break 语句

仅当循环没有被 break 语句终止时，才会执行 for/while 之后的 else 块。

在下面的示例中，else 语句只有在数组中没有元素是偶数的情况下才会被执行，也就是说，如果语句没有被执行任何迭代。因此，对于数组[1，9，8]，if 在循环的第三次迭代中执行，因此 for 循环之后出现的 else 被忽略。在数组[1，3，5]的情况下，if 不在任何迭代中执行，因此在循环执行后执行 else。

```
**示例 1:使用 while 循环**

## 蟒蛇 3

```
def contains_even_number(l):

    n = len(l)
    i = 0
    while i < n:
        if l[i] % 2 == 0:
            print("list contains an even number")
            break
        i += 1

    # This else executes only if break is NEVER
    # reached and loop terminated after all
    # iterations
    else:
        print("list does not contain an even number")

# Driver code 
print ("For List 1:")
contains_even_number([1, 9, 8])
print (" \nFor List 2:")
contains_even_number([1, 3, 5])
```

**输出:**

```
For List 1:
list contains an even number

For List 2:
list does not contain an even number
```

**例 2:用于循环**我们将使用与上面相同的例子，但是这次我们将使用 for 循环而不是 while 循环。

## 蟒蛇 3

```
def contains_even_number(l): 
    for ele in l: 
        if ele % 2 == 0: 
            print ("list contains an even number") 
            break

    # This else executes only if break is NEVER 
    # reached and loop terminated after all
    # iterations. 
    else:      
        print ("list does not contain an even number") 

# Driver code 
print ("For List 1:") 
contains_even_number([1, 9, 8]) 
print (" \nFor List 2:") 
contains_even_number([1, 3, 5])
```

**输出:**

```
For List 1:
list contains an even number

For List 2:
list does not contain an even number
```

```