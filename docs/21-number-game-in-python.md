# Python 中的 21 号游戏

> 原文:[https://www.geeksforgeeks.org/21-number-game-in-python/](https://www.geeksforgeeks.org/21-number-game-in-python/)

21，巴格拉姆，或 20 加 1，是一种通过从 1 数到 21 的游戏，称“21”的玩家被淘汰。它可以在任意数量的玩家之间播放。

**实现**
这是一款使用 Python 编程语言的简单 21 号游戏。这里说明的游戏是玩家和电脑之间的游戏。游戏中可以有很多变化。

*   玩家可以选择先开始还是后开始。
*   数字列表会在玩家轮到他之前显示出来，这样就方便了。
*   如果在输入中没有给出连续的数字，那么玩家将自动被取消资格。
*   如果玩家有机会打 21，他就输了，否则就赢了。

选择打第二局就有可能赢下电脑。策略是呼叫号码直到 4 的倍数，这将最终导致计算机上的 21，因此使玩家成为赢家。

```py
# Python code to play 21 Number game

# returns the nearest multiple to 4
def nearestMultiple(num):
    if num >= 4:
        near = num + (4 - (num % 4))
    else:
        near = 4
    return near

def lose1():
    print ("\n\nYOU LOSE !")
    print("Better luck next time !")
    exit(0)

# checks whether the numbers are consecutive
def check(xyz):
    i = 1
    while i<len(xyz):
        if (xyz[i]-xyz[i-1])!= 1:
            return False
        i = i + 1
    return True

# starts the game
def start1():
    xyz = []
    last = 0
    while True:
        print ("Enter 'F' to take the first chance.")
        print("Enter 'S' to take the second chance.")
        chance = input('> ')

        # player takes the first chance
        if chance == "F":
            while True:
                if last == 20:
                    lose1()
                else:
                    print ("\nYour Turn.")
                    print ("\nHow many numbers do you wish to enter?")
                    inp = int(input('> '))

                    if inp > 0 and inp <= 3:
                        comp = 4 - inp
                    else:
                        print ("Wrong input. You are disqualified from the game.")
                        lose1()

                    i, j = 1, 1

                    print ("Now enter the values")
                    while i <= inp:
                        a = input('> ')
                        a = int(a)
                        xyz.append(a)
                        i = i + 1

                    # store the last element of xyz.
                    last = xyz[-1] 

                    # checks whether the input 
                    # numbers are consecutive
                    if check(xyz) == True: 
                        if last == 21:
                            lose1()

                        else:
                            #"Computer's turn."
                            while j <= comp:
                                xyz.append(last + j)
                                j = j + 1
                            print ("Order of inputs after computer's turn is: ")
                            print (xyz)
                            last = xyz[-1]
                    else:
                        print ("\nYou did not input consecutive integers.")
                        lose1()

        # player takes the second chance
        elif chance == "S":
            comp = 1
            last = 0
            while last < 20:
                #"Computer's turn"
                j = 1
                while j <= comp:
                    xyz.append(last + j)
                    j = j + 1
                print ("Order of inputs after computer's turn is:")
                print (xyz)
                if xyz[-1] == 20:
                    lose1()

                else:
                    print ("\nYour turn.")
                    print ("\nHow many numbers do you wish to enter?")
                    inp = input('> ')
                    inp = int(inp)
                    i = 1
                    print ("Enter your values")
                    while i <= inp:
                        xyz.append(int(input('> ')))
                        i = i + 1
                    last = xyz[-1]
                    if check(xyz) == True:
                        # print (xyz)
                        near = nearestMultiple(last)
                        comp = near - last
                        if comp == 4:
                            comp = 3
                        else:
                            comp = comp
                    else:
                        # if inputs are not consecutive
                        # automatically disqualified
                        print ("\nYou did not input consecutive integers.")
                        # print ("You are disqualified from the game.")
                        lose1()
            print ("\n\nCONGRATULATIONS !!!")
            print ("YOU WON !")
            exit(0)

        else:
            print ("wrong choice")

game = True    
while game == True:
        print ("Player 2 is Computer.")
        print("Do you want to play the 21 number game? (Yes / No)")
        ans = input('> ')
        if ans =='Yes':
            start1()
        else:
            print ("Do you want quit the game?(yes / no)")
            nex = input('> ')
            if nex == "yes":
                print ("You are quitting the game...")
                exit(0)
            elif nex == "no":
                print ("Continuing...")
            else:
                print ("Wrong choice")

```

**输出:**

```py
Player 2 is Computer.
Do you want to start the game? (Yes/No)
> Yes
Enter 'F' to take the first chance.
Enter 'S' to take the second chance.
> S
Order of inputs after computer's turn is:
[1]

Your turn.

How many numbers do you wish to enter?
> 3
Enter your values
> 2
> 3
> 4
Order of inputs after computer's turn is:
[1, 2, 3, 4, 5, 6, 7]

Your turn.

How many numbers do you wish to enter?
> 1
Enter your values
> 8
Order of inputs after computer's turn is:
[1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11]

Your turn.

How many numbers do you wish to enter?
> 1
Enter your values
> 12
Order of inputs after computer's turn is:
[1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15]

Your turn.

How many numbers do you wish to enter?
> 1
Enter your values
> 16
Order of inputs after computer's turn is:
[1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19]

Your turn.

How many numbers do you wish to enter?
> 1
Enter your values
> 20

CONGRATULATIONS!!!
YOU WON! 

```

**自己试试作为锻炼:**

*   你可以通过增加玩家数量来进一步增强程序。
*   您也只能使用偶数/奇数。
*   你可以用二进制数字系统代替数字。
*   你可以在游戏中添加不同的关卡。