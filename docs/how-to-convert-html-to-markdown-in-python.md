# 如何在 Python 中将 HTML 转换为 Markdown？

> 原文:[https://www . geesforgeks . org/如何用 python 将 html 转换为 markdown/](https://www.geeksforgeeks.org/how-to-convert-html-to-markdown-in-python/)

减价是在网上写格式化文本的一种方式。本文讨论了如何将一个 HTML 文本转换成 Markdown。我们可以使用 **markdownify 包**轻松将 HTML 转换为 markdown。因此，让我们看看如何下载 markdownify 包，并将我们的 HTML 转换为 python 中的 markdownify。

### **安装:**

这个模块没有内置 Python。要安装它，请在终端中键入以下命令。

```
pip install markdownify
```

### 方法

*   导入模块
*   创建 HTML 文本
*   使用 markdownify()函数并将文本传递给它
*   显示标记的文本

**例 1:**

## 蟒蛇 3

```
# import markdownify
import markdownify

# create html
html = """  
         <h1> <strong>Geeks</strong>
         for<br>
         Geeks
         </h1>
        """

# print HTML
print(html)

# convert html to markdown
h = markdownify.markdownify(html, heading_style="ATX")

print(h)
```

**输出:**

```
         <h1> <strong>Geeks</strong>
        for<br>
        Geeks
        </h1>

#  **Geeks**
for
Geeks
```

**例 2:**

## 计算机编程语言

```
# import markdownify
import markdownify

# create html
html = """  <h1>Fruits</h1>
         <ul>
             <li>  apple  </li>
             <li>  banana </li>
             <li>  orange </li>
        </ul>

        """

# print HTML
print(html)

# convert html to markdown
h = markdownify.markdownify(html, heading_style="ATX")

# print markdown
print(h)
```

**输出:**

```
<h1>Fruits</h1>
         <ul>
             <li>  apple  </li>
             <li>  banana </li>
             <li>  orange </li>
        </ul>

 # Fruits
*  apple 
*  banana 
*  orange 
```