# Python 街机–添加关卡

> 原文:[https://www.geeksforgeeks.org/python-arcade-adding-levels/](https://www.geeksforgeeks.org/python-arcade-adding-levels/)

在本文中，我们将学习如何用 Python 为我们的街机游戏添加不同的关卡。

## 添加级别

我们可以通过以下步骤轻松地为街机游戏添加多个关卡:

*   创建一个新变量来存储当前级别。

```
self.level = 1
```

*   在 self.level 变量的帮助下，加载你将在当前级别使用的精灵。在本例中，我们将为级别 1 加载名为“平台 1”的精灵，为级别 2 加载名为“平台 2”的精灵，以此类推。为此，我们可以使用下面的代码加载平台。

```
platform = arcade.Sprite(f"Platform{self.level}.png", 1)
```

*   如果玩家穿过屏幕的右侧，那么我们将增加 self.level 变量的值以进入下一个级别。

```
 if self.player_sprite.center_x>690:
    self.level += 1
```

## 使用的功能:

*   **Camera():**Camera 类用于控制可见视口。

> **语法:**街机。摄像机(宽度、高度、窗口)
> 
> **参数:**
> 
> *   **宽度:**视口的宽度
> *   **高度:**视口高度
> *   **窗口:**与此摄像机关联的窗口

*   **场景():**表示场景对象的类。

> **语法:**街机。场景(精灵列表，名称映射)
> 
> **参数:**
> 
> *   **sprite _ list:**sprite list 对象的列表
> *   **名称映射:**sprite list 对象的字典

*   **物理引擎平台转换器():**在平台转换器中使用的简单物理引擎。

> **语法:**街机。物理引擎平台变形器(玩家精灵、平台、重力、梯子)
> 
> **参数:**
> 
> *   **玩家 _ 精灵:**玩家的精灵
> *   **平台:**它无法通过的精灵
> *   **重力:**每帧向下加速度
> *   **梯子:**用户可以攀爬的梯子

### 使用的精灵:

![](img/03c0d8cbdf7dc6cdb949908ac0fb4c79.png) ![](img/8f85ce6b46f985ab79baa63ba513f0e4.png) ![](img/2bd0d0eff56a6973e57178e5be265632.png)

在下面的例子中，我们将创建一个 MainGame()类。在这个类里面，首先我们要初始化一些速度、相机、等级和玩家精灵的变量，然后我们将在这个类里面创建 6 个函数。

*   **on_draw():** 在这个功能里面，我们将使用我们的相机，绘制场景。
*   **setup():** 在这个功能中，我们将初始化我们的相机和场景对象，然后我们将加载我们的播放器和平台的精灵。之后，我们将调用 PhysicsEnginePlatformer()函数。
*   **on_update():** 在这个功能中，我们将更新玩家的精灵、相机和物理引擎的 x 坐标。我们也将改变我们在这个函数中的级别。
*   **on_key_press()和 on_key_release():** 在此功能中，我们将根据按下或释放的键盘键来更改速度变量的值。
*   **camera_move():** 在这个功能中，我们会根据我们玩家的当前位置来移动我们的相机。

**下面是实现:**

## 蟒蛇 3

```
# Importing arcade module
import arcade

# Creating MainGame class
class MainGame(arcade.Window):
    def __init__(self):
        super().__init__(600, 600,
                         title = "Player Movement")

        # Initializing a variable to store
        # the velocity of the player
        self.vel_x = 0

        # Creating variable for Camera
        self.camera = None

        # Creating variable to store current level
        self.level = 1

        # Creating scene object
        self.scene = None

        # Creating variable to store player sprite
        self.player = None

        # Creating variable for our game engine
        self.physics_engine = None

    # Creating on_draw() function to draw on the screen
    def on_draw(self):
        arcade.start_render()

        # Using the camera
        self.camera.use()

        # Drawing our scene
        self.scene.draw()

    def setup(self):
         # Initialize Scene object
        self.scene = arcade.Scene()

        # Using Camera() function
        self.camera = arcade.Camera(600, 600)

        # Creating different sprite lists
        self.scene.add_sprite_list("Player")
        self.scene.add_sprite_list("Platforms",
                                   use_spatial_hash=True)

        # Adding player sprite
        self.player_sprite = arcade.Sprite("Player.png", 1)

        # Adding coordinates for the center of the sprite
        self.player_sprite.center_x = 64
        self.player_sprite.center_y = 600

        # Adding Sprite in our scene
        self.scene.add_sprite("Player", self.player_sprite)

        # Adding platform sprite according to level
        platform = arcade.Sprite(f"Platform{self.level}.png", 1)

        # Adding coordinates for the center of the platform
        platform.center_x = 300
        platform.center_y = 32
        self.scene.add_sprite("Platforms", platform)

        # Creating Physics engine
        self.physics_engine = arcade.PhysicsEnginePlatformer(
            self.player_sprite, self.scene.get_sprite_list("Platforms"), 0.5
        )

    # Creating on_update function to
    # update the x coordinate
    def on_update(self, delta_time):

        # Changing x coordinate of player
        self.player_sprite.center_x += self.vel_x * delta_time

        # Updating the physics engine to move the player
        self.physics_engine.update()

        # Calling the camera_move function
        self.camera_move()

        # Changing level if player crosses the right
        # end of screen
        if self.player_sprite.center_x > 690:
            self.level += 1
            self.setup()

    # Creating function to change the velocity
    # when button is pressed
    def on_key_press(self, symbol, modifier):

        # Checking the button pressed
        # and changing the value of velocity
        if symbol == arcade.key.LEFT:
            self.vel_x = -300
        elif symbol == arcade.key.RIGHT:
            self.vel_x = 300

    # Creating function to change the velocity
    # when button is released
    def on_key_release(self, symbol, modifier):

        # Checking the button released
        # and changing the value of velocity
        if symbol == arcade.key.LEFT:
            self.vel_x = 0
        elif symbol == arcade.key.RIGHT:
            self.vel_x = 0

    def camera_move(self):

        # Getting the x coordinate for the center of camera
        screen_x = self.player_sprite.center_x - \
            (self.camera.viewport_width / 2)

        # Getting the y coordinate for the center of camera
        screen_y = self.player_sprite.center_y - \
            (self.camera.viewport_height / 2)

        # Moving the camera
        self.camera.move_to([screen_x, screen_y])

# Calling MainGame class
game = MainGame()
game.setup()
arcade.run()
```

**输出:**

![](img/18cf6b2cf2d271f00025f20470699da4.png)