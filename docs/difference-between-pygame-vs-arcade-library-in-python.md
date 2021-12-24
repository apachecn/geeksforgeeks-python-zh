# Python 中 Pygame VS 街机库的区别

> 原文:[https://www . geesforgeks . org/pygame-vs-arcade-library-in-python/](https://www.geeksforgeeks.org/difference-between-pygame-vs-arcade-library-in-python/)

如今，游戏编程非常有益，它也可以用于广告或作为教学工具。游戏开发包括数学、逻辑、物理、人工智能等等，而且非常有趣。在 Python 中，到目前为止， [Pygame 库](https://www.geeksforgeeks.org/introduction-to-pygame/)也是如此，但是经过多次改进和处理 Pygame 拥有的问题后，一个新的模块[街机库](https://www.geeksforgeeks.org/arcade-library-in-python/)出现了。在这里，我们将讨论它们之间的差异，但首先，让我们了解它们到底是什么。

[**Pygame:**](https://www.geeksforgeeks.org/introduction-to-pygame/) 它是一个用于设计视频游戏的 Python 模块，通过允许计算机图形和声音库来开发高质量和用户交互的游戏。Pygame 是由皮特·辛纳斯开发的。直到 2000 年，它还是一个社区项目，后来，它在开源自由软件通用公共许可证下发布。Pygame 是可移植的，其代码兼容所有操作系统。也可以用它来创建开源、免费、免费软件、共享软件和商业游戏。Pygame 代码是用 C 语言编写的，该模块附带了 Windows 和 macOS 的安装程序。它也可以很容易地在手持设备上使用。即使在所有这些之后，该模块仍然缺少一些需要改进的功能，这将在本文后面的流程中讨论。

[**街机:**](https://www.geeksforgeeks.org/arcade-library-in-python/) 它也是一个 Python 模块，但只适用于 Python 3.6 及以上版本。它试图涵盖 Pygame 不支持的大多数功能。这也使用计算机图形和声音库，以开发高质量和用户互动游戏。街机是由保罗·文森特·克雷文开发的。街机需要 OpenGL 3.3+的支持。它建立在 OpenGL 和 Pyglet 之上，兼容 Windows、Linux 和 macOS X，还可以用它创建开源、免费、免费软件、共享软件和商业游戏。它还支持标准坐标系，非常易于使用和编码。

### 街机和游戏差异表

<figure class="table">

| 

拱廊

 | 

皮尤游戏

 |
| --- | --- |
| 街机是基于开放总帐的 | PyGame 很少更新，它是基于一个旧的 SDL 1 库 |
| 它具有 Python 3 的新特性，比如装饰器和类型提示 | Python 3 没有新特性 |
| 街机画固定精灵比 Pygame 快得多 | PyGame 绘制静止精灵的速度比 Arcade 慢得多 |
| 赋予旋转椭圆、圆弧和其他形状的自由 | 没有这样的自由 |
| 街机支持标准坐标系 | Pygame 不支持标准坐标系 |
| 支持动画精灵 | 不支持动画精灵 |
| 命令的应用编程接口文档更好 | API 文档没有那么详细。 |
| 命令名称是一致的，即使用追加()添加到子画面列表 | 命令不一致，它使用 add() |
| 比 Pygame 更少的锅炉板代码，也更容易编写和理解。 | 没有这样的设施 |
| 鼓励逻辑和显示代码的分离 | 倾向于将两者放入同一个游戏循环中。 |
| 运行在 OpenGL 3+和 Pyglet 之上 | 在旧的 SDL1 库上运行。 |
| 街机使用支持摇摄和音量的索洛。 | Pygame 使用旧的和不支持的 Avbin 库 |

</figure>