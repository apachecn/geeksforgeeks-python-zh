# 如何在 Python 中从列表中移除一个项目？

> 原文:[https://www . geesforgeks . org/如何从 python 列表中移除项目/](https://www.geeksforgeeks.org/how-to-remove-an-item-from-the-list-in-python/)

[Python 列表](https://www.geeksforgeeks.org/python-list/)有各种内置方法可以从列表中移除项目。除此之外，我们还可以使用 del 语句通过指定位置从列表中移除元素。让我们看看这些方法–

**方法 1:使用 del 语句**
del 语句不是 List 的函数。通过指定要删除的项目(元素)的索引，可以使用 del 语句删除列表中的项目。

```
# Python 3 code to
# remove an item from list
# using del statement

lst = ['Iris', 'Orchids', 'Rose', 'Lavender',
       'Lily', 'Carnations']
print("Original List is :", lst)

# using del statement
# to delete item (Orchids at index 1) 
# from the list
del lst[1]
print("After deleting the item :", lst)
```

**输出:**

> 原列表为:['鸢尾'，'兰花'，'玫瑰'，'薰衣草'，'百合'，'康乃馨']
> 删除项目后:['鸢尾'，'玫瑰'，'薰衣草'，'百合'，'康乃馨']

**方法二:使用 remove()**
我们可以通过传递要删除的项的值作为 remove()函数的参数，从列表中删除一个项。

```
# Python 3 code to
# remove an item from list
# using function remove()

lst = ['Iris', 'Orchids', 'Rose', 'Lavender',
       'Lily', 'Carnations']
print("Original List is :", lst)

# using remove()
# to delete item ('Orchids') 
# from the list
lst.remove('Orchids')
print("After deleting the item :", lst)
```

**输出:**

> 原列表为:['鸢尾'，'兰花'，'玫瑰'，'薰衣草'，'百合'，'康乃馨']
> 删除项目后:['鸢尾'，'玫瑰'，'薰衣草'，'百合'，'康乃馨']

**方法三:使用 pop()**
pop()也是一种列表的方法。我们可以移除指定索引处的元素，并使用 pop()获取该元素的值。

```
# Python 3 code to
# remove an item from list
# using function pop()

lst = ['Iris', 'Orchids', 'Rose', 'Lavender', 
       'Lily', 'Carnations']
print("Original List is :", lst)

# using pop()
# to delete item ('Orchids' at index 1) 
# from the list
a = lst.pop(1)
print("Item popped :", a)
print("After deleting the item :", lst)
```

**输出–**

> 原列表为:['鸢尾'，'兰花'，'玫瑰'，'薰衣草'，'百合'，'康乃馨']
> 项目弹出:兰花
> 删除项目后:['鸢尾'，'玫瑰'，'薰衣草'，'百合'，'康乃馨']