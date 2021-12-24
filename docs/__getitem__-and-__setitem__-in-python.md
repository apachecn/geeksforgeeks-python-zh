# _ _ Python 中的 getitem__ 和 _ _ setitem _ _

> 原文:[https://www . geesforgeks . org/_ _ getitem _ _-和 __setitem__-in-python/](https://www.geeksforgeeks.org/__getitem__-and-__setitem__-in-python/)

Dunder 方法是双下划线方法，用于模拟内置类型的行为。它们是预定义的方法，简化了许多可以在类实例上执行的操作，如 __init__()、__str__()、__call__()等。这些方法非常有用，因为它们用于二进制运算、赋值运算、一元和二进制比较运算。

**注意:**更多信息请参考[邓德或者 Python 中的魔法方法](https://www.geeksforgeeks.org/dunder-magic-methods-python/)

## __getitem__ 和 __setitem__

作为这些神奇方法的一部分，有 getter 和 setter 方法。它们通过`__getitem__()`和`__setitem__()`方法实现。但是，这些方法仅用于索引属性，如数组、字典、列表等。它提供了这样的方法，而不是直接访问和操作类属性，因此这些属性只能由它自己的实例修改，从而实现抽象。

这些方法不是将类属性设为公共属性，而是将其设为私有属性，并提供验证，即只有正确的值被设置为属性，并且只有正确的调用方才能访问这些属性。

让我们以一个人的银行记录为例。它包含余额、交易历史和其他机密记录。现在，这个银行记录需要作为一个内置的数据类型来处理，以方便许多操作。有几种方法需要访问余额和交易历史记录。如果他们直接修改余额，他们可能最终会插入空值，或者非常脆弱的负值。因此，`__getitem__()`和`__setitem__()`有助于安全地呈现细节。

**例:**

```py
class bank_record:

    def __init__(self, name):

        self.record = {
                        "name": name,
                        "balance": 100,
                        "transaction":[100]
                        }

    def __getitem__(self, key):

        return self.record[key]

    def __setitem__(self, key, newvalue):

        if key =="balance" and newvalue != None and newvalue>= 100:
            self.record[key] += newvalue

        elif key =="transaction" and newvalue != None:
            self.record[key].append(newvalue)

    def getBalance(self):
        return self.__getitem__("balance")

    def updateBalance(self, new_balance):

        self.__setitem__("balance", new_balance)
        self.__setitem__("transaction", new_balance)    

    def getTransactions(self):
        return self.__getitem__("transaction")

    def numTransactions(self):
        return len(self.record["transaction"])

sam = bank_record("Sam")
print("The balance is : "+str(sam.getBalance()))

sam.updateBalance(200)
print("The new balance is : "+str(sam.getBalance()))
print("The no. of transactions are: "+str(sam.numTransactions()))

sam.updateBalance(300)
print("The new balance is : "+str(sam.getBalance()))
print("The no. of transactions are: "+str(sam.numTransactions()))
print("The transaction history is: "+ str(sam.getTransactions()))
```

**输出**

```py
The balance is : 100
The new balance is : 300
The no. of transactions are: 2
The new balance is : 600
The no. of transactions are: 3
The transaction history is: [100, 200, 300]
```

在这里你可以看到，实现`numTransactions()`、`getTransactions()`、`getBalance()`、`setBalance()`有多容易，只需要通过实现`__getitem__()`和`__setitem__()`的方法。此外，它还负责余额和交易历史的验证。