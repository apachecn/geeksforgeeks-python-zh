# 使用 Python 中的 Mutpy 模块进行突变测试

> 原文:[https://www . geeksforgeeks . org/突变测试-使用-mutpy-模块-in-python/](https://www.geeksforgeeks.org/mutation-testing-using-mutpy-module-in-python/)

**先决条件:** [突变检测](https://www.geeksforgeeks.org/software-testing-mutation-testing/)

**Mutpy** 是 Python 中的一个突变测试工具，它生成突变体并计算突变分数。它支持标准的 unittest 模块，生成 YAML/HTML 报告，并有丰富多彩的输出。它在 AST 水平上应用突变。

### 安装:

这个模块没有内置 Python。要安装它，请在终端中键入以下命令。

```
pip install mutpy

```

在这里，我们将使用 Mutpy 库来执行为一个简单程序编写的测试用例。

现在，我们对一个程序执行**突变测试，这个程序检查一个数是否是质数**。

**代码:** *此代码保存为*isprime . py

## python 3

```
# define a function 
def isPrime(num):

    if num > 1:

       # check for factors
       for i in range(2,num):
           if (num % i) == 0:
               return False

       else:
           return True

    # if input number is less than
    # or equal to 1, it is not prime
    else:
       return False;
```

现在，我们需要使用 **Pytest** 或 **Unittest** 库为上述程序编写测试用例。测试用例应该用杀死所有突变的方法来编写，即测试用例应该足够有效以给出一个好的突变分数。测试用例是使用如下所示文件中的**单元测试**库编写的。

测试用例是使用**self . asserteqal()**编写的，这是一个测试断言，通常用于确定测试用例是通过还是失败。我们在下面编写了三个测试函数来检查三种类型的输入:

1.  Enter as prime number.
2.  Input is a non-prime number.
3.  Invalid input

**注意:**函数名和测试文件名都要以‘test’字开头。

**代码:**此代码另存为 test _ isprime . py .

T5】python 3T0T9

为了执行这些测试用例，我们需要在单个文件夹中创建两个单独的文件 *isPrime.py* 和 *test_isPrime.py* ，并在命令提示符下运行以下命令:

```
mut.py --target isPrime --unit-test test_isPrime -m --runner pytest

```

在上面的命令中，我们必须指定三件事:

*   **Target:** The target file that will run the test case, in our example, *isprime.py*
*   **Unit test:** A file with unit tests that must be performed, that is, *test _ isprime.py* in our example.
*   **菲兰达:# t1]pytest 阿力单元测试**

输出将是一组突变体以及细节，如突变分数、被杀死的突变数量、存活下来的突变数量等。

```
[*] Start mutation process:
   - targets: isPrime
   - tests: test_isPrime
[*] 3 tests passed:
   - test_isPrime [3.07469 s]
[*] Start mutants generation and execution:
   - [#   1] AOR isPrime:
--------------------------------------------------------------------------------
   3:
   4:     if num > 1:
   5:
   6:         for i in range(2, num):
-  7:             if num % i == 0:
+  7:             if num * i == 0:
   8:                 return False
   9:         else:
  10:
  11:             return True
--------------------------------------------------------------------------------
[1.45151 s] killed by testing program mutpy/test_isPrime.py::CalculatorTest::test_nonprime
   - [#   2] COI isPrime:
--------------------------------------------------------------------------------
   1:
   2: def isPrime(num):
   3:
-  4:     if num > 1:
+  4:     if not (num > 1):
   5:
   6:         for i in range(2, num):
   7:             if num % i == 0:
   8:                 return False
--------------------------------------------------------------------------------
[1.25723 s] killed by testing program mutpy/test_isPrime.py::CalculatorTest::test_invalid
   - [#   3] COI isPrime:
--------------------------------------------------------------------------------
   3:
   4:     if num > 1:
   5:
   6:         for i in range(2, num):
-  7:             if num % i == 0:
+  7:             if not (num % i == 0):
   8:                 return False
   9:         else:
  10:
  11:             return True
--------------------------------------------------------------------------------
[1.28817 s] killed by testing program mutpy/test_isPrime.py::CalculatorTest::test_prime
   - [#   4] CRP isPrime:
--------------------------------------------------------------------------------
   1:
   2: def isPrime(num):
   3:
-  4:     if num > 1:
+  4:     if num > 2:
   5:
   6:         for i in range(2, num):
   7:             if num % i == 0:
   8:                 return False
--------------------------------------------------------------------------------
[1.23510 s] survived
   - [#   5] CRP isPrime:
--------------------------------------------------------------------------------
   2: def isPrime(num):
   3:
   4:     if num > 1:
   5:
-  6:         for i in range(2, num):
+  6:         for i in range(3, num):
   7:             if num % i == 0:
   8:                 return False
   9:         else:
  10:
--------------------------------------------------------------------------------
[1.20360 s] survived
   - [#   6] CRP isPrime:
--------------------------------------------------------------------------------
   3:
   4:     if num > 1:
   5:
   6:         for i in range(2, num):
-  7:             if num % i == 0:
+  7:             if num % i == 1:
   8:                 return False
   9:         else:
  10:
  11:             return True
--------------------------------------------------------------------------------
[1.23499 s] killed by testing program mutpy/test_isPrime.py::CalculatorTest::test_prime
   - [#   7] ROR isPrime:
--------------------------------------------------------------------------------
   1:
   2: def isPrime(num):
   3:
-  4:     if num > 1:
+  4:     if num < 1:
   5:
   6:         for i in range(2, num):
   7:             if num % i == 0:
   8:                 return False
--------------------------------------------------------------------------------
[1.24164 s] killed by testing program mutpy/test_isPrime.py::CalculatorTest::test_invalid
   - [#   8] ROR isPrime:
--------------------------------------------------------------------------------
   1:
   2: def isPrime(num):
   3:
-  4:     if num > 1:
+  4:     if num >= 1:
   5:
   6:         for i in range(2, num):
   7:             if num % i == 0:
   8:                 return False
--------------------------------------------------------------------------------
[1.21934 s] survived
   - [#   9] ROR isPrime:
--------------------------------------------------------------------------------
   3:
   4:     if num > 1:
   5:
   6:         for i in range(2, num):
-  7:             if num % i == 0:
+  7:             if num % i != 0:
   8:                 return False
   9:         else:
  10:
  11:             return True
--------------------------------------------------------------------------------
[1.32597 s] killed by testing program mutpy/test_isPrime.py::CalculatorTest::test_prime
[*] Mutation score [14.91747 s]: 66.7%
   - all: 9
   - killed: 6 (66.7%)
   - survived: 3 (33.3%)
   - incompetent: 0 (0.0%)
   - timeout: 0 (

```

从上面的输出我们可以看到，已经有 6 个突变体被杀死，只有 3 个突变体能够存活。此外，突变得分达到 66.7%。我们可以通过分析从测试用例中幸存下来的突变体，并编写新的或修改测试用例来杀死幸存下来的突变体，从而进一步提高这一突变分数。