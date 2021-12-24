# 根据学生年龄分配糖果

> 原文:[https://www . geesforgeks . org/按学生年龄分发糖果/](https://www.geeksforgeeks.org/distribution-of-candies-according-to-ages-of-students/)

给定两个整数数组 age 和 pack，其中 age 存储不同学生的年龄，pack 的一个元素存储该包的糖果数量(完整数组表示包的数量)。糖果可以分发给学生，这样:

1.  每个学生只能得到一包糖果。
2.  所有同龄的学生必须得到同等数量的糖果。
3.  一个年龄大的学生比所有比他小的学生得到的糖果都多。

任务是确定是否有可能以所描述的方式分发糖果。如果可能，则打印是，否则打印否

**示例:**

> **输入:**年龄[] = {5，15，10}，包[] = {2，2，2，3，3，4}
> **输出:**是
> 有 3 个 5，15，10 岁的学生。还有 6 包糖果，分别装 2、2、2、3、3、4 颗糖果。
> 我们会给 5 岁的学生一包 2 颗糖，给 10 岁的学生一包 3 颗糖，给 15 岁的学生一包 4 颗糖
> 
> **输入:**年龄[] = {5，5，6，7}，包[] = {5，4，6，6}
> **输出:**否

**进场:**

*   制作两个频率阵列，一个存储特定年龄学生的数量，一个存储特定数量糖果的包装数量。
*   然后遍历从最小年龄开始的年龄的频率数组，并且对于每个年龄以升序尝试找到大于或等于所选年龄的学生数量的糖果包(从一包糖果的最少数量开始)
*   如果上述情况失败，则答案为否，否则重复上述步骤，直到所有学生都拿到糖果，最后打印“是”。

下面是上述方法的实现:

## C++

```
// C++ implementation of the approach
#include <bits/stdc++.h>
using namespace std;

// Function to check The validity of distribution
void check_distribution(int n, int k,
                        int age[], int candy[])
{

    // Stroring the max age of all
    // students + 1
    int mxage = *(std::max_element(
        age, age + n)) + 1;

    // Stroring the max candy + 1
    int mxcandy = *(std::max_element(
        candy, candy + k)) + 1;

    int fr1[mxage] = {0};
    int fr2[mxcandy] = {0};

    // Creating the frequency array of
    // the age of students
    for(int j = 0; j < n; j++)
    {
        fr1[age[j]] += 1;
    }

    // Creating the frequency array of the 
    // packets of candies
    for(int j = 0; j < k; j++)
    {
        fr2[candy[j]] += 1;
    }

    // Pointer to tell whether we have reached 
    // the end of candy frequency array
    k = 0;

    // Flag to tell if distribution
    // is possible or not
    bool Tf = true;
    for(int j = 0; j < mxage; j++)
    {
        if (fr1[j] == 0)
            continue;

        // Flag to tell if we can choose
        // some candy packets for the
        // students with age j
        bool flag = false;

        while (k < mxcandy)
        {

            // If the quantity of packets is
            // greater than or equal to the
            // number of students of age j,
            // then we can choose these 
            // packets for the students
            if (fr1[j] <= fr2[k])
            {
                flag = true;
                break;
            }
            k += 1;
        }

        // Start searching from k + 1
        // in next operation
        k = k + 1;

        // If we cannot choose any packets 
        // then the answer is NO
        if (flag == false)
        {
            Tf = false;
            break;
        }
    }

    if (Tf)
        cout << "YES" << endl;
    else
        cout << "NO" << endl;
}

// Driver code      
int main()
{
    int age[] = { 5, 15, 10 };
    int candy[] = { 2, 2, 2, 3, 3, 4 };

    int n = sizeof(age) / sizeof(age[0]);
    int k = sizeof(candy) / sizeof(candy[0]);

    check_distribution(n, k, age, candy);

    return 0;
}

// This code is contributed by divyeshrabadiya07
```

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java implementation of the approach
import java.util.*;

class Main
{
    // Function to check The validity of distribution
    public static void check_distribution(int n, int k,
                            int age[], int candy[])
    {

        // Stroring the max age of all
        // students + 1
        int mxage = age[0];
        for(int i = 0; i < age.length; i++)
        {
            if(mxage < age[i])
            {
                mxage = age[i];
            }
        }

        // Stroring the max candy + 1
        int mxcandy = candy[0];
        for(int i = 0; i < candy.length; i++)
        {
            if(mxcandy < candy[i])
            {
                mxcandy = candy[i];
            }
        }

        int fr1[] = new int[mxage + 1];
        Arrays.fill(fr1, 0);
        int fr2[] = new int[mxcandy + 1];
        Arrays.fill(fr2, 0);

        // Creating the frequency array of
        // the age of students
        for(int j = 0; j < n; j++)
        {
            fr1[age[j]] += 1;
        }

        // Creating the frequency array of the 
        // packets of candies
        for(int j = 0; j < k; j++)
        {
            fr2[candy[j]] += 1;
        }

        // Pointer to tell whether we have reached 
        // the end of candy frequency array
        k = 0;

        // Flag to tell if distribution
        // is possible or not
        boolean Tf = true;
        for(int j = 0; j < mxage; j++)
        {
            if (fr1[j] == 0)
                continue;

            // Flag to tell if we can choose
            // some candy packets for the
            // students with age j
            boolean flag = false;

            while (k < mxcandy)
            {

                // If the quantity of packets is
                // greater than or equal to the
                // number of students of age j,
                // then we can choose these 
                // packets for the students
                if (fr1[j] <= fr2[k])
                {
                    flag = true;
                    break;
                }
                k += 1;
            }

            // Start searching from k + 1
            // in next operation
            k = k + 1;

            // If we cannot choose any packets 
            // then the answer is NO
            if (flag == false)
            {
                Tf = false;
                break;
            }
        }

        if (Tf)
            System.out.println("YES");
        else
            System.out.println("NO");
    }

  // Driver code
  public static void main(String[] args)
  {
    int age[] = { 5, 15, 10 };
    int candy[] = { 2, 2, 2, 3, 3, 4 };
    int n = age.length;
    int k = candy.length;

    check_distribution(n, k, age, candy);
  }
}

// This code is contributed by divyesh072019
```

## 蟒蛇 3

```
# Python3 implementation of the approach

# Function to check The validity of distribution
def check_distribution(n, k, age, candy):

    # Stroring the max age of all students + 1
    mxage = max(age)+1

    # Stroring the max candy + 1
    mxcandy = max(candy)+1
    fr1 = [0] * mxage
    fr2 = [0] * mxcandy

    # creating the frequency array of the
    # age of students
    for j in range(n):
        fr1[age[j]] += 1

    # Creating the frequency array of the
    # packets of candies
    for j in range(k):
        fr2[candy[j]] += 1

    # pointer to tell whether we have reached
    # the end of candy frequency array
    k = 0

    # Flag to tell if distribution is possible or not
    Tf = True
    for j in range(mxage):
        if (fr1[j] == 0):
            continue

        # Flag to tell if we can choose some
        # candy packets for the students with age j
        flag = False
        while (k < mxcandy):

            # If the quantity of packets is greater 
            # than or equal to the number of students
            # of age j, then we can choose these
            # packets for the students
            if (fr1[j] <= fr2[k]):
                flag = True
                break
            k += 1

        # Start searching from k + 1 in next operation
        k = k + 1

        # If we cannot choose any packets
        # then the answer is NO
        if (flag == False):
            Tf = False
            break
    if (Tf):
        print("YES")
    else:
        print("NO")

# Driver code
age = [5, 15, 10]
candy = [2, 2, 2, 3, 3, 4]
n = len(age)
k = len(candy)
check_distribution(n, k, age, candy)
```

## C#

```
// C# implementation of the approach
using System.IO;
using System;
class GFG
{
    // Function to check The validity of distribution
    static void check_distribution(int n,int k,
                                   int[] age,int[] candy)
    {

        // Stroring the max age of all
        // students + 1
        int mxage = age[0];
        for(int i = 0; i < age.Length; i++)
        {
            if(mxage < age[i])
            {
                mxage = age[i];
            }
        }

        // Stroring the max candy + 1
        int mxcandy = candy[0];
        for(int i = 0; i < candy.Length; i++)
        {
            if(mxcandy < candy[i])
            {
                mxcandy = candy[i];
            }
        }

        int[] fr1 = new int[mxage + 1];
        Array.Fill(fr1, 0);
        int[] fr2 = new int[mxcandy + 1];
        Array.Fill(fr2, 0);

        // Creating the frequency array of
        // the age of students
        for(int j = 0; j < n; j++)
        {
            fr1[age[j]] += 1;
        }

        // Creating the frequency array of the 
        // packets of candies
        for(int j = 0; j < k; j++)
        {
            fr2[candy[j]] += 1;
        }

        // Pointer to tell whether we have reached 
        // the end of candy frequency array
        k = 0;

        // Flag to tell if distribution
        // is possible or not
        bool Tf = true;

        for(int j = 0; j < mxage; j++)
        {
            if(fr1[j] == 0)
            {
                continue;
            }

            // Flag to tell if we can choose
            // some candy packets for the
            // students with age j
            bool flag = false;

            while (k < mxcandy)
            {

                // If the quantity of packets is
                // greater than or equal to the
                // number of students of age j,
                // then we can choose these 
                // packets for the students
                if (fr1[j] <= fr2[k])
                {
                    flag = true;
                    break;
                }
                k += 1;
            }

            // Start searching from k + 1
            // in next operation
            k = k + 1;

            // If we cannot choose any packets 
            // then the answer is NO
            if (flag == false)
            {
                Tf = false;
                break;
            }

        }

        if(Tf)
        {
            Console.WriteLine("Yes");
        }
        else
        {
            Console.WriteLine("No");
        }

    }

    // Driver code
    static void Main()
    {
        int[] age = {5, 15, 10};
        int[] candy = { 2, 2, 2, 3, 3, 4 };
        int n = age.Length;
        int k = candy.Length;

        check_distribution(n, k, age, candy);
    }
}

// This code is contributed by avanitrachhadiya2155
```

## java 描述语言

```
<script>
    // Javascript implementation of the approach

    // Function to check The validity of distribution
    function check_distribution(n, k, age, candy)
    {

        // Stroring the max age of all
        // students + 1
        let mxage = age[0];
        for(let i = 0; i < age.length; i++)
        {
            if(mxage < age[i])
            {
                mxage = age[i];
            }
        }

        // Stroring the max candy + 1
        let mxcandy = candy[0];
        for(let i = 0; i < candy.length; i++)
        {
            if(mxcandy < candy[i])
            {
                mxcandy = candy[i];
            }
        }

        let fr1 = new Array(mxage + 1);
        fr1.fill(0);
        let fr2 = new Array(mxcandy + 1);
        fr2.fill(0);

        // Creating the frequency array of
        // the age of students
        for(let j = 0; j < n; j++)
        {
            fr1[age[j]] += 1;
        }

        // Creating the frequency array of the
        // packets of candies
        for(let j = 0; j < k; j++)
        {
            fr2[candy[j]] += 1;
        }

        // Pointer to tell whether we have reached
        // the end of candy frequency array
        k = 0;

        // Flag to tell if distribution
        // is possible or not
        let Tf = true;

        for(let j = 0; j < mxage; j++)
        {
            if(fr1[j] == 0)
            {
                continue;
            }

            // Flag to tell if we can choose
            // some candy packets for the
            // students with age j
            let flag = false;

            while (k < mxcandy)
            {

                // If the quantity of packets is
                // greater than or equal to the
                // number of students of age j,
                // then we can choose these
                // packets for the students
                if (fr1[j] <= fr2[k])
                {
                    flag = true;
                    break;
                }
                k += 1;
            }

            // Start searching from k + 1
            // in next operation
            k = k + 1;

            // If we cannot choose any packets
            // then the answer is NO
            if (flag == false)
            {
                Tf = false;
                break;
            }

        }

        if(Tf)
        {
            document.write("YES");
        }
        else
        {
            document.write("NO");
        }

    }

    let age = [5, 15, 10];
    let candy = [ 2, 2, 2, 3, 3, 4 ];
    let n = age.length;
    let k = candy.length;

    check_distribution(n, k, age, candy);

    // This code is contributed by suresh07.
</script>
```

**Output:** 

```
YES
```