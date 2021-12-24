# 使用 Python 实现校验和

> 原文:[https://www . geesforgeks . org/impering-checksum-use-python/](https://www.geeksforgeeks.org/implementing-checksum-using-python/)

**校验和**是计算机网络中的一种错误检测方法。该方法由较高层协议使用，并在发送端使用校验和生成器，在接收端使用校验和检查器。在本文中，我们将在 Python 中实现校验和算法。

> **参考以下文章，获取校验和**的详细信息
> 
> *   [<u>计算机网络中的错误检测</u>](https://www.geeksforgeeks.org/error-detection-in-computer-networks/)
> *   [<u>错误检测代码–校验和</u>](https://www.geeksforgeeks.org/error-detection-code-checksum/)

实现算法的步骤。

#### **步骤 1:** 生成校验和(发送方)

1.  该消息分为 4 个部分，每个部分由 k 位组成。
2.  所有的部分加在一起得到总和。
3.  总和被补充并成为校验和。
4.  校验和与数据一起发送。

#### **步骤 2:** 校验和检查器(接收端)

1.  消息被分成 4 段 k 位。
2.  所有的部分加在一起得到总和。
3.  生成的校验和被添加到所有部分的总和中。
4.  所得到的和是互补的。

遵循这些步骤后，如果结果等于零，则数据是正确的，因此被接受。否则，检测到错误并拒绝数据。

**以下是上述方法的实现:**

## 蟒蛇 3

```py
# Function to find the Checksum of Sent Message
def findChecksum(SentMessage, k):

    # Dividing sent message in packets of k bits.
    c1 = SentMessage[0:k]
    c2 = SentMessage[k:2*k]
    c3 = SentMessage[2*k:3*k]
    c4 = SentMessage[3*k:4*k]

    # Calculating the binary sum of packets
    Sum = bin(int(c1, 2)+int(c2, 2)+int(c3, 2)+int(c4, 2))[2:]

    # Adding the overflow bits
    if(len(Sum) > k):
        x = len(Sum)-k
        Sum = bin(int(Sum[0:x], 2)+int(Sum[x:], 2))[2:]
    if(len(Sum) < k):
        Sum = '0'*(k-len(Sum))+Sum

    # Calculating the complement of sum
    Checksum = ''
    for i in Sum:
        if(i == '1'):
            Checksum += '0'
        else:
            Checksum += '1'
    return Checksum

# Function to find the Complement of binary addition of
# k bit packets of the Received Message + Checksum
def checkReceiverChecksum(ReceivedMessage, k, Checksum):

    # Dividing sent message in packets of k bits.
    c1 = ReceivedMessage[0:k]
    c2 = ReceivedMessage[k:2*k]
    c3 = ReceivedMessage[2*k:3*k]
    c4 = ReceivedMessage[3*k:4*k]

    # Calculating the binary sum of packets + checksum
    ReceiverSum = bin(int(c1, 2)+int(c2, 2)+int(Checksum, 2) +
                      int(c3, 2)+int(c4, 2)+int(Checksum, 2))[2:]

    # Adding the overflow bits
    if(len(ReceiverSum) > k):
        x = len(ReceiverSum)-k
        ReceiverSum = bin(int(ReceiverSum[0:x], 2)+int(ReceiverSum[x:], 2))[2:]

    # Calculating the complement of sum
    ReceiverChecksum = ''
    for i in ReceiverSum:
        if(i == '1'):
            ReceiverChecksum += '0'
        else:
            ReceiverChecksum += '1'
    return ReceiverChecksum

# Driver Code
SentMessage = "10010101011000111001010011101100"
k = 8
ReceivedMessage = "10000101011000111001010011101101"

# Calling the findChecksum() function
Checksum = findChecksum(SentMessage, k)

# Calling thr checkReceiverChecksum() function
ReceiverChecksum = checkReceiverChecksum(ReceivedMessage, k, Checksum)

# Printing Checksum
print("SENDER SIDE CHECKSUM: ", Checksum)
print("RECEIVER SIDE CHECKSUM: ", ReceiverChecksum)

# If sum = 0, No error is detected
if(int(ReceiverChecksum, 2) == 0):
    print("Receiver Checksum is equal to 0\. Therefore,")
    print("STATUS: ACCEPTED")

# Otherwise, Error is detected
else:
    print("Receiver Checksum is not equal to 0\. Therefore,")
    print("STATUS: ERROR DETECTED")
```

**输出:**

```py
SENDER SIDE CHECKSUM:  10000101
RECEIVER SIDE CHECKSUM:  0001001
Receiver Checksum is not equal to 0\. Therefore,
STATUS: ERROR DETECTED
```