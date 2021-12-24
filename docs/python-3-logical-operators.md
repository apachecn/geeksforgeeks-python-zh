# Python 3 – Logical Operators

> 原文：[https://www.geeksforgeeks.org/python-3-logical-operators/](https://www.geeksforgeeks.org/python-3-logical-operators/)

Logical Operators are used to perform certain logical operations on values and variables. These are the special reserved keywords that carry out some logical computations. The value the operator operates on is known as Operand. In Python, they are used on conditional statements (either True or False), and as a result, they return boolean only (True or False). They are used to combine conditional statements

There are following logical operators supported by Python language:

*   Logical AND
*   Logical OR
*   Logical NOT

## **Logical AND**

Logical operator **AND** returns True only if both the operands are True else it returns False. It is a binary operator, which means to return some value, it has to be operated between two operators (i.e, two operators are required)

**Truth Table:**

<figure class="table">

| Operator A | Operator B | Logical **AND** result |
| --- | --- | --- |
| True | True | True |
| True | False | False |
| False | True | False |
| False | False | False |

</figure>

**Example 1:**

## Python3

```

a = 12
b = 26
c = 4

if a > b and a > c: 
    print("Number a is larger") 

if b > a and b > c: 
    print("Number b is larger") 

if c > a and c > b:    
    print("Number c is larger") 
```

**Output:**

```
Number b is larger

```

**Example 2:**

## Python3

```
a = 10

if (a == 0 and "Hello"):
    print("a has value zero(0)")
else:
    print("a is not equal to zero")
```

**Output:**

```
a is not equal to zero

```

If the first expression evaluated to be false while using and operator, then further expressions are not evaluated. Also, any string is always considered a true statement. In the above example, the first condition is false and hence it will not check the second condition and hence, it will not check for another condition and it will go to *else* statement.

## **Logical OR**

The logical operator **OR** returns False only if both the operands are False else it returns True. It is a binary operator, which means to return some value, it has to be operated between two operators (i.e, two operators are required)

**Truth Table:**

<figure class="table">

| Operator A | Operator B | Logical **OR** Result |
| --- | --- | --- |
| True | True | True |
| True | False | True |
| False | True | True |
| False | False | False |

</figure>

**Example 1:**

## Python3

```
a = 10
b = -5

if a < 0 or b < 0:
  print("Their product will be negative")
else:
  print("Their product will be positive")
```

**Output:**

```
Their product will be negative

```

**Example 2:**

## Python3

```
a = 10

if (a == 0 or "GeeksForGeeks"):
  print("Is Awesome")
else:
  ("Try Again!")
```

**Output:**

```
Is Awesome

```

Here, in the **OR** Logical operator, even if the first expression evaluated is false while using and operator, then also the further expressions are evaluated. Also, any string is always considered a true statement. In the above example, the first statement is false but then too, it will evaluate the second statement because it returns False only if both the operands are False and since the string is considered as True statement, thus, it will be evaluated and the below print statement will be printed.

## Logical NOT

Logical **NOT** operator works with the single boolean value and returns the value as True if the boolean value is False and vice-versa (that is the opposite of it).  It is a unary operator, which means to return some value, it has to be operated on one operator only. (i.e, only operator is required)

**Truth Table:**

<figure class="table">

| Operator A | Logical **NOT Result** |
| --- | --- |
| True | False |
| False | True |

</figure>

**Example 1:**

## Python3

```
a = 10

if not a == 10:
  print ("a not equals 10")
else:
  print("a equals 10")
```

**Output:**

```
a equals 10

```

Here, a is equal to 10 the boolean a == 10 return the value True. Hence, the boolean **not** a == 10 will return the value as False and since the *if* condition is not satisfied, it will jump to *else* statement. 

**Example 2:**

## Python3

```
a = 10

if not a%5 == 0:
  print("a is not perfectly divisible by 5")
else:
  print("a is perfectly divisible by 5")
```

**Output:**

```
a is perfectly divisible by 5

```