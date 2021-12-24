# 使用 PyGame–Python 构建太空入侵者

> 原文:[https://www . geesforgeks . org/building-space-intruss-using-pygame-python/](https://www.geeksforgeeks.org/building-space-invaders-using-pygame-python/)

在本文中，我们将使用 Python 中的 PyGame 构建空间入侵者。

使用过的文件可以从[这里](https://drive.google.com/drive/folders/1LIhvAzDeeftnYVlQaVj3PMPkU-mLylmB?usp=sharing)下载。

## **进场:**

*   导入所需的模块。
*   初始化 pygame。
*   创建三个函数:
    *   **iscollection():**哪个告诉我们碰撞发生了没有？
    *   **game_over():** 返回 True 或 False，代码根据该值决定游戏是否结束。
    *   **show_score(x，y):** 在屏幕上显示分数
*   创建一个无限循环来连续执行代码。

## **isCollision():**

其实很简单。在解释这一点之前，我们希望您先看看下面游戏循环中代码的冲突部分:

## 蟒蛇 3

```
# Collision
collision = isCollision(bullet_X, invader_X[i], bullet_Y, invader_Y[i])
if collision:
        score_val += 1
        bullet_Y = 600
        bullet_state = "rest"
        invader_X[i] = random.randint(64, 736)
        invader_Y[i] = random.randint(30, 200)
        invader_Xchange[i] *= -1
```

“isCollision()”函数返回的值存储在“碰撞”变量中。根据函数内部为冲突设置的标准，函数返回的值为真或假。我们来看看 isCollision()函数里面是什么:

## python 3

```
def isCollision(x1, x2, y1, y2):
    distance = math.sqrt((math.pow(x1 - x2, 2)) + (math.pow(y1 - y2, 2)))
    if distance <= 50:
        return True
    else:
        return False
```

函数内部设置的碰撞标准最简单的就是子弹和入侵者(我们的敌人)之间的距离。如你所见，计算距离的公式是每个学生在高中数学课上学习的东西。它是坐标为(x1，y1)和(x2，y2)的两个点之间的距离公式，这两个点是作为 isCollision()函数的参数传递的。

在这里，我们设置了标准，如果距离值小于或等于 50，则表示发生了碰撞。该值是根据子弹和入侵者使用的 png 图像的高度和宽度选择的。该值可以根据您自己的要求使用试错法进行调整。

因此，每当子弹和入侵者的位置发生变化时，isCollision()函数就会检查是否发生了碰撞。这就是为什么它在游戏循环中被调用的原因。

## game_over():

返回“真”或“假”，在此基础上代码决定游戏是否结束。为了理解 game_over()函数，让我们来看看下面出现在游戏循环中的代码片段:

## python 3

```
# movement of the invader
for i in range(no_of_invaders):

        if invader_Y[i] >= 450:
            if abs(player_X-invader_X[i]) < 80:
                for j in range(no_of_invaders):
                    invader_Y[j] = 2000
                    explosion_sound = mixer.Sound('data/explosion.wav')
                    explosion_sound.play()
                game_over()
                break
```