# 硒蟒中的元素方法

> 原文:[https://www . geesforgeks . org/element-methods-in-selenium-python/](https://www.geeksforgeeks.org/element-methods-in-selenium-python/)

Selenium 的 Python 模块是为使用 Python 执行自动化测试而构建的。Python 中的硒与元素一起工作。元素可以是标签、属性或任何东西，它是`class selenium.webdriver.remote.webelement.WebElement`的一个实例。使用硒在屏幕上找到一个元素后，您可能想点击它或找到子元素等。硒元素提供了围绕这个硒元素的方法。在本文中，我们讨论了可以使用 Selenium 及其 WebElement 执行多个任务的各种方法。

## 如何在 Selenium Python 中对一个元素使用方法？

要在 WebElement 上使用一个方法，首先我们需要在网页中找到它。在 Selenium Python 中，如何定位一个元素有多种方法。结账–[定位器策略–硒蟒](https://www.geeksforgeeks.org/locator-strategies-selenium-python/)。抓取元素后，可以根据以下语法使用方法–
**语法–**

```
element.method_name
```

**示例–**

```
<input type="text" name="passwd" id="passwd-id" />
```

要找到一个元素，需要使用一种定位策略，例如，

```
element = driver.find_element_by_id("passwd-id")
element = driver.find_element_by_name("passwd")
element = driver.find_element_by_xpath("//input[@id='passwd-id']")
```

此外，要找到多个元素，我们可以使用–

```
elements = driver.find_elements_by_name("passwd")
```

现在人们可以使用任何方法，如–

```
element.method_name
```

## 硒蟒中的元素方法

| 元素方法 | 描述 |
| --- | --- |
| [为 _selected()](https://geeksforgeeks.org/is_selected-element-method-selenium-python/) | is_selected 方法用于检查元素是否被选中。它返回一个布尔值“真”或“假”。 |
| [为 _displayed()](https://geeksforgeeks.org/is_displayed-element-method-selenium-python/) | is _ displayed 方法用于检查元素对用户是否可见。它返回一个布尔值“真”或“假”。 |
| [is_enabled()](https://geeksforgeeks.org/is_enabled-element-method-selenium-python/) | is_enabled 方法用于检查元素是否已启用。它返回一个布尔值“真”或“假”。 |
| [get_property()](https://geeksforgeeks.org/get_property-element-method-selenium-python/) | get_property 方法用于获取元素的属性，比如获取锚点标签的 text_length 属性。 |
| [get_attribute()](https://geeksforgeeks.org/get_attribute-element-method-selenium-python/) | get_attribute 方法用于获取元素的属性，比如获取锚点标签的 href 属性。 |
| [send_keys()](https://geeksforgeeks.org/send_keys-element-method-selenium-python/) | send_keys 方法用于将文本发送到任何字段，例如表单的输入字段，甚至锚定标签段落等。 |
| [点击()](https://geeksforgeeks.org/click-element-method-selenium-python/) | click 方法用于单击任何元素，如锚点标签、链接等。 |
| [晴()](https://geeksforgeeks.org/clear-element-method-selenium-python/) | clear 方法用于清除任何字段的文本，例如表单的输入字段，甚至锚定标签段落等。 |
| [屏幕截图()](https://geeksforgeeks.org/screenshot-element-method-selenium-python/) | 截图方法用于将当前元素的截图保存到 PNG 文件中。 |
| [提交()](https://geeksforgeeks.org/submit-element-method-selenium-python/) | submit 方法用于在向表单发送数据后提交表单。 |
| [value_of_css_property()](https://geeksforgeeks.org/value_of_css_property-element-method-selenium-python/) | value_of_css_property 方法用于获取元素的 css 属性值。 |
| [位置](https://geeksforgeeks.org/location-element-method-selenium-python/) | location 方法用于获取元素在可渲染画布中的位置。 |
| [萤幕撷取画面 _as_png](https://geeksforgeeks.org/screenshot_as_png-element-method-selenium-python/) | 截图 _as_png 方法用于获取当前元素的截图作为二进制数据。 |
| [父代](https://geeksforgeeks.org/parent-element-method-selenium-python/) | 父方法用于获取对从中找到此元素的 WebDriver 实例的内部引用。 |
| [尺寸](https://geeksforgeeks.org/size-element-method-selenium-python/) | size 方法用于获取当前元素的大小。 |
| [标签 _ 名称](https://geeksforgeeks.org/tag_name-element-method-selenium-python/) | tag_name 方法用于获取您所引用的标签的名称。 |
| [文字](https://geeksforgeeks.org/text-element-method-selenium-python/) | text 方法用于获取当前元素的文本。 |
| [直肠](https://geeksforgeeks.org/rect-element-method-selenium-python/) | rect 方法用于获取具有元素大小和位置的字典。 |
| [截图 _as_base64](https://geeksforgeeks.org/screenshot_as_base64-element-method-selenium-python/) | scratch _ as _ base64 方法用于以 base64 编码字符串的形式获取当前元素的屏幕截图。 |