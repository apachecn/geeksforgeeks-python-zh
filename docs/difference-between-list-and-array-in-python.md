# Python 中列表和数组的区别

> 原文:[https://www . geesforgeks . org/python 中列表和数组的区别/](https://www.geeksforgeeks.org/difference-between-list-and-array-in-python/)

**[列表:](https://www.geeksforgeeks.org/python-list/)**Python 中的列表是可以包含多种数据类型元素的项目集合，这些数据类型可以是数字、字符逻辑值等。这是一个支持负索引的有序集合。可以使用包含数据值的[]创建列表。
使用 python 的内置函数，可以轻松合并和复制列表内容。

```py
# creating a list containing elements 
# belonging to different data types
sample_list = [1,"Yash",['a','e']]
print(sample_list)
```

**输出:**

```py
[1, 'Yash', ['a', 'e']]

```

第一个元素是整数，第二个是字符串，第三个是字符列表。

**[数组:](https://www.geeksforgeeks.org/python-arrays/)** 数组是包含同质元素的向量，即属于同一数据类型。元素被分配了连续的内存位置，允许容易的修改，即元素的添加、删除和访问。在 Python 中，我们必须使用`array`模块来声明数组。如果数组的元素属于不同的数据类型，则会引发异常“不兼容的数据类型”。

```py
# creating an array containing same 
# data type elements 
import array

sample_array = array.array('i', [1, 2, 3])  

# accessing elements of array
for i in sample_array:
     print(i)
```

**输出:**

```py
1
2
3

```

下面是 Python 中列表和数组的区别:

| 目录 | 排列 |
| --- | --- |
| 可以由属于不同数据类型的元素组成 | 仅由属于同一数据类型的元素组成 |
| 无需显式导入模块进行声明 | 需要显式导入模块进行声明 |
| 无法直接处理算术运算 | 可以直接处理算术运算 |
| 可以嵌套以包含不同类型的元素 | 必须包含所有相同大小的嵌套元素 |
| 对于较短的数据项序列是首选的 | 对于较长的数据项序列是首选的 |
| 更大的灵活性允许轻松修改(添加、删除)数据 | 灵活性降低，因为添加、删除必须按元素进行 |
| 可以打印整个列表，而无需任何显式循环 | 必须形成一个循环来打印或访问数组的组件 |
| 消耗更大的内存，以便轻松添加元素 | 内存大小相对更紧凑 |