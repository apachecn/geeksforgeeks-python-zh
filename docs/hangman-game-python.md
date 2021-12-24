# Python 中的刽子手游戏

> 原文:[https://www.geeksforgeeks.org/hangman-game-python/](https://www.geeksforgeeks.org/hangman-game-python/)

《牛津文字游戏指南》的作者托尼·奥加德说:“刽子手维基:
刽子手的起源是模糊的，意思是没有被发现，但它似乎是在维多利亚时代出现的。这个游戏在 1894 年爱丽丝·伯莎·戈姆的《传统游戏》中以“鸟、兽和鱼”的名字被提到。“规则很简单；一个玩家写下一个单词的首字母和末字母，另一个玩家猜测中间的字母。在其他来源，[哪里？]这个游戏叫做“绞刑架”、“绞刑游戏”或“绞刑架”。

**实施**

这是一个使用 Python 编程语言的简单 Hangman 游戏。初学者可以将此作为一个小项目来提升自己的编程技能和理解逻辑。

1.  刽子手程序从秘密词列表中随机选择一个秘密词。随机模块将提供这种能力，所以程序中的第 1 行导入它。
2.  **游戏:**在这里，从我们的收集中随机拾取一个单词(一个水果名称)，玩家获得有限的机会赢得游戏。
3.  当该单词中的一个字母被猜对时，该单词中该字母的位置就会变得可见。这样，在所有的机会结束之前，这个单词的所有字母都将被猜到。
4.  为了方便起见，我们给了字数+ 2 的机会。例如，要猜测的单词是芒果，那么用户得到 5 + 2 = 7 的机会，因为芒果是一个五个字母的单词。

```py
# Python Program to illustrate 
# Hangman Game
import random
from collections import Counter

someWords = '''apple banana mango strawberry 
orange grape pineapple apricot lemon coconut watermelon
cherry papaya berry peach lychee muskmelon'''

someWords = someWords.split(' ')
# randomly choose a secret word from our "someWords" LIST.
word = random.choice(someWords)         

if __name__ == '__main__':
    print('Guess the word! HINT: word is a name of a fruit')

    for i in word:
         # For printing the empty spaces for letters of the word
        print('_', end = ' ')        
    print()

    playing = True
     # list for storing the letters guessed by the player
    letterGuessed = ''                
    chances = len(word) + 2
    correct = 0
    flag = 0
    try:
        while (chances != 0) and flag == 0: #flag is updated when the word is correctly guessed 
            print()
            chances -= 1

            try:
                guess = str(input('Enter a letter to guess: '))
            except:
                print('Enter only a letter!')
                continue

            # Validation of the guess
            if not guess.isalpha():
                print('Enter only a LETTER')
                continue
            elif len(guess) > 1:
                print('Enter only a SINGLE letter')
                continue
            elif guess in letterGuessed:
                print('You have already guessed that letter')
                continue

            # If letter is guessed correctly
            if guess in word:
                k = word.count(guess) #k stores the number of times the guessed letter occurs in the word
                for _ in range(k):    
                    letterGuessed += guess # The guess letter is added as many times as it occurs

            # Print the word
            for char in word:
                if char in letterGuessed and (Counter(letterGuessed) != Counter(word)):
                    print(char, end = ' ')
                    correct += 1
                # If user has guessed all the letters
                elif (Counter(letterGuessed) == Counter(word)): # Once the correct word is guessed fully, 
                                                                # the game ends, even if chances remain
                    print("The word is: ", end=' ')
                    print(word)
                    flag = 1
                    print('Congratulations, You won!')
                    break # To break out of the for loop
                    break # To break out of the while loop
                else:
                    print('_', end = ' ')

        # If user has used all of his chances
        if chances <= 0 and (Counter(letterGuessed) != Counter(word)):
            print()
            print('You lost! Try again..')
            print('The word was {}'.format(word))

    except KeyboardInterrupt:
        print()
        print('Bye! Try again.')
        exit()
```

**注意:**请在你的终端上运行程序。

```py
omkarpathak@omkarpathak-Inspiron-3542:~/Documents/
Python-Programs$ python P37_HangmanGame.py 
Guess the word! HINT: word is a name of a fruit
_ _ _ _ _ 

Enter a letter to guess: m
_ _ m _ _ 
Enter a letter to guess: o
_ _ m o _ 
Enter a letter to guess: l
l _ m o _ 
Enter a letter to guess: e
l e m o _ 
Enter a letter to guess: n
l e m o n 
Congratulations, You won!

```

**自己试试练习:**

*   您可以通过在每次猜测后添加计时器来进一步增强程序
*   您也可以从一开始就给出提示，让任务对用户来说稍微容易一点
*   如果玩家的猜测是错误的，你也可以减少一次机会。如果猜测正确，
    玩家的几率不降低

本文由 **Omkar Pathak** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。