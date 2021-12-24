# Python 模块的依赖树

> 原文:[https://www . geesforgeks . org/dependency-a-tree-of-a-python-module/](https://www.geeksforgeeks.org/dependency-tree-of-a-python-module/)

一般很多 Python 包都是依赖于其他包的，但是我们怎么知道**是依赖于哪个包的模块呢？**

## pip 冻结:

这是一个 python 内置模块，可以帮助我们了解依赖的包，但是它将所有依赖项显示为一个平面列表，找出哪些是顶级包，以及它们依赖哪些包需要一些努力。让我们看一个它如何工作的例子:

在命令提示符下键入以下命令:

```py
$pip freeze

```

**输出:**

```py
altair==4.1.0
attrs==19.3.0
docutils==0.15.2
entrypoints==0.3
Jinja2==2.11.2
jmespath==0.10.0
jsonschema==3.2.0
MarkupSafe==1.1.1
numpy==1.18.4
opencv-python==4.2.0.34
pandas==1.0.4
pyrsistent==0.16.0
python-dateutil==2.8.1
pytz==2020.1
six==1.15.0
toolz==0.10.0
urllib3==1.25.9

```

## **pipdeptree 实用程序:**

一种简单的方法是使用 **pipdeptree 实用程序。**pipdeptree 在命令行上工作，并以依赖树的形式显示已安装的 python 包。

这个模块没有内置 Python。要安装它，请在终端中键入以下命令。

```py
$pip install pipdeptree

```

这将安装 pipdeptree 的最新版本，至少需要 Python 2.7。

现在在命令提示符下运行这个命令，获取所有 Python 模块的依赖树。

**命令:**

```py
$pipdeptree

```

**输出:**

```py
$pipdeptree
altair==4.1.0
 - entrypoints [required: Any, installed: 0.3]
 - jinja2 [required: Any, installed: 2.11.2]
   - MarkupSafe [required: >=0.23, installed: 1.1.1]
 - jsonschema [required: Any, installed: 3.2.0]
   - attrs [required: >=17.4.0, installed: 19.3.0]
   - pyrsistent [required: >=0.14.0, installed: 0.16.0]
     - six [required: Any, installed: 1.15.0]
   - setuptools [required: Any, installed: 41.2.0]
   - six [required: >=1.11.0, installed: 1.15.0]
 - numpy [required: Any, installed: 1.18.4]
 - pandas [required: >=0.18, installed: 1.0.4]
   - numpy [required: >=1.13.3, installed: 1.18.4]
   - python-dateutil [required: >=2.6.1, installed: 2.8.1]
     - six [required: >=1.5, installed: 1.15.0]
   - pytz [required: >=2017.2, installed: 2020.1]
 - toolz [required: Any, installed: 0.10.0]
docutils==0.15.2
jmespath==0.10.0
opencv-python==4.2.0.34
 - numpy [required: >=1.17.3, installed: 1.18.4]
pipdeptree==1.0.0
 - pip [required: >=6.0.0, installed: 20.2.1]
urllib3==1.25.9

```

## 将 pipdeptree 和冻结相结合:

让我们看看当我们使用 pipdeptree 并完全冻结时会发生什么，

**命令:**

```py
$pipdeptree --freeze

```

**输出:**

```py
altair==4.1.0
  entrypoints==0.3
  Jinja2==2.11.2
    MarkupSafe==1.1.1
  jsonschema==3.2.0
    attrs==19.3.0
    pyrsistent==0.16.0
      six==1.15.0
    setuptools==41.2.0
    six==1.15.0
  numpy==1.18.4
  pandas==1.0.4
    numpy==1.18.4
    python-dateutil==2.8.1
      six==1.15.0
    pytz==2020.1
  toolz==0.10.0
docutils==0.15.2
jmespath==0.10.0
Mako==1.1.3
  MarkupSafe==1.1.1
opencv-python==4.2.0.34
  numpy==1.18.4
pipdeptree==1.0.0
  pip==20.2.1
scipy==1.5.2
  numpy==1.18.4
urllib3==1.25.9

```

因此，在这里我们看到，将 pipdeptree 与 freeze 一起使用，通过结合两个命令的属性来显示输出。所以看起来 pip freeze 的输出指示哪个包安装了另一个包，类似于 pipdeptree，但是这里使用缩进代替连字符(-)来指示树。

### pipdeptree 中的警告:

在执行 **pipdeptree** 命令时，通常会出现两种类型的警告，让我们逐一查看。

**1。冲突依赖:**顾名思义“冲突依赖”，它的相关性也是如此。有时有一些包被指定为具有不同版本的多个包的依赖项，在这种情况下，可能会出现冲突的依赖项警告。因此，任何被指定为具有不同版本的多个包的依赖项的包都被认为是可能冲突的依赖项。

默认情况下，pipdeptree 会警告可能的冲突依赖关系。

让我们再看一个 pipdeptree 的例子:

**命令:**

```py
$pipdeptree

```

**输出:**

```py
Warning!!! Possibly conflicting dependencies found:
* impacket==0.9.20
 - ldap3 [required: ==2.5.1, installed: ?]
 - ldapdomaindump [required: >=0.9.0, installed: ?]
------------------------------------------------------------------------
alembic==1.0.11.dev0
attrs==18.2.0
dulwich==0.20.2
  - certifi [required: Any, installed: 2018.11.29]
  - urllib3 [required: >=1.24.1, installed: 1.24.1]
EditorConfig==0.12.1
Flask-Cors==3.0.8
  - Flask [required: >=0.9, installed: 1.1.1]
  - Six [required: Any, installed: 1.13.0]
Flask-Session==0.3.1
Flask-SocketIO==4.2.1
  - Flask [required: >=0.9, installed: 1.1.1]
  - python-socketio [required: >=4.3.0, installed: 4.5.1]
    - python-engineio [required: >=3.9.0, installed: 3.12.1]
      - six [required: >=1.9.0, installed: 1.13.0]
    - six [required: >=1.9.0, installed: 1.13.0]
google==2.0.1
  - beautifulsoup4 [required: Any, installed: 4.8.0]
html2text==2019.8.11
impacket==0.9.20
  - ldap3 [required: ==2.5.1, installed: ?]
  - ldapdomaindump [required: >=0.9.0, installed: ?]
ipython==5.8.0
  - backports.shutil-get-terminal-size [required: Any, installed: 1.0.0]
  - pathlib2 [required: Any, installed: 2.3.5]
    - scandir [required: Any, installed: 1.10.0]
  - pexpect [required: Any, installed: 4.6.0]

```

pip [还没有真正的依赖解析。](https://github.com/pypa/pip/issues/988)警告打印到标准错误，而不是标准输出。要完全消除此警告，请使用 **-w** 静音或**–warn**静音标志。也可以使用**–warn fail**将其设为严格模式，在这种情况下，该命令不仅会将警告打印到 stderr，还会以非零状态代码退出。如果您希望将此工具安装到您的配置项管道中，这可能会很有用。

**注意:**0 . 6 . 0 版本增加了**–警告标志**。对于旧版本，使用**–不学习标志。**

**2。循环依赖:**当两个包相互依赖时，就会出现这种依赖。假设，A 包依赖 B 包，B 包依赖 A 包。

为此，让我们再看一个例子:

**命令:**

```py
$pipdeptree

```

**输出:**

```py
Warning!!! Cyclic dependencies found:
- CircularDependencyA => CircularDependencyB => CircularDependencyA
- CircularDependencyB => CircularDependencyA => CircularDependencyB
------------------------------------------------------------------------
wsgiref==0.1.2
argparse==1.2.1

```

**注意:**它们也被打印到 stderr，并且可以使用**–warn 标志进行控制。**

### 要查找安装特定软件包的原因:

现在，我们有时可能想知道为什么要安装特定的软件包。那么我们可以使用–reverse(或简称-r)标志。要了解所有软件包需要什么特定软件包，可以将其与**–软件包**结合使用

标志如下例所示:

**命令**:

```py
$pipdeptree --reverse --packages MarkupSafe,numpy

```

**输出:**

```py
MarkupSafe==1.1.1
  - Jinja2==2.11.2 [requires: MarkupSafe>=0.23]
    - altair==4.1.0 [requires: jinja2]
  - Mako==1.1.3 [requires: MarkupSafe>=0.9.2]
numpy==1.18.4
  - altair==4.1.0 [requires: numpy]
  - opencv-python==4.2.0.34 [requires: numpy>=1.17.3]
  - pandas==1.0.4 [requires: numpy>=1.13.3]
    - altair==4.1.0 [requires: pandas>=0.18]
  - scipy==1.5.2 [requires: numpy>=1.14.5]

```

### 使用 pipdeptree 编写 requirements.txt 文件:

如果您希望只跟踪您的 **requirements.txt** 文件中的顶层包，那么可以使用 pipdeptree 从输出中只对顶层行进行 grep，

**命令:**

```py
$pipdeptree | grep -P '^\w+'

```

**输出:**

```py
Lookupy==0.1
wsgiref==0.1.2
argparse==1.2.1
psycopg2==2.5.2
Flask-Script==0.6.6
alembic==0.6.2
ipython==2.0.0
slugify==0.0.1
redis==2.9.1

```

但是这里有一个问题。输出中没有提到**lookup****作为可编辑包安装(参考上面 pip freeze 的输出)，其来源信息丢失。要解决此问题，必须使用 **-f** 或**-冻结标志**运行管道树**

****命令:****

```py
$pipdeptree -f --warn silence | grep -P '^[\w0-9\-=.]+' 
```

****输出:****

```py
-e git+git@github.com:naiquevin/lookupy.git@cdbe30c160e1c29802df75e145ea4ad903c05386#egg=Lookupy-master
wsgiref==0.1.2
argparse==1.2.1
psycopg2==2.5.2
Flask-Script==0.6.6
alembic==0.6.2
ipython==2.0.0
slugify==0.0.1
redis==2.9.1 
```

****命令:****

```py
$ pipdeptree -f --warn silence | grep -P '^[\w0-9\-=.]+' > requirements.txt 
```

****冻结标志**也不会输出子依赖项的连字符，因此您可以将 **pipdeptree -f** 的完整输出转储到 **requirements.txt** 文件，使文件对人类友好(由于缩进)也对 pip 友好。(不过要注意重复的依赖关系)**

### **使用带外部工具的管道树:**

**pipdeptree 使用 flag–json 以 JSON 表示形式显示输出，如下所示:**

****命令:****

```py
$pipdeptree --json 
```

****输出:****

```py
[
    {
        "package": {
            "key": "werkzeug",
            "package_name": "Werkzeug",
            "installed_version": "1.0.1"
        },
        "dependencies": []
    },
    {
        "package": {
            "key": "urllib3",
            "package_name": "urllib3",
            "installed_version": "1.25.9"
        },
        "dependencies": []
    },

    {
        "package": {
            "key": "pytz",
            "package_name": "pytz",
            "installed_version": "2020.1"
        },
        "dependencies": []
    },
    {
        "package": {
            "key": "python-dateutil",
            "package_name": "python-dateutil",
            "installed_version": "2.8.1"
        },
        "dependencies": [
            {
                "key": "six",
                "package_name": "six",
                "installed_version": "1.15.0",
                "required_version": ">=1.5"
            }
        ]
    },
    {
        "package": {
            "key": "pyrsistent",
            "package_name": "pyrsistent",
            "installed_version": "0.16.0"
        },
        "dependencies": [
            {
                "key": "six",
                "package_name": "six",
                "installed_version": "1.15.0",
                "required_version": null
            }
        ]
    },
    {
        "package": {
            "key": "pipdeptree",
            "package_name": "pipdeptree",
            "installed_version": "1.0.0"
        },
        "dependencies": [
            {
                "key": "pip",
                "package_name": "pip",
                "installed_version": "20.2.1",
                "required_version": ">=6.0.0"
            }
        ]
    },

] 
```

****注意:****–JSON**将输出一个包含所有包及其直接依赖项的平面列表。要获取嵌套 JSON，请使用–**-JSON-tree**(在 0.11.0 版本中添加)。**

****命令:****

```py
$pipdeptree --json-tree 
```

****输出:****

```py
 [
    {
        "key": "altair",
        "package_name": "altair",
        "installed_version": "4.1.0",
        "required_version": "4.1.0",
        "dependencies": [
            {
                "key": "entrypoints",
                "package_name": "entrypoints",
                "installed_version": "0.3",
                "required_version": "Any",
                "dependencies": []
            },
            {
                "key": "jinja2",
                "package_name": "jinja2",
                "installed_version": "2.11.2",
                "required_version": "Any",
                "dependencies": [
                    {
                        "key": "markupsafe",
                        "package_name": "MarkupSafe",
                        "installed_version": "1.1.1",
                        "required_version": ">=0.23",
                        "dependencies": []
                    }
                ]
            },

    {
        "key": "urllib3",
        "package_name": "urllib3",
        "installed_version": "1.25.9",
        "required_version": "1.25.9",
        "dependencies": []
    }
] 
```