# Python |单元测试中的异常条件测试

> 原文:[https://www . geesforgeks . org/python-例外-条件-单元内测试-测试/](https://www.geeksforgeeks.org/python-exceptional-conditions-testing-in-unit-tests/)

本文旨在编写一个单元测试，干净利落地测试是否出现异常。为了测试异常，使用**assertrails()**方法。

**代码#1:测试某个函数引发了值错误异常**

```
import unittest

# A simple function to illustrate
def parse_int(s):
    return int(s)

class TestConversion(unittest.TestCase):
    def test_bad_int(self):
        self.assertRaises(ValueError, parse_int, 'N/A')
```

**代码#2:需要用不同的方法测试异常的值**

```
import errno

class TestIO(unittest.TestCase):
    def test_file_not_found(self):
        try:
            f = open('/file/not/found')
        except IOError as e:
            self.assertEqual(e.errno, errno.ENOENT)
        else:
            self.fail('IOError not raised')
```

`assertRaises()` 方法为测试异常的存在提供了一种方便的方法。一个常见的陷阱是编写测试，手动尝试自行处理异常。

**代码#3:示例**

```
class TestConversion(unittest.TestCase):
    def test_bad_int(self):
        try:
            r = parse_int('N/A')
        except ValueError as e:
            self.assertEqual(type(e), ValueError)
```

这种方法的问题是很容易忘记角落案例，比如根本没有提出任何异常的案例。为此，需要为这种情况添加额外的检查，如下面的代码所示。

**代码#4 :**

```
class TestConversion(unittest.TestCase):
    def test_bad_int(self):
        try:
            r = parse_int('N/A')
        except ValueError as e:
            self.assertEqual(type(e), ValueError)
        else:
            self.fail('ValueError not raised')
```

`assertRaises()`方法简单照顾到了这些细节，所以优先使用。`assertRaises()`的一个限制是它没有提供一种方法来测试创建的异常对象的值。
要做到这一点，必须手动测试。在这两个极端之间的某个地方，可以使用**assertraisseregex()**方法，它允许测试异常并同时对异常的字符串表示执行正则表达式匹配。

**代码#5 :**

```
class TestConversion(unittest.TestCase):
    def test_bad_int(self):
        self.assertRaisesRegex(
                ValueError, 'invalid literal .*', 
                parse_int, 'N/A')
```

关于`assertRaises()`和`assertRaisesRegex()`一个鲜为人知的事实是，它们也可以用作上下文管理器。

**代码#6 :**

```
class TestConversion(unittest.TestCase):
    def test_bad_int(self):
        with self.assertRaisesRegex(ValueError, 'invalid literal .*'):
            r = parse_int('N/A')
```

如果除了简单地执行可调用之外，测试还涉及多个步骤(例如，设置)，那么这种形式会很有用。