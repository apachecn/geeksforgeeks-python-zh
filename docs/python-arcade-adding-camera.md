# Python 街机–添加摄像头

> 原文:[https://www.geeksforgeeks.org/python-arcade-adding-camera/](https://www.geeksforgeeks.org/python-arcade-adding-camera/)

在本文中，我们将学习如何在 Python 中为街机游戏添加摄像头。

## 添加摄像机

您可以使用摄像机()功能在街机中创建摄像机。

> **语法:**街机。相机(宽度。高度)
> 
> **参数:**
> 
> *   宽度:相机的宽度
> *   高度:相机的高度

为了使用这个相机，我们要创建一个新的变量。

```py
self.camera = None
```

然后在我们的 setup()函数中，我们将使用 camera()函数创建我们的相机。

```py
self.camera= arcade.Camera(200,200)
```

之后，我们将使用相机。使用 on_draw()函数中的函数来使用相机。

```py
self.camera.use()
```

在下面的例子中，我们将创建 MainGame()类。在我们的 MainGame()类中，首先我们将初始化速度、相机、场景、玩家精灵和物理引擎的一些变量，然后我们将创建 5 个函数:

*   **on_draw():** 在这个函数内部，我们将使用 arcade.start_render()开始渲染，然后我们将绘制我们的场景。
*   **setup():** 在这个函数里面，我们将调用街机。场景()和街机。Camera()函数，然后我们将在精灵列表中加载和存储我们的精灵。
*   **on_update():** 这里我们将更新我们的玩家精灵和我们的物理引擎的 x 坐标。
*   **on_key_press():** 在这个功能里面，我们会检查哪个键盘按钮被按下了，我们会根据这个来改变速度变量的值。
*   **on_key_release():** 在这个功能里面，我们会检查哪个键盘按钮被释放了，我们会根据这个来改变速度变量的值。

### 使用的精灵:

![](img/02af0c15dc736aa484a815416994dcab.png) ![](img/2bd0d0eff56a6973e57178e5be265632.png)

**下面是实现:**

## 蟒蛇 3

```py
# Importing arcade module
import arcade

# Creating MainGame class
class MainGame(arcade.Window):
    def __init__(self):
        super().__init__(600, 600, title="Player Movement")

        # Initializing a variable to store
        # the velocity of the player
        self.vel_x = 0

        # Creating variable for Camera
        self.camera = None

        # Creating scene object
        self.scene = None

        # Creating variable to store player sprite
        self.player = None

        # Creating variable for our game engine
        self.physics_engine = None

    # Creating on_draw() function to draw on the screen
    def on_draw(self):
        arcade.start_render()
        self.camera.use()
        # Drawing our scene
        self.scene.draw()

    def setup(self):

        # Initialize Scene object
        self.scene = arcade.Scene()

        # Using Camera() function
        self.camera = arcade.Camera(200, 200)

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

        # Adding platform sprite
        platform = arcade.Sprite("Platform.png", 1)

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

# Calling MainGame class
game = MainGame()
game.setup()
arcade.run()
```