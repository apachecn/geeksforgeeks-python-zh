# 使用 Python 进行自动化软件测试

> 原文:[https://www . geesforgeks . org/automated-software-testing-with-python/](https://www.geeksforgeeks.org/automated-software-testing-with-python/)

软件测试是开发人员通过向软件提供一些测试输入来确保软件的实际输出与期望输出相匹配的过程。软件测试是一个重要的步骤，因为如果执行得当，它可以帮助开发人员在很短的时间内发现软件中的错误。

软件测试可以分为两类，**人工测试**和**自动化测试**。自动化测试是使用脚本而不是人工来执行测试。在本文中，我们将讨论使用 Python 进行自动化软件测试的一些方法。

让我们编写一个简单的应用程序来执行所有的测试。

```
class Square:
    def __init__(self, side):
        """ creates a square having the given side
        """
        self.side = side

    def area(self):
        """ returns area of the square
        """
        return self.side**2

    def perimeter(self):
        """ returns perimeter of the square
        """
        return 4 * self.side

    def __repr__(self):
        """ declares how a Square object should be printed
        """
        s = 'Square with side = ' + str(self.side) + '\n' + \
        'Area = ' + str(self.area()) + '\n' + \
        'Perimeter = ' + str(self.perimeter())
        return s

if __name__ == '__main__':
    # read input from the user
    side = int(input('enter the side length to create a Square: '))

    # create a square with the provided side
    square = Square(side)

    # print the created square
    print(square)
```

**注:**关于`__repr__()`功能的更多信息，请参考[这篇文章](https://www.geeksforgeeks.org/str-vs-repr-in-python/)。

现在我们已经准备好了我们的软件，让我们看看我们的项目文件夹的目录结构，然后，我们将开始测试我们的软件。

```
---Software_Testing
   |--- __init__.py (to initialize the directory as python package)
   |--- app.py (our software)
   |--- tests (folder to keep all test files)
           |--- __init__.py

```

### “单元测试”模块

手动测试的一个主要问题是它需要时间和精力。在手动测试中，我们在一些输入上测试应用程序，如果它失败了，我们要么记下它，要么针对那个特定的测试输入调试应用程序，然后我们重复这个过程。通过 [`unittest`](https://docs.python.org/3/library/unittest.html) ，可以一次性提供所有的测试输入，然后就可以测试你的应用了。最后，您会得到一份详细的报告，其中明确指定了所有失败的测试用例(如果有的话)。

`unittest`模块既有内置的测试框架，也有测试运行器。测试框架是一组在编写测试用例时必须遵循的规则，而测试运行器是一个工具，它用一堆设置来执行这些测试，并收集结果。

**安装:** `unittest`可在 PyPI 获得，可通过以下命令安装–

```
pip install unittest
```

**使用:**我们在 Python 模块中编写测试(。py)。为了运行我们的测试，我们只需使用任何 IDE 或终端执行测试模块。

现在，让我们使用`unittest`模块为上面讨论的小软件编写一些测试。

1.  在名为“tests”的文件夹中创建一个名为`tests.py`的文件。
2.  在`tests.py`导入`unittest`。
3.  Create a class named `TestClass` which inherits from the class `unittest.TestCase`.

    **规则 1:** 所有的测试都是作为类的方法编写的，必须从类`unittest.TestCase`继承。

4.  创建如下所示的测试方法。
    **规则 2:** 每种测试方法的名称都应该以“test”开头，否则会被测试运行人员跳过。

```
def test_area(self):
    # testing the method Square.area().

    sq = Square(2)    # creates a Square of side 2 units.

    # test if the area of the above square is 4 units, 
    # display an error message if it's not.

    self.assertEqual(sq.area(), 4, 
        f'Area is shown {sq.area()} for side = {sq.side} units')
```

**规则 3:** 我们使用特殊的 [`assertEqual()`](https://docs.python.org/2/library/unittest.html#unittest.TestCase.assertEqual) 语句来代替 Python 中内置的 [`assert`](https://www.geeksforgeeks.org/python-assert-keyword/) 语句。

`assertEqual()`的第一个参数是实际输出，第二个参数是期望输出，第三个参数是错误信息，如果两个值彼此不同(测试失败)，则会显示错误信息。

10.  为了运行我们刚刚定义的测试，我们需要调用方法`unittest.main()`，在“tests.py”模块中添加以下几行。

    ```
    if __name__ == '__main__':
        unittest.main()
    ```

    因为这几行,一旦你运行执行脚本“test.py”，函数`unittest.main()`就会被调用,所有的测试都会被执行

    T6】

最后，“tests.py”模块应该类似于下面给出的代码。

```
import unittest
from .. import app

class TestSum(unittest.TestCase):

    def test_area(self):
        sq = app.Square(2)

        self.assertEqual(sq.area(), 4, 
            f'Area is shown {sq.area()} rather than 9')

if __name__ == '__main__':
    unittest.main()
```

写完测试用例后，现在让我们测试应用程序是否有任何错误。要测试您的应用程序，您只需要使用命令提示符或您选择的任何 IDE 执行测试文件“tests.py”。输出应该是这样的。

```
.
----------------------------------------------------------------------
Ran 1 test in 0.000s

OK

```

在第一行中，`.`(点)代表成功的测试，而‘F’代表失败的测试用例。`OK`消息，最后告诉我们所有的测试都成功通过了。

让我们在“tests.py”中添加一些测试，然后重新测试我们的应用程序。

```
import unittest
from .. import app

class TestSum(unittest.TestCase):

    def test_area(self):
        sq = app.Square(2)
        self.assertEqual(sq.area(), 4, 
            f'Area is shown {sq.area()} rather than 9')

    def test_area_negative(self):
        sq = app.Square(-3)
        self.assertEqual(sq.area(), -1, 
            f'Area is shown {sq.area()} rather than -1')

    def test_perimeter(self):
        sq = app.Square(5)
        self.assertEqual(sq.perimeter(), 20, 
            f'Perimeter is {sq.perimeter()} rather than 20')

    def test_perimeter_negative(self):
        sq = app.Square(-6)
        self.assertEqual(sq.perimeter(), -1, 
            f'Perimeter is {sq.perimeter()} rather than -1')

if __name__ == '__main__':
    unittest.main()
```

```
.F.F
======================================================================
FAIL: test_area_negative (__main__.TestSum)
----------------------------------------------------------------------
Traceback (most recent call last):
  File "tests_unittest.py", line 11, in test_area_negative
    self.assertEqual(sq.area(), -1, f'Area is shown {sq.area()} rather than -1 for negative side length')
AssertionError: 9 != -1 : Area is shown 9 rather than -1 for negative side length

======================================================================
FAIL: test_perimeter_negative (__main__.TestSum)
----------------------------------------------------------------------
Traceback (most recent call last):
  File "tests_unittest.py", line 19, in test_perimeter_negative
    self.assertEqual(sq.perimeter(), -1, f'Perimeter is {sq.perimeter()} rather than -1 for negative side length')
AssertionError: -24 != -1 : Perimeter is -24 rather than -1 for negative side length

----------------------------------------------------------------------
Ran 4 tests in 0.001s

FAILED (failures=2)
```

上述测试报告中需要注意的几点是–

*   第一行表示测试 1 和测试 3 成功执行，而测试 2 和测试 4 失败
*   报告中描述了每个失败的测试用例，描述的第一行包含失败测试用例的名称，最后一行包含我们为该测试用例定义的错误消息。
*   在报告的最后，您可以看到失败测试的数量，如果没有测试失败，报告将以`OK`结束

**注:**欲了解更多信息，请阅读 [`unittest`](https://docs.python.org/2/library/unittest.html) 的完整文档。

### “nose2”模块

[`nose2`](https://nose2.readthedocs.io/en/latest/) 的目的是扩展`unittest`使测试更容易。`nose2`与使用`unittest`测试框架编写的测试兼容，可以作为`unittest`测试运行程序的替代。

**安装:** `nose2`可以使用命令从 PyPI 安装，

```
pip install nose2
```

**使用:** `nose2`没有任何测试框架，只是一个与`unittest`测试框架兼容的测试运行器。因此，我们将使用`nose2`运行上面写的相同测试(针对`unittest`)。为了运行测试，我们在项目源目录中使用以下命令(在我们的例子中是“Software_Testing”)，

```
nose2
```

在`nose2`术语中，所有 python 模块(。py)以“test”开头的名称(即 test_file.py，test_1.py)被认为是测试文件。执行时，`nose2`将在以下一个或多个类别下的所有子目录中查找所有测试文件，

*   它们是 python 包(包含“__init__”。py”)。
*   其名称以“test”开头，其后为小写，即 TestFiles，tests。
*   它们被命名为“src”或“lib”。

`nose2`首先加载项目中存在的所有测试文件，然后执行测试。因此，有了`nose2`我们可以自由地在不同文件夹的不同测试文件中分割我们的测试，并立即执行它们，这在处理大量测试时非常有用。

现在让我们了解`nose2`提供的不同定制选项，这些选项可以在测试过程中帮助我们。

1.  **Changing the search directory –**
    If we want to change the directory in which `nose2` searchs for test files, we can do that using the command line arguments `-s` or `--start-dir` as,

    ```
    nose2 -s DIR_ADD DIR_NAME
    ```

    这里，`DIR_NAME`是我们要搜索测试文件的目录，`DIR_ADD`是`DIR_NAME`的父目录相对于项目源目录(即 use)的地址。/"如果测试目录在项目源目录中)。
    当您一次只想测试应用程序的一个特性时，这非常有用。

2.  **Running specific test cases –**
    Using `nose2` we can also run a specific test at a time by using the command line arguments `-s` and `--start-dir` as,

    ```
    nose2 -s DIR_ADD DIR_NAME.TEST_FILE.TEST_CLASS.TEST_NAME
    ```

    *   测试名称:测试方法的名称。
    *   测试类:定义测试方法的类。
    *   测试文件:定义测试用例的测试文件的名称，即 test.py
    *   目录名:测试文件所在的目录。
    *   DIR _ ADD:DIR _ NAME 的父目录相对于项目源的地址。

    使用这个特性，我们可以在特定的输入上测试我们的软件。

3.  **Running tests in a single module –**
    `nose2` can also be used like `unittest` by calling the function `nose2.main()` just like we called `unittest.main()` in previous examples.

    除了上述基本定制之外`nose2`还提供了[高级功能](https://nose2.readthedocs.io/en/latest/configuration.html)，比如加载各种插件和配置文件或者创建你自己的测试运行程序。

### “pytest”模块

[`pytest`](https://docs.pytest.org/en/latest/) 是 python 最流行的测试框架。使用`pytest`你可以测试任何东西，从基本的 python 脚本到数据库、API 和 ui。虽然`pytest`主要用于 API 测试，但在本文中，我们将只介绍`pytest`的基础知识。

**安装:**可以使用命令从 PyPI 安装`pytest`，

```
pip install pytest
```

**使用:**在项目源中使用以下命令调用`pytest`测试运行程序，

```
py.test
```

与`nose2`不同，`pytest`在项目目录内的所有位置寻找测试文件。任何以“test_”开头或以“_test”结尾的文件都被认为是`pytest`术语中的测试文件。让我们在“tests”文件夹中创建一个文件“test_file1.py”作为我们的测试文件。

**创建测试方法:**
`pytest`支持在`unittest`框架中编写的测试方法，但是`pytest`框架提供了更简单的语法来编写测试。参见下面的代码，了解`pytest`框架的测试方法语法。

```
from .. import app

def test_file1_area():
    sq = app.Square(2)
    assert sq.area() == 4, 
        f"area for side {sq.side} units is {sq.area()}"

def test_file1_perimeter():
    sq = app.Square(-1)
    assert sq.perimeter() == -1, 
        f'perimeter is shown {sq.perimeter()} rather than -1'
```

**注:**与`unittest`类似，`pytest`要求所有测试名称以“test”开头。

与`unittest`不同，`pytest`使用默认的 python [`assert`](https://www.geeksforgeeks.org/python-assert-keyword/) 语句，这使得它更容易使用。

注意，现在“tests”文件夹包含两个文件，即“tests.py”(写在`unittest`框架中)和“test_file1.py”(写在`pytest`框架中)。现在让我们运行`pytest`测试运行程序。

```
py.test
```

你会得到一个类似于使用`unittest`得到的报告。

```
============================= test session starts ==============================
platform linux -- Python 3.6.7, pytest-4.4.1, py-1.8.0, pluggy-0.9.0
rootdir: /home/manthan/articles/Software_testing_in_Python
collected 6 items 

tests/test_file1.py .F [ 33%]
tests/test_file2.py .F.F [100%]

=================================== FAILURES ===================================
```

报告右侧的百分比显示了此时已经完成的测试的百分比，即 6 个测试用例中有 2 个在“test_file1.py”结束时完成。

以下是`pytest`附带的一些更基本的定制。

1.  **运行特定的测试文件:**要只运行特定的测试文件，请使用命令，

    ```
    py.test <filename>
    ```

2.  **Substring matching:** Suppose we want to test only the `area()` method of our `Square` class, we can do this using substring matching as follows,

    ```
    py.test -k "area"
    ```

    使用此命令`pytest`将只执行那些名称中有字符串“area”的测试，即“test_file1_area()”、“test_area()”等。

3.  **Marking:** As a substitute to substring matching, marking is another method using which we can run a specific set of tests. In this method we put a mark on the tests we want to run. Observe the code example given below,

    ```
    # @pytest.mark.<tag_name>
    @pytest.mark.area     

    def test_file1_area():
        sq = app.Square(2)
        assert sq.area() == 4, 
            f"area for side {sq.side} units is {sq.area()}"
    ```

    在上面的代码示例中`test_file1_area()`被标记为“区域”。所有标记有标签的测试方法都可以通过使用命令来执行，

    ```
    py.test -m <tag_name>
    ```

4.  **Parallel Processing:** If you have a large number of tests then `pytest` can be customised to run these test methods in parallel. For that you need to install [`pytest-xdist`](https://pypi.org/project/pytest-xdist/) which can be installed using the command,

    ```
    pip install pytest-xdist
    ```

    现在，您可以使用以下命令来使用多处理更快地执行测试，

    ```
    py.test -n 4
    ```

    使用此命令`pytest`分配 4 名工人并行执行测试，您可以根据需要更改此数量。

    如果你的测试是线程安全的，你也可以使用[多线程](https://www.geeksforgeeks.org/operating-system-difference-multitasking-multithreading-multiprocessing/)来加速测试过程。为此您需要安装 [`pytest-parallel`](https://pypi.org/project/pytest-parallel/) (使用画中画)。要在多线程中运行测试，请使用命令，

    ```
    pytest --workers 4
    ```