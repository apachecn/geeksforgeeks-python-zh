# 开始 Python 测试

> 原文:[https://www . geesforgeks . org/python 测试入门/](https://www.geeksforgeeks.org/getting-started-with-testing-in-python/)

在这里，我们将学习如何创建一个基本测试，执行它，并在您的用户之前找到错误！您将了解可用于编写和执行测试的工具，还将看到自动化、手动、单元和集成测试等测试术语。

### **自动测试与手动测试**

<figure class="table">

| **自动化** | **手动测试**
 |
| 测试自动化软件和测试工具一起执行测试用例。 | 显式地，人类参与一步一步地执行测试，他们可能在没有测试脚本的情况下进行测试。 |
| 测试用例是由质量保证工程师编写的，但是执行是完全自动的，而且速度非常快，可以运行 n 种不同的场景。 | 分析师和质量保证工程师需要参与端到端的测试，这很耗时。 |
| 在 Python 中，我们需要安装一个名为“unittest”的包。 | 在 Python 中，通过“白盒测试”、“单元测试”、“集成测试”等。，方法，可以进行手动测试。 |

</figure>

### **单元测试与集成测试**

<figure class="table">

| **单元测试** | **整合测试** |
| 单元测试是在一个组件接一个组件的基础上进行的，因此如果有任何小的组件需要测试，我们需要进行单元测试。 | 集成测试工作在整个组件上，我们可以得出结论，许多单元测试进行集成测试。如果整个集成测试完成，软件也就完成了 |
| 在计算器程序中针对特定参数集单独测试加法计算 | 测试所有算术运算，如加法、减法等。，(无论计算器程序中存在什么)具有不同的参数集 |

</figure>

**单元测试示例:**

## 蟒蛇 3

```py
# define a function
def test_sum_numbers():
    assert sum([100, 200, 300,400]) == 1000, "Result should be 1000"

# define a function
def test_sum_tuple_values():
    assert sum((100, 200, 200,400)) == 1000, "Result should be 1000"

# Driver code
if __name__ == "__main__":

    test_sum_numbers()
    test_sum_tuple_values()

    print("Checking whether all tests are passed or not")
```

**输出:**

```py
Traceback (most recent call last):
 File "....../test_example.py", line 9, in <module>
   test_sum_tuple_values()
 File "...../test_example.py", line 5, in test_sum_tuple_values
   assert sum((100, 200, 200,400)) == 1000, "Result should be 1000"
AssertionError: Result should be 1000
```

在上面的例子中，我们有两个方法，当执行代码时，第二个方法抛出错误，因为给定的值不会产生 1000。

### 选择测试运行程序:

Test Runner 是一个库或测试工具，它读取包含单元测试和一堆可以执行的设置的源代码，并将其输出到控制台或日志文件。
Python 中有不同的测试运行器。受欢迎的有

*   单元测试
*   鼻子或鼻子 2
*   pytest(测试)

**unittest** :内置于标准 python 库中。**导入 unittest** 应该是使用它的代码的起始行。根据 python 版本的不同，应该会有所不同，因为 Python 的较高版本支持 unittest，而较早版本支持 unittest2。
下面给出了使用 unittest 的 python 代码示例片段:

## 蟒蛇 3

```py
# import library
import unittest

# create a class
class TestXXXXX(unittest.TestCase):

      # define a function
    def test_xxxxxxx(self):

        data = [100, 200, 300]
        result = sum(data)
        self.assertEqual(result, 6000)

# driver code
if __name__ == '__main__':

    unittest.main()
```

**输出:**

```py
======================================================================
.F
FAIL: test_xxxxxxx (__main__.TestXXXXX)
----------------------------------------------------------------------
Traceback (most recent call last):
 File "......py", line 8, in test_xxxxxxx
   self.assertEqual(result, 6000)
AssertionError: 600 != 6000
----------------------------------------------------------------------
Ran 1 test in 0.001s
FAILED (failures=1)
```

**nose 或 nose2:** 这是一个开源应用程序，仅与 unittest 类似。它与使用 unittest 框架编写的多种测试兼容。nose2 是最新版本，它们是通过使用。

```py
pip install nose2 
```

**pytest:** 支持 unittest 测试用例执行。它具有支持内置断言语句、过滤测试用例、从上次失败的测试中返回等优点

## 蟒蛇 3

```py
def test_sum_numbers_using_pytest():
    assert sum([700, 900]) == 1600, "Resultant should be 1600"

def test_sum_tuple_using_pytest():
    assert sum((700,1900)) == 1600, "Resultant should be 1600"
```