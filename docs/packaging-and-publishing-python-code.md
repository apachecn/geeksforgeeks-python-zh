# 打包发布 Python 代码

> 原文:[https://www . geesforgeks . org/packing-and-publishing-python-code/](https://www.geeksforgeeks.org/packaging-and-publishing-python-code/)

如果你已经用 python 编码了，甚至有一段时间了，你现在一定已经熟悉了‘pip’的概念。它是一个包管理系统，用于安装和管理用 Python 编写的软件包/库。
那么有人可能会问，这些包/库都存放在哪里？很明显，必须有一个大的“在线存储库”来存储所有这些代码。而这个问题的答案就是 [Python 包索引](https://pypi.python.org/pypi "Python Package Index") (PyPI)。

PyPI 是 Python 的官方第三方软件存储库。在写这篇文章的时候，PyPI 已经在托管 95971 个包了！
pip 使用 PyPI 作为包及其依赖项的默认来源。所以无论何时你输入:

```
 pip install package_name
```

pip 将在 PyPI 上查找该包，如果找到，它将在您本地系统上下载并安装该包。

在本文中，我将演示如何在 PyPI 上发布您自己的 python 包，以便它可以单行安装，并且可以方便地让所有其他 Python 用户在线使用！我将以一个示例包为例，向您展示整个过程。示例包托管在 [Github](https://github.com/nikhilkumarsingh/mygmap) 上。

**第一步:准备好 python 脚本**

当然，第一步是准备好您的 python 程序(您想在 PyPI 上发布它)！

它可以是任何 python 脚本。这里我使用我自己的 python 脚本，我已经命名为“ **locator.py** ”(我使用这个名字只是为了参考。请随意以任何名称保存您的 python 脚本。)此文件可在[这里](https://github.com/nikhilkumarsingh/mygmap/blob/master/geo/locator.py)获得。

**第二步:准备好包目录结构**

这是最重要的一步。现在，我们必须遵循包目录的一些预定义结构。
作为参考，请随意查看本教程中使用的示例项目的 Github 存储库。您可以克隆这个存储库，并进行一些修改来创建您自己的包。

目录结构必须是这样的:
![Getting the package-directory structure ready](img/52346c0b0f28a0a3416427a6607f07aa.png)

好的，让我们讨论一下这些文件将包含什么。

*   **setup.py :** 是最重要的文件。它是配置项目各个方面的文件。setup.py 的主要特点是它包含一个全局 setup()函数。此函数的关键字参数是如何定义项目的具体细节。
    您需要使用 pip 安装这个 [setuptools](https://pypi.python.org/pypi/setuptools) 库:

```
pip install setuptools
```

以下是我的**设置。py** 的样子:

```
from setuptools import setup

# reading long description from file
with open('DESCRIPTION.txt') as file:
    long_description = file.read()

# specify requirements of your package here
REQUIREMENTS = ['requests']

# some more details
CLASSIFIERS = [
    'Development Status :: 4 - Beta',
    'Intended Audience :: Developers',
    'Topic :: Internet',
    'License :: OSI Approved :: MIT License',
    'Programming Language :: Python',
    'Programming Language :: Python :: 2',
    'Programming Language :: Python :: 2.6',
    'Programming Language :: Python :: 2.7',
    'Programming Language :: Python :: 3',
    'Programming Language :: Python :: 3.3',
    'Programming Language :: Python :: 3.4',
    'Programming Language :: Python :: 3.5',
    ]

# calling the setup function 
setup(name='mygmap',
      version='1.0.0',
      description='A small wrapper around google maps api',
      long_description=long_description,
      url='https://github.com/nikhilkumarsingh/mygmap',
      author='Nikhil Kumar Singh',
      author_email='nikhilksingh97@gmail.com',
      license='MIT',
      packages=['geo'],
      classifiers=CLASSIFIERS,
      install_requires=REQUIREMENTS,
      keywords='maps location address'
      )
```

让我们看看 setup 函数的不同参数有什么作用:

1.  **名称**:是你项目的名称。您的包将在 PyPI 上以此名称列出。
2.  **版本**:可以指定项目当前版本的字符串。
    你想怎么设置系列版本的方案完全是你自己的选择(你可以用‘1.0’或者‘0.1’甚至‘0 . 0 . 1’)。
    如果你发布你的项目，这个版本会在每个版本的 PyPI 上显示。每次你上传一个新版本，你也必须改变这个论点。
3.  **描述:**关于包裹的简短描述。您可以使用 long_description 参数来编写长描述。
4.  **long_description:** 我们可以使用富文本来更好地描述我们的文件。默认文件格式为[重组文本](https://en.wikipedia.org/wiki/ReStructuredText)。你可以看看 [DESCRIPTION.txt](https://github.com/nikhilkumarsingh/mygmap/blob/master/DESCRIPTION.txt) 来感受一下语法。
5.  **网址:**你项目的主页网址。这使得人们更容易关注或参与你的项目。
6.  **作者，作者 _ 邮箱:**关于作者的详细信息
7.  **许可证:**指定您正在使用的许可证类型。
8.  **分类器:**这是一个字符串列表，我们可以在其中指定关于我们项目的更多细节，比如它的开发状态、主题、许可证以及您项目支持的 python 版本。在这里可以看到更多的量词[。](https://pypi.python.org/pypi?%3Aaction=list_classifiers)
9.  **install_requires:** 可以用来指定你的包需要运行哪些第三方库。当有人安装您的软件包时，这些依赖项将由 pip 安装。
10.  **关键词:**列出描述你的项目的关键词。

*   **DESCRIPTION.txt** :这个文件包含了要在 PyPI 页面显示的关于我们包的长描述。我们在这里使用重组文本文件格式。在这里查看我们套餐[中使用的文件。](https://github.com/nikhilkumarsingh/mygmap/blob/master/DESCRIPTION.txt)*   **LICENSE.txt** :为项目的使用设置一个许可证是一个很好的做法。您可以使用任何免费提供的模板。最常用的是**麻省理工**执照。
    我正在使用的这个项目的许可证可以在这里获得。(在项目中使用本许可证时，您可以替换作者的姓名)*   **README.md** :这个文件和我们的 PyPI 包没有任何关系。它包含要在 Github 页面上显示的描述。您也可以将它用于 PyPI 页面，但是它需要对我们的代码进行更多的修改。现在，让我们保持简单。*   **__init__.py**: The primary use of __init__.py is to initialize a python package.
    The inclusion of this file in a directory indicates to the Python interpreter that the directory should be treated like a Python package.
    You can leave this file empty.

    **第三步:创建你的账户** 现在，是时候在 [PyPI](https://pypi.python.org/pypi?%3Aaction=register_form) 和[上创建账户了，测试一下 PyPI](https://testpypi.python.org/pypi?%3Aaction=register_form) 。Test PyPI 只是一个测试站点，我们会先上传我们的代码，看看是否一切正常。

    建立账户后，创建这个**。pypirc** 文件在你系统的主目录中，输入账号详细信息。

    ```
    [distutils]
    index-servers =
      pypi
      pypitest

    [pypi]
    repository=https://pypi.python.org/pypi
    username= your_username
    password= your_password

    [pypitest]
    repository=https://testpypi.python.org/pypi
    username= your_username
    password= your_password
    ```

    注意*:如果你在 windows 系统上，只需在命令提示符下输入 **echo %USERPROFILE%** 即可知道你电脑的主目录。放下**。**文件在那里。*

    **第四步:** **上传包**

    最后，我们准备在 PyPI 上上传我们的包！

    *   First of all, we will check if our package installs correctly on Test PyPI.
        Open command prompt/terminal in the root directory of your package.
        Run this in terminal:

        ```
        python setup.py register -r pypitest
        ```

        这将尝试在 PyPI 的测试服务器上注册您的包，只是为了确保您已经正确设置了一切。

        现在，运行这个:

        ```
        python setup.py sdist upload -r pypitest
        ```

        您应该没有错误，并且现在应该能够在[测试 PyPI 存储库](https://testpypi.python.org/pypi)中看到您的库。

    *   Once you’ve successfully uploaded to PyPI Test, perform the same steps but point to the live PyPI server instead.
        To register on PyPI, run:

        ```
        python setup.py register -r pypi
        ```

        然后，运行:

        ```
        python setup.py sdist upload -r pypi
        ```

你们都完了！您的软件包现在可以在 PyPI 上公开获得，并且可以通过简单的 pip 命令轻松安装！
我们使用本教程创建的包在这里提供[。](https://pypi.python.org/pypi/mygmap/1.0.3)

只需在终端上输入，

```
 pip install your_package_name
```

检查安装过程是否成功完成。
 **参考文献:**

*   [http://peterdowns.com/posts/first-time-with-pypi.html](http://peterdowns.com/posts/first-time-with-pypi.html)
*   [https://packaging.python.org/distributing/](https://packaging.python.org/distributing/)

本文由**尼克尔·库马尔**供稿。如果你喜欢极客博客并想投稿，你也可以用 contribute.geeksforgeeks.org 写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。