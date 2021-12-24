# 使用 JSON 进行两个程序之间的通信

> 原文:[https://www . geesforgeks . org/communication-two-programs-use-JSON/](https://www.geeksforgeeks.org/communication-between-two-programs-using-json/)

JSON 代表 JavaScript 对象符号。为了在计算机和人类之间进行交流，我们使用了一种编程语言。为了在两个程序之间进行通信，必须有一种通用的数据格式，这里我们使用 JSON 格式。假设您有一个应用程序，前端用 Python 编写，后端用 Java 编写。现在你需要在这两种语言之间交流来做一些事情。(例如，测验网站将在前端接受您的输入，并将数据发送到后端以计算结果，并将结果返回给前端)。

所以这里我们使用 JSON 在两个叫做 Python 和 Java 的程序之间进行通信。我们可以使用一种通用的文本格式进行交流，但是文本格式会包含很多复杂性。然而，JSON 是轻量级的，易于使用。JSON 是独立于语言的，因此可以被任何编程语言使用。

**序列化:**

序列化是将编程数据转换为 JSON 文本的过程。例如，在 python 中，我们可以使用作为 python 对象的字典来转换为 JSON 文本。将 python 对象转换为 JSON 文本的过程称为序列化。

**反序列化:**

反序列化是序列化的逆过程。它是将 JSON 文本转换为编程数据的过程。在 Python 中，我们可以将一个 JSON 文本转换成一个名为[字典 Python](https://www.geeksforgeeks.org/python-dictionary/) 的 Python 对象。

**将两个变量从 Python 转移到 Java:**

为了在两个程序之间进行通信，我们需要使用一种语言序列化数据，并使用其他语言反序列化数据。这里我们用 Python 序列化数据，用 Java 反序列化数据。因此，我们将数据从 Python 传输到 Java。在这里，让我们将两个变量‘a’和‘b’从 Python 转移到 Java，并用 Java 计算结果。

**使用 Python 的序列化:**

让我们使用 python 代码生成一个 JSON 文件，如下所示。

## 巨蟒

```
# Import JSON 
import json

# using MAP
data = {"a" : 1, "b" : 2.3}
with open("JSONData.json", "w") as file:
    json.dump(data, file)
# JSONData.json file will be created
```