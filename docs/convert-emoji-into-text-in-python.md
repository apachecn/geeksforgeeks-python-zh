# 将表情符号转换为 Python 中的文本

> 原文:[https://www . geesforgeks . org/convert-emoji-to-text-in-python/](https://www.geeksforgeeks.org/convert-emoji-into-text-in-python/)

使用 **demoji 模块**可以将 Python 中的表情符号或表情符号转换为文本。它用于准确地移除和替换文本字符串中的表情符号。要安装 demoji 模块，可以使用以下命令:

```
pip install demoji
```

由于表情列表本身经常更新和更改，演示模块还需要从 Unicode 联盟的[表情代码存储库](http://unicode.org/Public/emoji/12.0/emoji-test.txt)中初始下载数据。上述下载应使用以下代码块:

## 蟒蛇 3

```
import demoji

demoji.download_codes()
```

**输出:**

![](img/4121d554390b17c108f3aea60c2c92da.png)

现在我们都准备好使用 demoji 模块了，我们可以跳到几个例子。
**例 1:**

![](img/c3154a6d6a9977c7cd730a45aa66d6bb.png)

**输出:**

![](img/dc935ede520c5f92cba5af5be9f2f05a.png)

**例 2:**

![](img/3193f22b199a371043de5f9b242387b1.png)

**输出:**

![](img/ff093b7678bd4bcb5ff15750f086fed3.png)

**例 3:**

![](img/8506549ca49f5291683fbbf433c1ddf6.png)

**输出:**

![](img/049979e85444d0381117220e53c5bde9.png)

**例 4:**

![](img/4582abf3d976b82236a156263975f31c.png)

**输出:**

![](img/d815a0c4328186ebd41cece59eb5aed3.png)