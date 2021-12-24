# Python–unittest 中的 assertLess()函数

> 原文:[https://www . geesforgeks . org/python-assertless-function-in-unit test/](https://www.geeksforgeeks.org/python-assertless-function-in-unittest/)

Python 中的 assertLess()是一个 [unittest](https://www.geeksforgeeks.org/unit-testing-python-unittest/) 库函数，用于单元测试中检查第一个给定值是否小于第二个给定值。该函数将采用三个参数作为输入，并根据断言条件返回一个布尔值。

该函数检查第一个给定值是否小于第二个给定值，如果小于，则返回真，否则如果第一个给定值不小于第二个给定值，则返回假。

> **语法:**无资产(第一，第二，消息=无)
> 
> **参数** : assertLess()接受以下列出的三个参数，并进行解释:
> 
> *   **第一个**:第一个输入值(整数)
> *   **秒**:秒输入值(整数)
> *   **消息**:作为测试用例失败时显示的消息的字符串。

下面列出了一个示例，说明了给定断言函数的正测试用例和负测试用例:

**例 1** :如果第一个值不小于第二个值。

## 蟒蛇 3

```
# test suite
import unittest

class TestStringMethods(unittest.TestCase):

    # negative test function to test if
    # values1 is less than value2
    def test_negativeForLess(self):
        first = 6
        second = 5

        # error message in case if test case got failed
        message = "first value is not less that second value."

        # assert function() to check if values1 is
        # less than value2
        self.assertLess(first, second, message)

# main for function call
if __name__ == '__main__':
    unittest.main()
```

**输出:**

> f
> = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = =
> FAIL:test _ negative forless(_ _ main _ _)。TestStringMethods)
> ————————————————————-
> 回溯(最近一次调用最后一次):
> 文件“p1.py”，第 13 行，在 test _ negative forless
> self . assertless(第一，第二，消息)
> asserterror:5 不小于 5:第一个值不小于第二个值。
> 
> ———————————————————————】在 0.000 秒内跑了 1 次测试
> 
> 失败(失败=1)

**例 2:** 如果第一给定值小于第二给定值

## 计算机编程语言

```
# test suite
import unittest

class TestStringMethods(unittest.TestCase):

    # positive test function to test if 
    # values are almost equal with place
    def test_positiveForLess(self):
        first = 2
        second = 3

        # error message in case if test case got failed
        message = "first value is not less that second value."

        # assert function() to check if values1 is
        # less than value2
        self.assertLess(first, second, message)

# main for function call
if __name__ == '__main__':
    unittest.main()
```

**输出:**

> 。
> ————————————————————————————————
> 0.000 秒内跑 1 次测试
> 
> 好