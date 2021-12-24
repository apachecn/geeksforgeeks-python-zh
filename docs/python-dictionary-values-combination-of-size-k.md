# Python–大小为 K 的字典值组合

> 原文:[https://www . geesforgeks . org/python-dictionary-values-size-k 组合/](https://www.geeksforgeeks.org/python-dictionary-values-combination-of-size-k/)

有时，在使用 Python 字典时，我们可能会遇到一个问题，即我们需要提取大小为 k 的某个键的值的组合。这通常是当值是字符串形式时。这可以在日常编程中应用。让我们讨论一下执行这项任务的方法。

> **输入** : test_dict = {'a' : 'a '，' b' : 'b '，' c' : 'c '，' d' : 'd'}
> **输出** : ['aaa '，' bbb '，' ccc '，' ddd']
> **输入** : test_dict = {'a' : 'abcd '，' b ':，' c ':，' d' : "}
> **输出** : ['aaa '，' aab '，' aac '，' aad']

**方法:使用递归+生成函数+ yield**
以上功能的组合可以用来解决这个问题。在这种情况下，我们使用递归执行所有可能的组合任务。生成器函数用于动态创建值，并使用 yield 返回调用函数。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Dictionary values combination of size K
# Using yield + generator function + recursion

def gen_strs(chr_key, test_dict, K):
    def hlpr(s):
        if len(s) == K:
            yield s
        elif len(s) < K:
            for ltr in test_dict[s[-1]]:
                yield from hlpr(s + ltr)
    for ltr in chr_key:
        yield from hlpr(ltr)

# initializing dictionary
test_dict = {'a' : 'abc', 'b' : 'bd', 'c' : 'c', 'd' : 'ab'}

# printing original dictionary
print("The original dictionary : " + str(test_dict))

# initializing K
K = 3

# initializing character keys
chr_key = 'abcd'

# Dictionary values combination of size K
# Using yield + generator function + recursion
res = []
for ele in gen_strs(chr_key, test_dict, K):
    res.append(ele)

# printing result
print("The extracted combinations : " + str(res))
```

**Output : **

原始字典:{'b': 'bd '，' a': 'abc '，' d': 'ab '，' c': 'c'}
提取的组合:['aaa '，' aab '，' aac '，' abb '，' abd '，' acc '，' bbb '，' bbd '，' bda '，' bdb '，' ccc '，' dab '，' dac '，' dbb '，' dbd']