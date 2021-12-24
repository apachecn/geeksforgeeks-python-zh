# 使用 Python 中的 PyWebIO 模块创建登记表

> 原文:[https://www . geesforgeks . org/create-a-registration-form-use-pywebio-module-in-python/](https://www.geeksforgeeks.org/create-a-registration-form-using-pywebio-module-in-python/)

在本文中，我们将使用 PyWebIO 模块创建一个注册表单。这是一个 Python 模块，主要用于使用 Python 编程在本地网站上创建简单的交互式界面。

此表单将输入用户名、姓名、密码、电子邮件、网站链接。说到密码，它还会再次检查你的密码，确认你的密码是否正确。它还将验证您的电话号码、网站链接、电子邮件地址。之后，您将获得由性别组成的单选按钮，您还将获得评论部分，以便您可以写下您的反馈。

### **表单元素**

为了创建一个具有验证的适当表单，我们将通过示例一个接一个地学习不同的表单元素。

**1。input_group:** 这个元素用于获取组中的输入。当我们使用 **input_group** 时，我们需要为每个输入函数提供**名称**参数来识别结果中的输入项。

> **语法:** input_group("Title "，[input('Any name '，name = ' Any ')、input('Any name '，name = ' Any ')])

## 蟒蛇 3

```py
info = input_group("Group inputs", [
     input('Username', name='username'),
     input('Password', name='pass')])
```

**输出:**

![](img/45638f4d181a6c35ecdf2edb28cc9f1a.png)

**2。输入:**该元素用于从浏览器中获取用户的各种输入。

> **语法:**输入(“某些文本”)

## 蟒蛇 3

```py
input("Your name")
```