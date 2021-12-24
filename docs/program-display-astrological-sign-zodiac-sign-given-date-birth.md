# 显示给定出生日期的占星星座或黄道星座的程序

> 原文:[https://www . geesforgeks . org/program-display-占星-星座-生肖-星座-给定日期-出生/](https://www.geeksforgeeks.org/program-display-astrological-sign-zodiac-sign-given-date-birth/)

对于给定的出生日期，这个程序显示一个占星符号或十二生肖符号。
示例:

```py
Input : Day = 10, Month = December
Output : Sagittarius
Explanation :
People born on this date have a zodiac *Sagittarius*.

Input : Day = 7, Month = September
Output : Virgo
```

**方法:**
虽然精确的日期可以一天左右移动，但取决于年份，以下是西方(或热带)占星术使用的一般生肖日期:

```py
WESTERN ASTROLOGY STAR SIGN DATES :

Aries (March 21-April 19)
Taurus (April 20-May 20)
Gemini (May 21-June 20)
Cancer (June 21-July 22)
Leo (July 23-August 22)
Virgo (August 23-September 22)
Libra (September 23-October 22)
Scorpio (October 23-November 21)
Sagittarius (November 22-December 21)
Capricorn (December 22-January 19)
Aquarius (January 20-February 18)
Pisces (February 19-March 20) 
```

我们需要检查我们提到的日期和月份，从而找到它的对应生肖，即哪个生肖适合那个特定的日期和月份，并打印它相应的生肖。
以下是上述方法的实施:

## C++

```py
// CPP program to display astrological sign
// or Zodiac sign for given date of birth
#include <bits/stdc++.h>
using namespace std;

void zodiac_sign(int day, string month)
{
    string astro_sign="";

    // checks month and date within the
    // valid range of a specified zodiac
    if (month == "december"){

        if (day < 22)
        astro_sign = "Sagittarius";
        else
        astro_sign ="capricorn";
    }

    else if (month == "january"){
        if (day < 20)
        astro_sign = "Capricorn";
        else
        astro_sign = "aquarius";
    }

    else if (month == "february"){
        if (day < 19)
        astro_sign = "Aquarius";
        else
        astro_sign = "pisces";
    }

    else if(month == "march"){
        if (day < 21)
        astro_sign = "Pisces";
        else
        astro_sign = "aries";
    }
    else if (month == "april"){
        if (day < 20)
        astro_sign = "Aries";
        else
        astro_sign = "taurus";
    }

    else if (month == "may"){
        if (day < 21)
        astro_sign = "Taurus";
        else
        astro_sign = "gemini";
    }

    else if( month == "june"){
        if (day < 21)
        astro_sign = "Gemini";
        else
        astro_sign = "cancer";
    }

    else if (month == "july"){
        if (day < 23)
        astro_sign = "Cancer";
        else
        astro_sign = "leo";
    }

    else if( month == "august"){
        if (day < 23)
        astro_sign = "Leo";
        else
        astro_sign = "virgo";
    }

    else if (month == "september"){
        if (day < 23)
        astro_sign = "Virgo";
        else
        astro_sign = "libra";
    }

    else if (month == "october"){
        if (day < 23)
        astro_sign = "Libra";
        else
        astro_sign = "scorpio";
    }

    else if (month == "november"){
        if (day < 22)
        astro_sign = "scorpio";
        else
        astro_sign = "sagittarius";
    }

    cout<<astro_sign;
}

// Driver code
int main ()
{

    int day = 19;
    string month = "may";
    zodiac_sign(day, month);

    return 0;
}

// This code is contributed by Gitanjali.
```

## Java 语言(一种计算机语言，尤用于创建网站)

```py
// Java program to display astrological sign
// or Zodiac sign for given date of birth
import java.io.*;

class GFG {

    static void zodiac_sign(int day, String month)
    {
        String astro_sign="";

        // checks month and date within the
        // valid range of a specified zodiac
        if (month == "december"){

            if (day < 22)
            astro_sign = "Sagittarius";
            else
            astro_sign ="capricorn";
        }

        else if (month == "january"){
            if (day < 20)
            astro_sign = "Capricorn";
            else
            astro_sign = "aquarius";
        }

        else if (month == "february"){
            if (day < 19)
            astro_sign = "Aquarius";
            else
            astro_sign = "pisces";
        }

        else if(month == "march"){
            if (day < 21)
            astro_sign = "Pisces";
            else
            astro_sign = "aries";
        }
        else if (month == "april"){
            if (day < 20)
            astro_sign = "Aries";
            else
            astro_sign = "taurus";
        }

        else if (month == "may"){
            if (day < 21)
            astro_sign = "Taurus";
            else
            astro_sign = "gemini";
        }

        else if( month == "june"){
            if (day < 21)
            astro_sign = "Gemini";
            else
            astro_sign = "cancer";
        }

        else if (month == "july"){
            if (day < 23)
            astro_sign = "Cancer";
            else
            astro_sign = "leo";
        }

        else if( month == "august"){
            if (day < 23)
            astro_sign = "Leo";
            else
            astro_sign = "virgo";
        }

        else if (month == "september"){
            if (day < 23)
            astro_sign = "Virgo";
            else
            astro_sign = "libra";
        }

        else if (month == "october"){
            if (day < 23)
            astro_sign = "Libra";
            else
            astro_sign = "scorpio";
        }

        else if (month == "november"){
            if (day < 22)
            astro_sign = "scorpio";
            else
            astro_sign = "sagittarius";
        }

        System.out.println(astro_sign);
    }

    // Driver code
    public static void main (String[] args)
    {

        int day = 19;
        String month = "may";
        zodiac_sign(day, month);

    }
}

// This code is contributed by Gitanjali.
```

## 计算机编程语言

```py
# Python program to display astrological sign
# or Zodiac sign for given date of birth

def zodiac_sign(day, month):

    # checks month and date within the valid range
    # of a specified zodiac
    if month == 'december':
        astro_sign = 'Sagittarius' if (day < 22) else 'capricorn'

    elif month == 'january':
        astro_sign = 'Capricorn' if (day < 20) else 'aquarius'

    elif month == 'february':
        astro_sign = 'Aquarius' if (day < 19) else 'pisces'

    elif month == 'march':
        astro_sign = 'Pisces' if (day < 21) else 'aries'

    elif month == 'april':
        astro_sign = 'Aries' if (day < 20) else 'taurus'

    elif month == 'may':
        astro_sign = 'Taurus' if (day < 21) else 'gemini'

    elif month == 'june':
        astro_sign = 'Gemini' if (day < 21) else 'cancer'

    elif month == 'july':
        astro_sign = 'Cancer' if (day < 23) else 'leo'

    elif month == 'august':
        astro_sign = 'Leo' if (day < 23) else 'virgo'

    elif month == 'september':
        astro_sign = 'Virgo' if (day < 23) else 'libra'

    elif month == 'october':
        astro_sign = 'Libra' if (day < 23) else 'scorpio'

    elif month == 'november':
        astro_sign = 'scorpio' if (day < 22) else 'sagittarius'

    print(astro_sign)

# Driver code
if __name__ == '__main__':
    day = 19
    month = "may"
    zodiac_sign(day, month)
```

## C#

```py
// C# program to display astrological sign
// or Zodiac sign for given date of birth
using System;

class GFG {

    static void zodiac_sign(int day, string month)
    {
        string astro_sign="";

        // checks month and date within the
        // valid range of a specified zodiac
        if (month == "december"){

            if (day < 22)
            astro_sign = "Sagittarius";
            else
            astro_sign ="capricorn";
        }

        else if (month == "january"){
            if (day < 20)
            astro_sign = "Capricorn";
            else
            astro_sign = "aquarius";
        }

        else if (month == "february"){
            if (day < 19)
            astro_sign = "Aquarius";
            else
            astro_sign = "pisces";
        }

        else if(month == "march"){
            if (day < 21)
            astro_sign = "Pisces";
            else
            astro_sign = "aries";
        }
        else if (month == "april"){
            if (day < 20)
            astro_sign = "Aries";
            else
            astro_sign = "taurus";
        }

        else if (month == "may"){
            if (day < 21)
            astro_sign = "Taurus";
            else
            astro_sign = "gemini";
        }

        else if( month == "june"){
            if (day < 21)
            astro_sign = "Gemini";
            else
            astro_sign = "cancer";
        }

        else if (month == "july"){
            if (day < 23)
            astro_sign = "Cancer";
            else
            astro_sign = "leo";
        }

        else if( month == "august"){
            if (day < 23)
            astro_sign = "Leo";
            else
            astro_sign = "virgo";
        }

        else if (month == "september"){
            if (day < 23)
            astro_sign = "Virgo";
            else
            astro_sign = "libra";
        }

        else if (month == "october"){
            if (day < 23)
            astro_sign = "Libra";
            else
            astro_sign = "scorpio";
        }

        else if (month == "november"){
            if (day < 22)
            astro_sign = "scorpio";
            else
            astro_sign = "sagittarius";
        }

        Console.WriteLine(astro_sign);
    }

    // Driver code
    public static void Main ()
    {

        int day = 19;
        string month = "may";
        zodiac_sign(day, month);

    }
}

// This code is contributed by vt_m.
```

## java 描述语言

```py
<script>

// JavaScript program to display astrological sign
// or Zodiac sign for given date of birth

// Function to calculate sum
// digits of n
function zodiac_sign(day, month)
    {
        let astro_sign="";

        // checks month and date within the
        // valid range of a specified zodiac
        if (month == "december"){

            if (day < 22)
            astro_sign = "Sagittarius";
            else
            astro_sign ="capricorn";
        }

        else if (month == "january"){
            if (day < 20)
            astro_sign = "Capricorn";
            else
            astro_sign = "aquarius";
        }

        else if (month == "february"){
            if (day < 19)
            astro_sign = "Aquarius";
            else
            astro_sign = "pisces";
        }

        else if(month == "march"){
            if (day < 21)
            astro_sign = "Pisces";
            else
            astro_sign = "aries";
        }
        else if (month == "april"){
            if (day < 20)
            astro_sign = "Aries";
            else
            astro_sign = "taurus";
        }

        else if (month == "may"){
            if (day < 21)
            astro_sign = "Taurus";
            else
            astro_sign = "gemini";
        }

        else if( month == "june"){
            if (day < 21)
            astro_sign = "Gemini";
            else
            astro_sign = "cancer";
        }

        else if (month == "july"){
            if (day < 23)
            astro_sign = "Cancer";
            else
            astro_sign = "leo";
        }

        else if( month == "august"){
            if (day < 23)
            astro_sign = "Leo";
            else
            astro_sign = "virgo";
        }

        else if (month == "september"){
            if (day < 23)
            astro_sign = "Virgo";
            else
            astro_sign = "libra";
        }

        else if (month == "october"){
            if (day < 23)
            astro_sign = "Libra";
            else
            astro_sign = "scorpio";
        }

        else if (month == "november"){
            if (day < 22)
            astro_sign = "scorpio";
            else
            astro_sign = "sagittarius";
        }

        document.write(astro_sign);
    }

// Driver Code

        let day = 19;
        let month = "may";
        zodiac_sign(day, month);

</script>
```

**输出:**

```py
Taurus
```