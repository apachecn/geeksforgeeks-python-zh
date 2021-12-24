# 定位硒蟒中的多种元素

> 原文:[https://www . geesforgeks . org/locating-多元素硒元素-python/](https://www.geeksforgeeks.org/locating-multiple-elements-in-selenium-python/)

Selenium Python 中的定位器策略是用于从页面中定位单个或多个元素并对其执行操作的方法。Selenium 的 Python 模块是为使用 Python 执行自动化测试而构建的。硒 Python 绑定提供了一个简单的应用编程接口，可以使用硒网络驱动程序编写功能/验收测试。安装硒并使用获取方法查看–[导航链接后，您可能想玩更多硒蟒。使用 geeksforgeeks 等 selenium 打开页面后，您可能希望自动单击某些按钮或自动填写表单或任何此类自动任务。本文围绕在 Selenium Python 中定位多个元素展开。](https://www.geeksforgeeks.org/navigating-links-using-get-method-selenium-python/)

## 定位多个元素的定位器策略

硒蟒遵循不同的元素定位策略。人们可以用 7 种不同的方法定位多个元素。以下是 python 中硒的定位策略列表–

| 探测器 | 描述 |
| --- | --- |
| [查找 _ 元素 _by_name](#find_elements_by_name) | 将返回名称属性值与位置匹配的所有元素。 |
| [查找 _ 元素 _by_xpath](#find_elements_by_xpath) | 将返回 xpath 语法与位置匹配的所有元素。 |
| [find _ elements _ by _ link _ text](#find_elements_by_link_text) | 将返回链接文本值与位置匹配的所有元素。 |
| [查找 _ 元素 _by_partial_link_text](#find_elements_by_partial_link_text) | 将返回部分链接文本值与位置匹配的所有元素。 |
| [find _ elements _ by _ tag _ name](#find_elements_by_tag_name) | 将返回具有给定标记名的所有元素。 |
| [find _ elements _ by _ class _ name](#find_elements_by_class_name) | 将返回具有匹配类属性名的所有元素。 |
| [find _ elements _ by _ CSS _ 选择器](#find_elements_by_class_name) | 将返回所有具有匹配 CSS 选择器的元素。 |

#### 按名称查找元素

使用此策略，将返回名称属性值与位置匹配的所有元素。如果没有元素具有匹配的名称属性，将引发 NoSuchElementException。

**Syntax –**

```py
driver.find_elements_by_name("name_of_element")

```

**示例–**
例如，考虑一下这个页面来源:

```py
<html>
 <body>
  <form id="loginForm">
   <input name="username" type="text" />
   <input name="username" type="username" />
   <input name="continue" type="submit" value="Login" />
  </form>
 </body>
<html>
```

现在，在您创建了驱动程序之后，您可以使用–

```py
elements = driver.find_elements_by_name('username')

```

要查看实际实现，请访问–[查找 _elements_by_name()驱动程序方法–硒 Python](https://www.geeksforgeeks.org/find_elements_by_name-driver-method-selenium-python/?ref=rp)

#### 查找元素 by XPath

使用这种策略，所有具有与位置匹配的 xpath 模式的元素都将被返回。如果没有元素具有匹配的元素属性，将引发 NoSuchElementException。

**Syntax –**

```py
driver.find_elements_by_xpath("xpath")

```

**示例–**
例如，考虑一下这个页面来源:

```py
<html>
 <body>
  <form id="loginForm">
   <input name="username" type="text" />
   <input name="password" type="password" />
   <input name="continue" type="submit" value="Login" />
  </form>
 </body>
<html>
```

现在，在您创建了驱动程序之后，您可以使用–

```py
login_form = driver.find_elements_by_xpath("/html/body/form[1]")
login_form = driver.find_elements_by_xpath("//form[1]")

```

要查看实际实现，请访问–[查找 _ 元素 _by_xpath()驱动程序方法–硒 Python](https://www.geeksforgeeks.org/find_elements_by_xpath-driver-method-selenium-python/?ref=rp)

#### 查找元素 by 链接文本

使用此策略，将返回所有链接文本值与位置匹配的元素。如果没有元素具有匹配的链接文本属性，将引发 NoSuchElementException。

**Syntax –**

```py
driver.find_elements_by_link_text("Text of Link")

```

**示例–**
例如，考虑一下这个页面来源:

```py
<html>
 <body>
  <p>Are you sure you want to do this?</p>
  <a href="continue.html">Continue</a>
  <a href="cancel.html">Cancel</a>
</body>
<html>
```

现在，在您创建了驱动程序之后，您可以使用–

```py
login_form = driver.find_elements_by_link_text('Continue')

```

要查看实际实现，请访问–[查找 _ 元素 _by_link_text()驱动程序方法–硒 Python](https://www.geeksforgeeks.org/find_elements_by_link_text-driver-method-selenium-python/?ref=rp)

#### 查找元素 by 部分链接文本

使用此策略，将返回部分链接文本值与位置匹配的所有元素。如果没有元素具有匹配的部分链接文本属性，将引发 NoSuchElementException。

**Syntax –**

```py
driver.find_elements_by_partial_link_text("Text of Link")

```

**示例–**
例如，考虑一下这个页面来源:

```py
<html>
 <body>
  <p>Are you sure you want to do this?</p>
  <a href="continue.html">Continue</a>
  <a href="cancel.html">Cancel</a>
</body>
<html>
```

现在，在您创建了驱动程序之后，您可以使用–

```py
login_form = driver.find_elements_by_partial_link_text('Conti')

```

要查看实际实现，请访问–[find _ elements _ by _ partial _ link _ text()驱动程序方法–Selenium Python](https://www.geeksforgeeks.org/find_elements_by_partial_link_text-driver-method-selenium-python/?ref=rp)

#### 按标签名查找元素

使用这种策略，将返回具有给定标记名的所有元素。如果没有元素具有匹配的标记名，将引发 NoSuchElementException。

**Syntax –**

```py
driver.find_elements_by_tag_name("Tag name")

```

**示例–**
例如，考虑一下这个页面来源:

```py
<html>
 <body>
  <h1>Welcome</h1>
  <p>Site content goes here.</p>
</body>
<html>
```

现在，在您创建了驱动程序之后，您可以使用–

```py
login_form = driver.find_elements_by_tag_name('h1')

```

要查看实际实现，请访问–[查找 _ 元素 _by_tag_name()驱动程序方法–硒 Python](https://www.geeksforgeeks.org/find_elements_by_tag_name-driver-method-selenium-python/?ref=rp)

#### 按类名查找元素

使用这种策略，将返回具有匹配类属性名的第一个元素。如果没有元素具有匹配的类属性名，将引发 NoSuchElementException。

**Syntax –**

```py
driver.find_elements_by_class_name("class_of_element")

```

**示例–**
例如，考虑一下这个页面来源:

```py
<html>
 <body>
  <p class="content">Site content goes here.</p>
</body>
<html>
```

现在，在您创建了驱动程序之后，您可以使用–

```py
content = driver.find_elements_by_class_name('content')

```

要查看实际实现，请访问–[查找 _elements_by_class_name()驱动程序方法–硒 Python](https://www.geeksforgeeks.org/find_elements_by_class_name-driver-method-selenium-python/?ref=rp)

#### find _ elements _ by _ css _ 选择器

使用这种策略，将返回所有具有匹配 CSS 选择器的元素。如果没有元素具有匹配的 CSS 选择器，将引发 NoSuchElementException。

**Syntax –**

```py
driver.find_elements_by_css_selector("CSS Selectors")

```

**示例–**
例如，考虑一下这个页面来源:

```py
<html>
 <body>
  <p class="content">Site content goes here.</p>
</body>
<html>
```

现在，在您创建了驱动程序之后，您可以使用–

```py
content = driver.find_elements_by_css_selector('p.content')

```

要查看实际实现，请访问–[find _ elements _ by _ CSS _ selector()驱动程序方法–Selenium Python](https://www.geeksforgeeks.org/find_elements_by_css_selector-driver-method-selenium-python/?ref=rp)