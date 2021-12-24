# 如何把字典变成一个类？

> 原文:[https://www . geeksforgeeks . org/如何将字典变成类/](https://www.geeksforgeeks.org/how-to-change-a-dictionary-into-a-class/)

使用[字典](https://www.geeksforgeeks.org/python-dictionary/)是一件好事，但是当我们有很多字典时，它就变得很难使用。那么让我们来了解一下如何将字典转换成类。

### **接近**

让我们以一个简单的字典“my_dict”为例，它将名称、等级和主题作为我的关键字，并将它们对应的值作为 Geeks、1223、Python。我们在这里调用一个函数 **Dict2Class** ，这个函数将我们的字典作为输入，并将其转换为类。然后，我们使用**[**setattr()**](https://www.geeksforgeeks.org/python-setattr-method/)**函数将每个键作为属性添加到类中，从而循环遍历字典。****

****setattr()用于为对象属性赋值。除了通过构造函数和对象函数将值赋给类变量的方法之外，该方法还为您提供了一种赋值的替代方法。****

> ******语法:** setattr(obj，var，val)****
> 
> *******参数:***
> ***对象:**要分配哪个属性的对象。*
> ***var :** 必须分配的对象属性。*
> ***val :** 变量赋值的值。*****
> 
> *******返回:***
> *无*****

*****下面是实现。*****

## ****蟒蛇 3****

```
**# Turns a dictionary into a class
class Dict2Class(object):

    def __init__(self, my_dict):

        for key in my_dict:
            setattr(self, key, my_dict[key])

# Driver Code
if __name__ == "__main__":

    # Creating the dictionary
    my_dict = {"Name": "Geeks",
               "Rank": "1223",
               "Subject": "Python"}

    result = Dict2Class(my_dict)

    # printing the result
    print("After Converting Dictionary to Class : ")
    print(result.Name, result.Rank, result.Subject)
    print(type(result))**
```

******输出:******

```
**After Converting Dictionary to Class : 
Geeks 1223 Python
<class '__main__.Dict2Class'>** 
```