# Python delattr()函数

> 原文:[https://www.geeksforgeeks.org/python-delattr-function/](https://www.geeksforgeeks.org/python-delattr-function/)

Python delattr()函数用于从类中删除属性。它需要两个参数，第一个是我们要从中删除的类对象，第二个是我们要删除的属性的名称。

**语法**

```py
delattr (object, name)  
```

**参数**

<figure class="table">

| 

**参数**

 | 

**描述**

 |
| --- | --- |
| 目标 | 我们要从中删除属性的对象 |
| 名字 | 我们要删除的属性的名称 |

</figure>

delattr()方法返回一个复数。

**例 1:**

创建一个带有属性名称、持续时间、价格、评级的课程。该类的一个实例被创建，现在我们使用 delattr()方法删除**评级**属性。最后，我们检查**等级**属性是否存在。尝试块用于处理密钥错误

## 蟒蛇 3

```py
class course:
    name = "data structures using c++"
    duration_months = 6
    price = 20000
    rating = 5

# creating an object of course
print(course.rating)

# deleting the rating attribute from object
delattr(course, 'rating')

# checking if the rating attribute is there or not
try:
    print(course.rating)
except Exception as e:
    print(e)
```

**Output**

```py
5
type object 'course' has no attribute 'rating'
```

**例 2:**

创建一个带有属性名称、持续时间、价格、评级的课程。创建了类的一个实例，现在我们使用 delattr()方法删除**价格**属性。最后，我们检查**价格**属性是否存在。尝试块用于处理密钥错误

## 蟒蛇 3

```py
class course:
    name = "data structures using c++"
    duration_months = 6
    price = 20000
    rating = 5

# creating an object of course
print(course.price)

# deleting the price attribute from object
delattr(course, 'price')

# checking if the price attribute is there or not
try:
    print(course.price)
except Exception as e:
    print(e)
```

**Output**

```py
20000
type object 'course' has no attribute 'price'
```