# Python 中的刽子手游戏

> 原文:[https://www.geeksforgeeks.org/hangman-game-in-python/](https://www.geeksforgeeks.org/hangman-game-in-python/)

刽子手是一种文字游戏，电脑将从字典中随机选择一个单词，玩家必须在给定的圈数内正确猜测。要猜的单词用一排星星表示。如果猜出来的字母是单词，脚本会自动放在正确的地方。

> **猜词规则:**
> 
> 1.  一次输入一个字母。
> 2.  不要使用重复的字母。
> 3.  每次猜测后，匝数将减少。

这是代码 [words.txt](https://media.geeksforgeeks.org/wp content/uploads/words.txt) 里面使用的文本文件，包含 5 万个英文单词。

**所需模块:**

```py
import random
```

下面是实现:

```py
# Python program to implement Hangman game

# Importing random module
import random

# Function to randomly select
# a word from dictionary
def get_word():

    # Path to the text file
    with open('/Users/Admin/Desktop/words.txt', 'r') as f:

        # Reads each word after splitting
        words1 = f.read().splitlines()

    # Returns any random word    
    return random.choice(words1)

myword = get_word()

# Function prints row of
# stars in place of words
for i in myword:

    print("*", end = " ")

# Calculating length of word
l = len(myword)
print("\nWord has %d letters" %l)

# Check if entered letter is correct
def check(myword, your_word, guess1):
    status = ''
    matches = 0

    for letter in myword:
        if letter in your_word:
            status += letter
        else:
            status += '*'
        if letter == guess1:
            matches += 1

    if matches > 1:
        print(matches, guess1)

    elif matches == 1:
        print(guess1)
    return status

# Main Game function
def game():
    guess = 0
    guessed = False
    your_word = []
    turns = len(myword) + 1
    turns1 = turns

    print("Total turns: ", turns)
    while guess < turns1:
        guess1 = input("Enter your guess: ")

        # Decrementing turn
        # after every guess
        turns -= 1

        # Print turns left
        print("Turns left", turns)

        # If letter is already guessed
        if guess1 in your_word:
            print("You already guessed")
        elif len(guess1) == 1:

            # Appending the letters
            # on their place
            your_word.append(guess1)
            result = check(myword, your_word, guess1)

            if result == myword:
                guessed = True
                print("You won " + name)
                print(myword)
            else:
                print(result)
        else:
            print("Invalid entry")
        guess += 1
    if guess == turns1:
        print("Word is:")
        print(myword)

# Driver Code
game()
```

**输出:**

```py
* * * * * 
Word has 5 letters
Total turns:  11

Enter your guess: a
Turns left 10
**********

Enter your guess: i
Turns left 9
i
**i**i****

Enter your guess: s
Turns left 8
s
**i**i**ss

Enter your guess: r
Turns left 7
**i**i**ss

Enter your guess: h
Turns left 6
**i**i**ss

Enter your guess: e
Turns left 5
e
**i**i*ess

Enter your guess: o
Turns left 4
**i**i*ess

Enter your guess: u
Turns left 3
u
*ui**i*ess

Enter your guess: t
Turns left 2
t
*ui*ti*ess

Enter your guess: n
Turns left 1
n
*ui*tiness

Enter your guess: l
Turns left 0
l
*uiltiness

Word is:
guiltiness

```