# 使用 Python 策划游戏

> 原文:[https://www.geeksforgeeks.org/mastermind-game-using-python/](https://www.geeksforgeeks.org/mastermind-game-using-python/)

鉴于当代人对游戏及其高要求技术的了解，许多人渴望进一步发展和推进游戏。最终，每个人都要从头开始。摄魂师是一款由两个玩家玩的破密码老游戏。这个游戏可以追溯到 19 世纪，可以用纸和铅笔玩。

**先决条件:**
[Python 中的随机数](https://www.geeksforgeeks.org/random-numbers-in-python/)

#### 游戏规则

两个玩家互相进行游戏；让我们假设玩家 1 和玩家 2。

*   **玩家 1** 通过设置多位数先玩。
*   **玩家 2** 现在尝试第一次猜数字。
*   如果玩家 2 第一次尝试成功(尽管几率极小)，他就赢得了游戏，并加冕为摄魂师！如果不是，那么玩家 1 通过显示玩家 2 得到的数字或数字来提示。
*   游戏继续进行，直到玩家 2 最终能够完全猜出数字。
*   现在**玩家 2** 开始设置数字，玩家 1 扮演猜数字的角色。
*   如果玩家 1 能够在比玩家 2 更少的尝试次数内猜出数字，则玩家 1 赢得游戏并加冕为摄魂师。
*   如果没有，那么玩家 2 赢得游戏。
*   然而，真正的游戏已经证明了美学，因为数字是由彩色编码的按钮表示的。

例如:
**输入:**

```
Player 1, set the number: 5672
Player 2, guess the number: 1472

```

**输出:**

```
Not quite the number. You did get 2 digits correct.
X X 7 2

Enter your next choice of numbers:

```

我们将不使用任何`Pygame`库来帮助我们获得额外的图形，因此将只处理框架和概念。此外，我们将与计算机对战，也就是说，计算机将生成要猜测的数字。

以下是上述想法的实现。

```
import random

# the .randrange() function generates a
# random number within the specified range.
num = random.randrange(1000, 10000)  

n = int(input("Guess the 4 digit number:"))

# condition to test equality of the
# guess made. Program terminates if true.
if (n == num):  
    print("Great! You guessed the number in just 1 try! You're a Mastermind!")
else:
    # ctr variable initialized. It will keep count of 
    # the number of tries the Player takes to guess the number.
    ctr = 0  

    # while loop repeats as long as the 
    # Player fails to guess the number correctly.
    while (n != num):  
        # variable increments every time the loop
        # is executed, giving an idea of how many
        # guesses were made.
        ctr += 1  

        count = 0

        # explicit type conversion of an integer to
        # a string in order to ease extraction of digits
        n = str(n)  

        # explicit type conversion of a string to an integer
        num = str(num)  

        # correct[] list stores digits which are correct
        correct = ['X']*4  

        # for loop runs 4 times since the number has 4 digits.
        for i in range(0, 4): 

             # checking for equality of digits
            if (n[i] == num[i]):  
                # number of digits guessed correctly increments
                count += 1  
                # hence, the digit is stored in correct[].
                correct[i] = n[i]  
            else:
                continue

        # when not all the digits are guessed correctly.
        if (count < 4) and (count != 0):  
            print("Not quite the number. But you did get ", count, " digit(s) correct!")
            print("Also these numbers in your input were correct.")
            for k in correct:
                print(k, end=' ')
            print('\n')
            print('\n')
            n = int(input("Enter your next choice of numbers: "))

        # when none of the digits are guessed correctly.
        elif (count == 0):  
            print("None of the numbers in your input match.")
            n = int(input("Enter your next choice of numbers: "))

    # condition for equality.
    if n == num:  
        print("You've become a Mastermind!")
        print("It took you only", ctr, "tries.")
```

让我们假设计算机设定的数字是 1564

**输出:**

```
Guess the 4 digit number: 1564

Great! You guessed the number in just 1 try! You're a Mastermind!

```

如果这个数字一次都猜不到。

**输出:**

```
Guess the 4 digit number: 2164    

Not quite the number. But you did get 2 digit(s) correct!
Also these numbers in your input were correct.
X X 6 4

Enter your next choice of numbers: 3564
Not quite the number. But you did get 2 digit(s) correct!
Also these numbers in your input were correct.
X 5 6 4

Enter your next choice of numbers: 1564
You've become a Mastermind.
It took you only 3 tries.

```

您可以通过增加输入的位数或不透露输入中哪些数字被正确放置来增加游戏难度。
这已经在下面的代码中解释过了。

```
import random

#the .randrange() function generates
# a random number within the specified range.
num = random.randrange(1000,10000) 

n = int(input("Guess the 4 digit number:"))

# condition to test equality of the 
# guess made. Program terminates if true.
if(n == num):             
     print("Great! You guessed the number in just 1 try! You're a Mastermind!")
else:
     # ctr variable initialized. It will keep count of 
     # the number of tries the Player takes to guess the number.
     ctr = 0    

     # while loop repeats as long as the Player
     # fails to guess the number correctly.
     while(n!=num):
          # variable increments every time the loop 
          # is executed, giving an idea of how many 
          # guesses were made.
          ctr += 1             

          count = 0

          # explicit type conversion of an integer to 
          # a string in order to ease extraction of digits
          n = str(n) 

          # explicit type conversion of a string to an integer                                 
          num = str(num)

          # correct[] list stores digits which are correct 
          correct=[]        

          # for loop runs 4 times since the number has 4 digits.     
          for i in range(0,4): 
              # checking for equality of digits
              if(n[i] == num[i]): 
                  # number of digits guessed correctly increments
                  count += 1    
                  # hence, the digit is stored in correct[].
                  correct.append(n[i])     
              else:
                  continue

          # when not all the digits are guessed correctly.
          if (count < 4) and (count != 0):     
              print("Not quite the number. But you did get ",count," digit(s) correct!")
              print("Also these numbers in your input were correct.")

              for k in correct:
                  print(k, end=' ')

              print('\n')
              print('\n')
              n = int(input("Enter your next choice of numbers: "))

          # when none of the digits are guessed correctly.
          elif(count == 0):         
              print("None of the numbers in your input match.")
              n=int(input("Enter your next choice of numbers: ")) 

     if n==num:                
         print("You've become a Mastermind!")
         print("It took you only",ctr,"tries.")

```

假设计算机设定的数字是 54876。

**输出:**

```
Guess the 5 digit number: 38476

Not quite the number. But you did get 2 digit(s) correct! 
Enter your next choice of numbers: 41876

Not quite the number. But you did get 4 digit(s) correct!
Enter the next choice of numbers: 54876

Great you've become a Mastermind!
It took you only 3 tries!

```

修改这段代码的整个范围是巨大的。这里的想法是了解这个概念是什么。像这种依赖类似基本代码的游戏还有很多。

通过利用这段代码，进一步开发它，同时结合 Pygame 的库，将使它更像真正的交易，更不用说涉及更多了！