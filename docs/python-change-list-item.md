# Python–变更列表项

> 原文:[https://www.geeksforgeeks.org/python-change-list-item/](https://www.geeksforgeeks.org/python-change-list-item/)

python 中的 List 是可变类型，这意味着它可以在赋值后改变。该列表类似于其他编程语言中的数组。在本文中，我们将看到如何在 python 中更改列表项。

### **我们先来了解一下如何访问 python 中的元素:**

*   正在访问列表[0]中的第一个元素
*   访问第二个元素 mylist[1]
*   访问最后一个元素 mylist[-1]或 mylist[len(mylist)-1]

## 蟒蛇 3

```
# code
gfg = [ 10, 20, 30, 40, 50, 60]

#first element
print(gfg[0])

#second element
print(gfg[1])

#last element
print(gfg[-1])
```

**输出:**

```
10
20
60
```

### **现在我们可以用不同的方法改变物品列表:**

**示例 1:** 更改单个列表项。

**进场:**

*   更改第一个元素 my list[0]=值
*   更改第三个元素 my list[2]=值
*   更改第四个元素 my list[3]=值

**代码:**

## 蟒蛇 3

```
# list
List=[ 10, 20, 30, 40, 50, 60]
print("original list ")
print(List)

#changing the first value
List[0] = 11

#changing the second value
List[1] = 21

#changing the last element
List[ -1] = 61

print("\nNew list")
print(List)
```

**输出:**

```
original list 
[10, 20, 30, 40, 50, 60]

New list
[11, 21, 30, 40, 50, 61]
```

**示例 2:** 使用循环更改所有值。

## 蟒蛇 3

```
# list
list = [ 10, 20, 30, 40, 50, 60]
print("Original list ")
print(list)

print("After incrementing each element of list by 2")  

# adding 2 to each value of list
# len method to calculate length of list
# range method is used to go upto a certain range
for i in range( len(list)):
    list[i] = list[i] + 2

print(list)
```

**输出:**

```
Original list 
[10, 20, 30, 40, 50, 60]
After incrementing each element of list by 2
[12, 22, 32, 42, 52, 62]
```

**示例 3:** 使用列表理解更改列表的所有值。

## 蟒蛇 3

```
# list
List_1 = [ 10, 20, 30, 40, 50]
print("Original list ")
print(List_1)

print("After incrementing each element of list by 2")
List_2=[ i+2 for i in List_1]

print(List_2)
```

**输出:**

```
Original list 
[10, 20, 30, 40, 50]
After incrementing each element of list by 2
[12, 22, 32, 42, 52]
```