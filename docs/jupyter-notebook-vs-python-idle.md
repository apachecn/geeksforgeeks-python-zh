# Jupyter 笔记本 VS Python IDLE

> 原文:[https://www . geesforgeks . org/jupyter-notebook-vs-python-idle/](https://www.geeksforgeeks.org/jupyter-notebook-vs-python-idle/)

如果您不知道在哪个平台上开始编写 Python 代码，本文将对您有所帮助，因为 Python 为您提供了多种选择。我们比较了两种选择。

## Jupyter 笔记型电脑

[**Jupyter Notebook**](https://www.geeksforgeeks.org/how-to-use-jupyter-notebook-an-ultimate-guide/) 基本上就是一个 web 应用。与 IDEs(集成开发环境)不同，它使用互联网运行。即使在无法离线执行之后，由于其丰富的格式和用户友好的界面，它也是大多数初学者的首选。它允许我们在浏览器中输入代码，并自动突出显示语法。它帮助我们知道我们是否在颜色和粗体格式的帮助下正确地缩进代码。例如，如果我们在循环范围之外编写 print 命令，它将改变 print 关键字的颜色。空白在 Python 中起着非常重要的作用，因为 Python 不涉及使用大括号来封闭循环、方法等的主体。一个缩进错误就可能导致错误。结果以不同的表示形式显示，如 HTML、PNG、LaTeX、SVG、PDF 等。

**注:**更多信息请参考[如何使用 Jupyter 笔记本-终极指南](https://www.geeksforgeeks.org/how-to-use-jupyter-notebook-an-ultimate-guide/)

**优势:**

*   Rich media representation and text formatting;
*   No separate installation is required. It comes with Anaconda installation;
*   Because it is proficient in mathematics (drawing, drawing and complex equations), it is favored by data scientists.
*   Notebooks created in Jupyter can be accessed (edited) from any device using a web browser.
*   Comes with a debugger.
*   It will automatically save the changes made to the notebook when we encode.

**缺点:**

*   Servers and web browsers are needed, that is, they can't work offline like other IDEs, which is very difficult for people who don't have a stable Internet connection.
*   It takes more time to install than other ide;
*   We can only access from localhost by default. It requires us to follow some important security steps to access it from any other server.

**安装**:参考以下文章了解正确的安装指南–

*   [【中文】朱庇特笔记本电脑？](https://www.geeksforgeeks.org/how-to-install-jupyter-notebook-in-windows/)
*   [朱庇特笔记本电脑？](https://www.geeksforgeeks.org/how-to-install-jupyter-notebook-in-linux/?ref=rp)

## Python IDLE

**Python IDLE** 是用于 Python 编程的 ide 之一。当我们安装 Anaconda 时，它会自动下载。IDLE 代表  **综合开发学习环境。**

您可以通过打开命令提示符并键入 IDLE 来访问它。它会在打开 IDLE 后给它一个 Python shell，您可以在这里开始编码。Shell 是一个交互式解释器。它立即为每一行代码提供输出。按回车键不仅会改变线条，还会立即产生线条的结果。与 *Jupyter Notebook 不同，* IDLE 不允许我们先写完整的代码，再计算结果。但是，如果用户想在键入代码时检查每一行代码，他会更喜欢 Python IDLE，而不是 Jupyter Notebook。

所以基本上，这取决于用户。他可能想完成他的代码，然后运行它，或者在编写代码时同时检查每一行。但是如果你是那些想要一个视觉上有吸引力的应用程序来编码的人之一，你必须使用 Jupyter Notebook。

**优点:**

*   Very simple and basic;
*   Run without any server or browser;
*   Only Anaconda installation is required.
*   With built-in debugger;
*   Can be customized according to the user's preferences;

**缺点:**

*   A file created with Python IDLE cannot be accessed from a device other than the device that created it, unless it is copied or sent to another device.
*   Changes will not be automatically saved when we encode.
*   Not as advanced as the times.

**安装**:参考下面的文章了解正确的安装指南–

*   [Download and install the latest version of Python 3](https://www.geeksforgeeks.org/download-and-install-python-3-latest-version/)