# Python 中的猴子补丁(动态行为)

> 原文:[https://www . geesforgeks . org/monkey-python 中的补丁-动态-行为/](https://www.geeksforgeeks.org/monkey-patching-in-python-dynamic-behavior/)

在 Python 中，术语猴子补丁指的是对类或模块的动态(或运行时)修改。在 Python 中，我们实际上可以在运行时改变代码的行为。

```
# monk.py
class A:
     def func(self):
          print ("func() is being called")
```

我们在下面的代码中使用上面的模块(monk)，并在运行时通过分配不同的值来改变 func()的行为。

```
import monk
def monkey_f(self):
     print ("monkey_f() is being called")

# replacing address of "func" with "monkey_f"
monk.A.func = monkey_f
obj = monk.A()

# calling function "func" whose address got replaced
# with function "monkey_f()"
obj.func()
```

示例:

```
Output :monkey_f() is being called

```