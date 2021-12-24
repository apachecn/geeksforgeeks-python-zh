# Python 中如何使用 CherryPy 进行乘法运算？

> 原文:[https://www . geeksforgeeks . org/如何使用 python 中的 cherrypy 执行乘法/](https://www.geeksforgeeks.org/how-to-perform-multiplication-using-cherrypy-in-python/)

CherryPy 也称为 web 应用程序库，是一个 Python web 框架，为 Python 开发人员提供了一个友好的 HTTP 协议接口。它允许开发人员以与传统的面向对象 Python 程序相同的方式构建网络应用程序。因此，导致更小的源代码开发没有时间。

该框架主要面向希望使用 Python 创建可移植的数据库驱动的 web 应用程序的开发人员，因为它提供了创建、检索、更新和删除功能。

安装奇瑞的基本要求包括:

*   python 2.4 或更高版本
*   Cherrypy 3.0

要安装 cherrypy，请在终端中运行以下命令:

```
pip install cherrypy
```

**进场:**

*   创建一个用户界面来接受用户的输入。
*   编写 cherrypy 程序来执行所需的操作

创建用户界面以接受用户输入的 HTML 代码:

## 超文本标记语言

```
<html>

<body> 

  <div class="container">   
    <h2><u><i>Operation</i></u></h2> 
    <form action="store" id="form" method="GET"> 
    <input type="number" name="number1" /><br /> 
    <input type="number" name="number2" /><br /> 

    <input style="margin-left: 250px;" id=" submit" type="submit"/></div> 
  </div>     
    </form> 
  </div> 

</body> 
</html>
```

**用于乘法的奇瑞码**

## 蟒蛇 3

```
import cherrypy

class Root(object):

    @cherrypy.expose
    def index(self):
        return """<html> 
<head> 

</head> 
<body> 

<div class="container"> 
    <h2><u><i>Multiplication</i></u></h2> 
    <form action="store" id="form" method="GET"> 
    <input type="number" name="num1" /><br /> 
    <input type="number" name="num2" /><br /> 

    <input style="margin-left: 250px;" id=" submit" type="submit"/></div> 
</div>
    </form> 
</div> 

</body> 
</html>"""

    @cherrypy.expose
    def store(self, num1, num2):

        mul1 = int(num1)
        mul2 = int(num2)

        result = mul1*mul2

        out = """<html> 
        <body> 

<p> Sum: %s</p>

        <a style="color:red; font-size:35px;" id="shutdown"; href="./shutdown"><i>Shutdown Server</i></a> 
        </body> 
        </html> 

        """

        return out % (result)

    @cherrypy.expose
    def shutdown(self):
        cherrypy.engine.exit()

if __name__ == "__main__":
    cherrypy.config.update({'server.socket_port': 8087})

    cherrypy.quickstart(Root())
```

**输出:**

![](img/d0bba618fcad84931edacd964003b4d9.png) ![](img/1445409f2dc3dd303220c94c63972616.png)