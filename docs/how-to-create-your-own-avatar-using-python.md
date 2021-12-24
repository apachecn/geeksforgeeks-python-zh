# 如何用 Python 创建自己的头像？

> 原文:[https://www . geeksforgeeks . org/如何使用 python 创建自己的头像/](https://www.geeksforgeeks.org/how-to-create-your-own-avatar-using-python/)

在本文中，我们将讨论如何使用 Python 创建自定义头像。为了完成这项任务。你不需要自己在软件上创建或者从某个网站下载，但是几行代码就可以帮你生成一个自己选择的**头像**。

我们将使用 **py-avataaars** 包，从中我们将创建那些美丽的化身。本模块的基本语法是:

```
from py_avataaars import PyAvataaar

avatar = PyAvataaar()
avatar.render_png_file('<output_file.png>')
```

这里，PyAvataaar 类位于 *__init__。py* 负责很多功能，其中最主要的是设置头像的参数，例如:肤色、服装、眼睛、头发、发色、心情等的变化。

所以，让我们开始…

**第一步:**安装一些包。

*   首先在你的终端中输入 *pip 安装 py-avataaars* 来安装替身包(更多信息请查看:[https://github.com/kebu/py-avataaars](https://github.com/kebu/py-avataaars)
*   然后从这里[gtk3-runtime-3.24.24-2021-01-30-ts-win64.exe](gtk3-runtime-3.24.24-2021-01-30-ts-win64.exe)下载安装这个 gtk 文件。您的防病毒软件会试图阻止它，但您应该允许它下载以使代码正常运行，相信我伙计们这是一个无害的文件(有关更多信息，请查看:[https://github . com/tschoonj/GTK-for-Windows-Runtime-Environment-Installer](https://github.com/tschoonj/GTK-for-Windows-Runtime-Environment-Installer)

**第二步:**编写 python 程序。

*   首先，我们将尝试通过编写这段代码来生成默认头像，并看看这是否正常工作

## 蟒蛇 3

```
# importing the require package
from py_avataaars import PyAvataaar  

# assigning various parameters to our avatar
avatar = PyAvataaar()

# rendering the avatar in png format
avatar.render_png_file("AVATAR_1.png")
```

**输出:**

![](img/64ac07fec07f6e2203eec4b3b358fb90.png)

上面的程序会在保存这个 python 程序的文件夹中生成 *AVATAR_1.png* 文件。一旦上述程序正常运行，我们将使用 *PyAvataaar()* 方法根据我们的需求生成头像。

**语法:**

> PyAvataaar(样式、肤色、头发颜色、面部头发类型、上衣类型、嘴巴类型、眼睛类型、眉毛类型、鼻子类型、配饰类型、衣服类型、衣服图形类型)

**实施:**

## 蟒蛇 3

```
# Python program to create custom avatars

# importing the require package
import py_avataaars as pa  

# assigning various parameters to our avatar
avatar = pa.PyAvataaar(style=pa.AvatarStyle.CIRCLE,
                       skin_color=pa.SkinColor.LIGHT,
                       hair_color=pa.HairColor.AUBURN,
                       facial_hair_type=pa.FacialHairType.MOUSTACHE_MAGNUM,
                       top_type=pa.TopType.SHORT_HAIR_SHAGGY_MULLET,
                       mouth_type=pa.MouthType.SCREAM_OPEN,
                       eye_type=pa.EyesType.SQUINT,
                       eyebrow_type=pa.EyebrowType.RAISED_EXCITED_NATURAL,
                       nose_type=pa.NoseType.DEFAULT,
                       accessories_type=pa.AccessoriesType.PRESCRIPTION_02,
                       clothe_type=pa.ClotheType.HOODIE,
                       clothe_graphic_type=pa.ClotheGraphicType.BAT,)

# rendering the avatar in png format
avatar.render_png_file("AVATAR_2.png")
```

**输出:**

![](img/968c5eed014c9db5fb3823c0251a4012.png)

您可以通过按下 *Ctrl* 按钮并将鼠标悬停在 *py_avataaars* 线上来相应地更改头像的参数，这会将其变为蓝色，然后您可以单击它来查看 *__init__。py* 文件，在这里可以找到所有的参数，每个都写在不同的类中。

**演示:**

<video class="wp-video-shortcode" id="video-556461-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210210210640/2021-02-10-19-13-20.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20210210210640/2021-02-10-19-13-20.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210210210640/2021-02-10-19-13-20.mp4)</video>