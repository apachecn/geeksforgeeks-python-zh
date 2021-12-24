# 使用 Python 的基本计算器程序

> 原文:[https://www . geesforgeks . org/make-simple-calculator-use-python/](https://www.geeksforgeeks.org/make-simple-calculator-using-python/)

创建一个简单的计算器，它可以根据用户输入执行基本的算术运算，如加法、减法、乘法或除法。
**进场:**

*   用户选择所需的操作。选项 1、2、3 和 4 有效。*   取两个数字，用 if…elif…else 分支来执行特定的部分。*   Using functions add(), subtract(), multiply() and divide() evaluate respective operations.

    例:

    ```py
    Please select operation -
    1\. Add
    2\. Subtract
    3\. Multiply
    4\. Divide
    Select operations form 1, 2, 3, 4 : 1
    Enter first number : 20
    Enter second number : 13
    20 + 13 = 33

    ```

    ```py
    # Python program for simple calculator

    # Function to add two numbers 
    def add(num1, num2):
        return num1 + num2

    # Function to subtract two numbers 
    def subtract(num1, num2):
        return num1 - num2

    # Function to multiply two numbers
    def multiply(num1, num2):
        return num1 * num2

    # Function to divide two numbers
    def divide(num1, num2):
        return num1 / num2

    print("Please select operation -\n" \
            "1\. Add\n" \
            "2\. Subtract\n" \
            "3\. Multiply\n" \
            "4\. Divide\n")

    # Take input from the user 
    select = int(input("Select operations form 1, 2, 3, 4 :"))

    number_1 = int(input("Enter first number: "))
    number_2 = int(input("Enter second number: "))

    if select == 1:
        print(number_1, "+", number_2, "=",
                        add(number_1, number_2))

    elif select == 2:
        print(number_1, "-", number_2, "=",
                        subtract(number_1, number_2))

    elif select == 3:
        print(number_1, "*", number_2, "=",
                        multiply(number_1, number_2))

    elif select == 4:
        print(number_1, "/", number_2, "=",
                        divide(number_1, number_2))
    else:
        print("Invalid input")
    ```

    输出:

    ```py
    Please select operation -
    1\. Add
    2\. Subtract
    3\. Multiply
    4\. Divide
    Select operations form 1, 2, 3, 4 : 1
    Enter first number : 15
    Enter second number : 14
    15 + 14 = 29

    ```