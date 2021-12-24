# 使用 Python 加密和解密图像

> 原文:[https://www . geesforgeks . org/encrypt-and-decrypt-image-use-python/](https://www.geeksforgeeks.org/encrypt-and-decrypt-image-using-python/)

在本文中，我们将使用简单的数学逻辑对图像进行加密/解密。它需要两样东西，数据和密钥，当对两个操作数(即数据和密钥)进行异或运算时，数据被加密，但是当用相同的密钥值再次进行相同的处理时，数据被解密。

### **加密**

这只不过是一个简单的过程，在这个过程中，我们将我们的数据或信息转换成秘密代码，以防止未经授权的访问，并保持其私密性和安全性。

首先，我们将选择一个图像，然后我们将该图像转换为字节数组，由于该字节数组，图像数据将完全转换为数字形式，然后我们可以轻松地对其应用异或运算。现在，每当我们对字节数组的每个值应用异或函数时，数据就会改变，因此我们将无法访问它。但是我们应该记住一件事，在这里我们的加密密钥起着非常重要的作用，没有那个密钥，我们无法解密我们的图像。它充当密码来解密它。

**下面的程序描述了加密的基本方法:**

## 蟒蛇 3

```py
# Assign values
data = 1281
key = 27

# Display values
print('Original Data:', data)
print('Key:', key)

# Encryption
data = data ^ key
print('After Encryption:', data)

# Decryption
data = data ^ key
print('After Decryption:', data)
```

**输出:**

```py
Original Data: 1281
Key: 27
After Encryption: 1306
After Decryption: 1281
```

在上面的程序中，我们可以看到异或运算是如何工作的，每当我们第一次对两个变量*数据*和*密钥*进行异或运算时，我们都会得到加密数据。然后当我们再次对我们的*数据*和*键*进行异或运算时，我们得到与我们的输入变量*数据*相同的值(解密数据)。在加密和解密期间，相同的逻辑将适用于图像的字节数组。

**加密的可执行代码:**

## 蟒蛇 3

```py
# try block to handle exception
try:
    # take path of image as a input
    path = input(r'Enter path of Image : ')

    # taking encryption key as input
    key = int(input('Enter Key for encryption of Image : '))

    # print path of image file and encryption key that
    # we are using
    print('The path of file : ', path)
    print('Key for encryption : ', key)

    # open file for reading purpose
    fin = open(path, 'rb')

    # storing image data in variable "image"
    image = fin.read()
    fin.close()

    # converting image into byte array to
    # perform encryption easily on numeric data
    image = bytearray(image)

    # performing XOR operation on each value of bytearray
    for index, values in enumerate(image):
        image[index] = values ^ key

    # opening file for writing purpose
    fin = open(path, 'wb')

    # writing encrypted data in image
    fin.write(image)
    fin.close()
    print('Encryption Done...')

except Exception:
    print('Error caught : ', Exception.__name__)
```

**输出:**

```py
Enter path of Image : C:\Users\lenovo\Pictures\Instagram\enc.png
Enter Key for encryption of Image : 22
The path of file :  C:\Users\lenovo\Pictures\Instagram\enc.png
Key for encryption :  22
Encryption done...
```

在上面的代码中，我们首先将图像和加密密钥的路径作为用户的输入，然后使用文件处理概念来处理二进制文件并打开该文件进行读取，然后读取图像的二进制数据并将其存储在*图像*变量中。现在我们将二进制形式的数据转换成字节数组，然后对字节数组的每个值进行异或运算，这将改变数据，因此我们将无法打开图像。

### [通信]解密

它只不过是将我们的加密数据转换成可读形式的过程。在这里，我们将再次对加密的图像应用相同的异或运算来解密它。但请始终记住，我们的加密密钥和解密密钥必须相同。

**解密可执行代码:**

## 蟒蛇 3

```py
# try block to handle the exception
try:
    # take path of image as a input
    path = input(r'Enter path of Image : ')

    # taking decryption key as input
    key = int(input('Enter Key for encryption of Image : '))

    # print path of image file and decryption key that we are using
    print('The path of file : ', path)
    print('Note : Encryption key and Decryption key must be same.')
    print('Key for Decryption : ', key)

    # open file for reading purpose
    fin = open(path, 'rb')

    # storing image data in variable "image"
    image = fin.read()
    fin.close()

    # converting image into byte array to perform decryption easily on numeric data
    image = bytearray(image)

    # performing XOR operation on each value of bytearray
    for index, values in enumerate(image):
        image[index] = values ^ key

    # opening file for writing purpose
    fin = open(path, 'wb')

    # writing decryption data in image
    fin.write(image)
    fin.close()
    print('Decryption Done...')

except Exception:
    print('Error caught : ', Exception.__name__)
```

**输出:**

```py
Enter path of Image : C:\Users\lenovo\Pictures\Instagram\enc.png
Enter Key for Decryption of Image : 22
The path of file :  C:\Users\lenovo\Pictures\Instagram\enc.png
Note : Encryption key and Decryption key must be same.
Key for Decryption :  22
Decryption done...
```

在上面的解密程序中，我们使用了与图像加密相同的过程。'

**下面是使用给定图像和按键描述上述程序功能的视频。**

<video class="wp-video-shortcode" id="video-500953-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20201013225712/video-20201013-223339_XTxPBdfH.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20201013225712/video-20201013-223339_XTxPBdfH.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20201013225712/video-20201013-223339_XTxPBdfH.mp4)</video>