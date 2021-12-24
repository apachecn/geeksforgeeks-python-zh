# Python–unittest

中的 assertGreaterEqual()函数

> 原文:[https://www . geeksforgeeks . org/python-assertgreaterequal-function-in-unit test/](https://www.geeksforgeeks.org/python-assertgreaterequal-function-in-unittest/)

**Python 中的 assertgreaterequil()**是一个 **unittest** 库函数，用于单元测试中检查第一个给定值是否大于等于第二个值。该函数将采用三个参数作为输入，并根据断言条件返回一个布尔值。

该函数检查第一个给定值是否大于或等于第二个值，如果大于或等于第二个值，则返回真，否则返回假。

> **语法:**assertgreatereleqal(第一，第二，消息=无)
> 
> **参数** : assertGreaterEqual()接受以下列出的三个参数，并进行解释:
> 
> *   **第一个**:第一个输入值(整数)
> *   **秒**:秒输入值(整数)
> *   **消息**:作为测试用例失败时显示的消息的字符串。

下面列出了一个示例，说明了给定断言函数的正测试用例和负测试用例:

**示例:**

## 蟒蛇 3

```
# test suite
import unittest

class TestStringMethods(unittest.TestCase):

    # negative test function to test if values1 is greater or equal than value2
    def test_negativeForGreaterEqual(self):
        first = 4
        second = 5

        # error message in case if test case got failed
        message = "first value is not greater or equal than second value."

        # assert function() to check if values1 is greater or equal than value2
        self.assertGreaterEqual(first, second, message)

if __name__ == '__main__':
    unittest.main()
```

**输出:**

> f
> = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = =
> FAIL:test _ negative greatere qual(_ _ main _ _)。TestStringMethods)
> —————————————————————-
> 回溯(最近一次调用最后一次):
> 文件“p1.py”，第 13 行，在 test _ negative greatere qual
> self . assertgreatere qual(第一个，第二个，消息)
> asserture error:4 不大于或等于 5:第一个值不大于或等于第二个值。
> 
> ———————————————————————】在 0.000 秒内运行 1 次测试
> 
> 失败(失败=1)

**例 2:**

## 计算机编程语言

```
# test suite
import unittest

class TestStringMethods(unittest.TestCase):

    # positive test function to test if values1 is greater than or equal to value2
    def test_positiveForGreaterEqual(self):
        first = 4
        second = 4

        # error message in case if test case got failed
        message = "first value is not greater or equal than second value."

        # assert function() to check if values1 is greater or equal than value2
        self.assertGreaterEqual(first, second, message)

if __name__ == '__main__':
    unittest.main()
```

**输出:**

> 。
> ————————————————————————————————
> 0.000 秒内跑 1 次测试
> 
> 好