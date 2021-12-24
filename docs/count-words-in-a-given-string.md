# 计算给定字符串中的单词数

> 原文:[https://www . geesforgeks . org/给定字符串中的字数/](https://www.geeksforgeeks.org/count-words-in-a-given-string/)

给定一个字符串，计算其中的字数。单词由以下字符分隔:空格(')或新行(' \n ')或制表符(' \t ')或这些字符的组合。

这个问题可以有很多解决办法。下面是一个简单有趣的解决方案。
想法是维持两种状态:in 和 OUT。状态“输出”表示看到一个分隔符。状态输入表示看到一个单词字符。当前一个状态为 OUT，下一个字符为单词字符时，我们增加单词计数。

## C++

```
/* C++ program to count no of words
from given input string. */
#include <bits/stdc++.h>
using namespace std;

#define OUT 0
#define IN 1

// returns number of words in str
unsigned countWords(char *str)
{
    int state = OUT;
    unsigned wc = 0; // word count

    // Scan all characters one by one
    while (*str)
    {
        // If next character is a separator, set the
        // state as OUT
        if (*str == ' ' || *str == '\n' || *str == '\t')
            state = OUT;

        // If next character is not a word separator and
        // state is OUT, then set the state as IN and
        // increment word count
        else if (state == OUT)
        {
            state = IN;
            ++wc;
        }

        // Move to next character
        ++str;
    }

    return wc;
}

// Driver code
int main(void)
{
    char str[] = "One two     three\n four\tfive ";
    cout<<"No of words : "<<countWords(str);
    return 0;
}

// This is code is contributed by rathbhupendra
```

## C

```
/* C program to count no of words from given input string. */
#include <stdio.h>

#define OUT    0
#define IN    1

// returns number of words in str
unsigned countWords(char *str)
{
    int state = OUT;
    unsigned wc = 0;  // word count

    // Scan all characters one by one
    while (*str)
    {
        // If next character is a separator, set the
        // state as OUT
        if (*str == ' ' || *str == '\n' || *str == '\t')
            state = OUT;

        // If next character is not a word separator and
        // state is OUT, then set the state as IN and
        // increment word count
        else if (state == OUT)
        {
            state = IN;
            ++wc;
        }

        // Move to next character
        ++str;
    }

    return wc;
}

// Driver program to tes above functions
int main(void)
{
    char str[] = "One two         three\n    four\tfive  ";
    printf("No of words : %u", countWords(str));
    return 0;
}
```

## Java 语言(一种计算机语言，尤用于创建网站)

```
/* Java program to count no of words
from given input string. */
public class GFG {

    static final int OUT = 0;
    static final int IN = 1;

    // returns number of words in str
    static int countWords(String str)
    {
        int state = OUT;
        int wc = 0;  // word count
        int i = 0;

        // Scan all characters one by one
        while (i < str.length())
        {
            // If next character is a separator, set the
            // state as OUT
            if (str.charAt(i) == ' ' || str.charAt(i) == '\n'
                    || str.charAt(i) == '\t')
                state = OUT;

            // If next character is not a word separator
            // and state is OUT, then set the state as IN
            // and increment word count
            else if (state == OUT)
            {
                state = IN;
                ++wc;
            }

            // Move to next character
            ++i;
        }
        return wc;
    }

    // Driver program to test above functions
    public static void main(String args[])
    {
        String str = "One two       three\n four\tfive  ";
        System.out.println("No of words : " + countWords(str));
    }
}
// This code is contributed by Sumit Ghosh
```

## 蟒蛇 3

```
# Python3 program to count words
# in a given string
OUT = 0
IN = 1

# Returns number of words in string
def countWords(string):
    state = OUT
    wc = 0

    # Scan all characters one by one
    for i in range(len(string)):

        # If next character is a separator,
        # set the state as OUT
        if (string[i] == ' ' or string[i] == '\n' or
            string[i] == '\t'):
            state = OUT

        # If next character is not a word
        # separator and state is OUT, then
        # set the state as IN and increment
        # word count
        elif state == OUT:
            state = IN
            wc += 1

    # Return the number of words
    return wc

# Driver Code
string = "One two         three\n four\tfive "
print("No. of words : " + str(countWords(string)))

# This code is contributed by BHAVYA JAIN
```

## C#

```
// C# program to count no of words
// from given input string.
using System;

class GFG {

    static int OUT = 0;
    static int IN = 1;

    // returns number of words in str
    static int countWords(String str)
    {
        int state = OUT;
        int wc = 0; // word count
        int i = 0;

        // Scan all characters one
        // by one
        while (i < str.Length)
        {
            // If next character is a separator,
            // set the state as OUT
            if (str[i] == ' ' || str[i] == '\n'||
                                  str[i] == '\t')
                state = OUT;

            // If next character is not a word
            // separator and state is OUT, then
            // set the state as IN and increment
            // word count
            else if (state == OUT)
            {
                state = IN;
                ++wc;
            }

            // Move to next character
            ++i;
        }

        return wc;
    }

    // Driver program to test above functions
    public static void Main()
    {
        String str = "One two     three\n four\tfive ";
        Console.WriteLine("No of words : "
                              + countWords(str));
    }
}

// This code is contributed by Sam007.
```

## 服务器端编程语言（Professional Hypertext Preprocessor 的缩写）

```
<?php
// PHP program to count no of
// words from given input string
$OUT = 0;
$IN = 1;

// returns number of words in str
function countWords($str)
{
    global $OUT, $IN;
    $state = $OUT;
    $wc = 0; // word count
    $i = 0;

    // Scan all characters one by one
    while ($i < strlen($str))
    {
        // If next character is
        // a separator, set the
        // state as OUT
        if ($str[$i] == " " ||
            $str[$i] == "\n" ||
            $str[$i] == "\t")
            $state = $OUT;

        // If next character is not a
        // word separator and state is
        // OUT, then set the state as
        // IN and increment word count
        else if ($state == $OUT)
        {
            $state = $IN;
            ++$wc;
        }

        // Move to next character
        ++$i;
    }

    return $wc;
}

// Driver Code
$str = "One two         three\n four\tfive ";
echo "No of words : " . countWords($str);

// This code is contributed
// by ChitraNayal
?>
```

## java 描述语言

```
<script>
// javascript program to count no of words
// from given input string.
    var OUT = 0;
    var IN = 1;

    // returns number of words in str
    function countWords( str)
    {
        var state = OUT;
        var wc = 0; // word count
        var i = 0;

        // Scan all characters one
        // by one
        while (i < str.length)
        {

            // If next character is a separator,
            // set the state as OUT
            if (str[i] == ' ' || str[i] == '\n'||
                                  str[i] == '\t')
                state = OUT;

            // If next character is not a word
            // separator and state is OUT, then
            // set the state as IN and increment
            // word count
            else if (state == OUT)
            {
                state = IN;
                ++wc;
            }

            // Move to next character
            ++i;
        }

        return wc;
    }

    // Driver program to test above functions
        var str = "One two     three\n four\tfive ";
        document.write("No of words : "
                              + countWords(str));

// This code is contributed by bunnyram19.
</script>
```

**Output**

```
No of words : 5
```

**时间复杂度:** O(n)
本文由**纳伦德拉·康拉尔卡尔**整理。如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。

**法二:使用** [**弦.劈()**](https://www.geeksforgeeks.org/split-string-java-examples/) **法**

1.  获取字符串以计算单词总数。
2.  检查字符串是否为空，然后返回 0。
3.  使用 String 类的 split()方法在空格处拆分字符串。
4.  split()方法在给定正则表达式的匹配项周围断开给定的字符串，并返回一个字符串数组。
5.  数组的长度是给定字符串中的字数。
6.  现在，打印结果。

下面是上述方法的实现:

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to count total
// number of words in the string
class GFG
{

    // Function to count total number
    // of words in the string
    public static int
      countWords(String str)
    {

        // Check if the string is null
        // or empty then return zero
        if (str == null || str.isEmpty())
            return 0;

        // Splitting the string around
        // matches of the given regular
        // expression
        String[] words = str.split("\\s+");

        // Return number of words
        // in the given string
        return words.length;
    }

    // Driver Code
    public static void main(String args[])
    {

        // Given String str
        String str =
          "One two       three\n four\tfive ";

        // Print the result
        System.out.println("No of words : " +
           countWords(str));
    }
}
// This code is contributed by Prashant Srivastava
```

**Output**

```
No of words : 5
```

**时间复杂度:** O(N)

**方法三:使用**[**stringtokenizer . count token()**](https://www.geeksforgeeks.org/stringtokenizer-counttokens-method-in-java-with-examples/)**方法**

1.  获取字符串以计算单词总数。
2.  检查字符串是否为空，然后返回 0。
3.  使用作为参数传递的给定字符串创建一个 StringTokenizer。
4.  使用 countTokens()方法计算给定字符串中的总字数。
5.  现在，打印结果。

下面是上述方法的实现:

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to count total
// number of words in the string
import java.util.StringTokenizer;
class GFG
{

    // Function to count total number
    // of words in the string
    public static int
      countWords(String str)
    {

        // Check if the string is null
        // or empty then return zero
        if (str    == null || str.isEmpty())
            return 0;

        // Create a StringTokenizer with the
        // given string passed as a parameter
        StringTokenizer tokens = new
          StringTokenizer(str);

        // Return the number of words
        // in the given string using
        // countTokens() method
        return tokens.countTokens();
    }

    // Driver Code
    public static void main(String args[])
    {

        // Given String str
        String str =
          "One two       three\n four\tfive ";

        // Print the result
        System.out.println("No of words: " +
          countWords(str));
    }
}
// This code is contributed by Prashant Srivastava
```

**Output**

```
No of words: 5
```

**时间复杂度:** O(N)

**方法四:使用 Character.isLetter()方法**

1.  获取字符串以计算单词总数。
2.  检查字符串是否为空，然后返回 0。
3.  将给定字符串转换为字符数组。
4.  检查字符是否是字母，字符数组的索引是否不等于行尾，也就是说，它是一个单词，并将 *isWord* 设置为 true。
5.  检查字符是否不是字母，表示有空格，然后将*字数*增加 1，将*字数*设置为假。
6.  检查句子的最后一个单词，并将*字数*增加 1。
7.  现在，打印结果。

下面是上述方法的实现:

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to count total
// number of words in the string
class GFG
{

    // Function to count total number
    // of words in the string
    public static int
      countWords(String str)
    {

        // Check if the string is null
        // or empty then return zero
        if(str    == null || str.isEmpty())
            return 0;

        int wordCount = 0;

        boolean isWord = false;
        int endOfLine = str.length() - 1;

        // Converting the given string
        // into a character array
        char[] ch = str.toCharArray();

        for (int i = 0; i < ch.length; i++) {

            // Check if the character is a letter
            // and index of character array doesn't
            // equal to end of line that means, it is
            // a word and set isWord by true
            if (Character.isLetter(ch[i])
                && i != endOfLine)

                isWord = true;

            // Check if the character is not a letter
            // that means there is a space, then we
            // increment the wordCount by one and set
            // the isWord by false
            else if (!Character.isLetter(ch[i])
                     && isWord) {

                wordCount++;
                isWord = false;
            }

            // Check for the last word of the
            // sentence and increment the wordCount
            // by one
            else if (Character.isLetter(ch[i])
                     && i == endOfLine)
                wordCount++;
        }

        // Return the total number of
        // words in the string
        return wordCount;

    }

    // Driver Code
    public static void main(String args[])
    {

        // Given String str
        String str =
          "One two       three\n four\tfive ";

        // Print the result
        System.out.println("No of words : " +
          countWords(str));
    }
}
// This code is contributed by Prashant Srivastava
```

## 蟒蛇 3

```
# Python program to count total
# number of words in the string

# Function to count total number
# of words in the string
def countWords(Str):

    # Check if the string is null
    # or empty then return zero
    if(Str == None or len(Str) == 0):
        return 0

    wordCount = 0
    isWord = False
    endOfLine = len(Str) - 1

    # Converting the given string
    # into a character array
    ch = list(Str)
    for i in range(len(ch)):

        # Check if the character is a letter
        # and index of character array doesn't
        # equal to end of line that means, it is
        # a word and set isWord by true
        if(ch[i].isalpha() and i != endOfLine):
            isWord = True

        # Check if the character is not a letter
        # that means there is a space, then we
        # increment the wordCount by one and set
        # the isWord by false
        elif(not ch[i].isalpha() and isWord):
            wordCount += 1
            isWord = False

        # Check for the last word of the
        # sentence and increment the wordCount
        # by one
        elif(ch[i].isalpha() and i == endOfLine):
            wordCount += 1

    # Return the total number of
    # words in the string
    return wordCount

# Driver Code

# Given String str
Str =  "One two       three\n four\tfive "

# Print the result
print("No of words :", countWords(Str))

# This code is contributed by rag2127
```

## C#

```
// C# program to count total
// number of words in the string
using System;
public class GFG
{

  // Function to count total number
  // of words in the string
  static int countWords(String str)
  {

    // Check if the string is null
    // or empty then return zero
    if(str == null)
    {
      return 0;
    }
    int wordCount = 0;
    bool isWord = false;
    int endOfLine = str.Length - 1;

    // Converting the given string 
    // into a character array
    char[] ch = str.ToCharArray();
    for (int i = 0; i < ch.Length; i++)
    {

      // Check if the character is a letter
      // and index of character array doesn't
      // equal to end of line that means, it is
      // a word and set isWord by true
      if (Char.IsLetter(ch[i]) 
          && i != endOfLine)
      {
        isWord = true;
      }

      // Check if the character is not a letter
      // that means there is a space, then we
      // increment the wordCount by one and set
      // the isWord by false
      else if (!Char.IsLetter(ch[i]) 
               && isWord)

      {
        wordCount++;
        isWord = false;
      }

      // Check for the last word of the 
      // sentence and increment the wordCount 
      // by one
      else if (Char.IsLetter(ch[i])
               && i == endOfLine)
      {
        wordCount++;
      }
    }

    // Return the total number of 
    // words in the string
    return wordCount;
  }

  // Driver Code
  static public void Main ()
  {

    // Given String str
    string str = "One two       three\n four\tfive ";

    // Print the result
    Console.WriteLine("No of words : " + countWords(str));
  }
}

// This code is contributed by avanitrachhadiya2155
```

## java 描述语言

```
<script>
// Javascript program to count total
// number of words in the string

// Function to count total number
    // of words in the string
function countWords(str)
{
    // Check if the string is null
        // or empty then return zero
        if(str    == null || str.length==0)
            return 0;

        let wordCount = 0;

        let isWord = false;
        let endOfLine = str.length - 1;

        // Converting the given string
        // into a character array
        let ch = str.split("");

        for (let i = 0; i < ch.length; i++) {

            // Check if the character is a letter
            // and index of character array doesn't
            // equal to end of line that means, it is
            // a word and set isWord by true
            if (isLetter(ch[i])
                && i != endOfLine)

                isWord = true;

            // Check if the character is not a letter
            // that means there is a space, then we
            // increment the wordCount by one and set
            // the isWord by false
            else if (!isLetter(ch[i])
                     && isWord) {

                wordCount++;
                isWord = false;
            }

            // Check for the last word of the
            // sentence and increment the wordCount
            // by one
            else if (isLetter(ch[i])
                     && i == endOfLine)
                wordCount++;
        }

        // Return the total number of
        // words in the string
        return wordCount;
}

function isLetter(c) {
  return c.toLowerCase() != c.toUpperCase();
}

// Driver Code

 // Given String str
let str="One two       three\n four\tfive ";

// Print the result
document.write("No of words : " +
          countWords(str));

// This code is contributed by ab2127
</script>
```

**Output**

```
No of words : 5
```

**时间复杂度:** O(N)