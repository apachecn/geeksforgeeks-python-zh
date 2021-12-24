# Python 中的默认参数

> 原文:[https://www.geeksforgeeks.org/default-arguments-in-python/](https://www.geeksforgeeks.org/default-arguments-in-python/)

Python 允许函数参数有默认值。如果在没有参数的情况下调用函数，参数将获得默认值。

### **默认参数:**

Python 有一种不同的方式来表示函数参数的语法和默认值。默认值指示如果在函数调用期间没有传递参数值，函数参数将采用该值。默认值通过使用表单*关键字名称*=值的赋值(=)操作符来赋值。
让我们通过一个函数*学生*来理解这一点。函数*学生*包含 3 个参数，其中 2 个参数被赋予默认值。所以函数*学生*接受一个必选参数(*名*，其余两个参数可选。

## 蟒蛇 3

```py
def student(firstname, lastname ='Mark', standard ='Fifth'):

     print(firstname, lastname, 'studies in', standard, 'Standard')
```