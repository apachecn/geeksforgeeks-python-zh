# Python |使用 pyfiglet 模块的 ASCII 艺术

> 原文:[https://www . geesforgeks . org/python-ascii-art-using-pyfiglet-module/](https://www.geeksforgeeks.org/python-ascii-art-using-pyfiglet-module/)

**pyfiglet** 采用 ASCII 文本，并以 ASCII 艺术字体渲染。`figlet_format` 方法将 ASCII 文本转换为 ASCII 艺术字体。

它需要以下参数:

```
text
font ( DEFAULT_FONT = 'standard' )
```

安装 pyfiglet 模块的命令:

```
pip install pyfiglet
```

**代码#1:** 默认字体文本

```
# import pyfiglet module
import pyfiglet

result = pyfiglet.figlet_format("Geeks For Geeks")
print(result)
```

**输出:**

```
  ____           _          _____             ____           _        
 / ___| ___  ___| | _____  |  ___|__  _ __   / ___| ___  ___| | _____ 
| |  _ / _ \/ _ \ |/ / __| | |_ / _ \| '__| | |  _ / _ \/ _ \ |/ / __|
| |_| |  __/  __/      \__ \ |  _| (_) | |    | |_| |  __/  __/      \__ \
 \____|\___|\___|_|\_\___/ |_|  \___/|_|     \____|\___|\___|_|\_\___/

```

**代码#2:** 倾斜字体文本

```
# import pyfiglet module
import pyfiglet

result = pyfiglet.figlet_format("Geeks For Geeks", font = "slant"  )
print(result)
```

**输出:**

```
   ______          __           ______              ______          __       
  / ____/__  ___  / /_______   / ____/___  _____   / ____/__  ___  / /_______
 / / __/ _ \/ _ \/ //_/ ___/  / /_  / __ \/ ___/  / / __/ _ \/ _ \/ //_/ ___/
/ /_/ /  __/  __/      (__  )  / __/ / /_/ / /     / /_/ /  __/  __/    (__  ) 
\____/\___/\___/_/|_/____/  /_/    \____/_/      \____/\___/\___/_/|_/____/  

```

**代码#3:** 三维字体文本

```
# import pyfiglet module
import pyfiglet

result = pyfiglet.figlet_format("G e e k", font = "3-d" )
print(result)
```

**输出:**

```
   ********                        **    
  **//////**                      /**    
 **      //     *****     *****   /**  **
/**            **///**   **///**  /** ** 
/**    *****  /*******  /*******  /****  
//**  ////**  /**////   /**////   /**/** 
 //********   //******  //******  /**//**
  ////////     //////    //////   //  //    

```

**代码# 4:**3×5 字体文本

```
# importing pyfiglet module
import pyfiglet

result = pyfiglet.figlet_format("G e e k", font = "3x5" )
print(result)
```

**输出:**

```

 ##                     #   
#       ###     ###     # # 
# #     ##      ##      ##  
# #     ###     ###     # # 
 ##                         

```

**代码# 5:**5 线斜字体文本

```
# import pyfiglet module
import pyfiglet

result = pyfiglet.figlet_format("G e e k", font = "5lineoblique" )
print(result)
```

**输出:**

```

    //   ) )                                       
   //              ___          ___         / ___  
  //  ____       //___) )     //___) )     //\ \   
 //    / /      //           //           //  \ \  
((____/ /      ((____       ((____       //    \ \   

```

**代码 6:** 字母字体文字

```
# import pyfiglet module
import pyfiglet

result = pyfiglet.figlet_format("G e e k", font = "alphabet" )
print(result)
```

**输出:**

```
 GGG             k    
G                k k  
G  GG  eee  eee  kk   
G   G  e e  e e  k k  
 GGG   ee   ee   k  k 

```

**代码# 7:**3-D 字体文本

```
# import pyfiglet module
import pyfiglet

result = pyfiglet.figlet_format("Geeks", font = "banner3-D" )
print(result)
```

**输出:**

```
:'######:::'########:'########:'##:::'##::'######::
'##... ##:: ##.....:: ##.....:: ##::'##::'##... ##:
 ##:::..::: ##::::::: ##::::::: ##:'##::: ##:::..::
 ##::'####: ######::: ######::: #####::::. ######::
 ##::: ##:: ##...:::: ##...:::: ##. ##::::..... ##:
 ##::: ##:: ##::::::: ##::::::: ##:. ##::'##::: ##:
. ######::: ########: ########: ##::. ##:. ######::
:......::::........::........::..::::..:::......::: 
```

**代码# 8:**doh 字体文本

```
# import pyfiglet module
import pyfiglet

result = pyfiglet.figlet_format("Geeks", font = "doh" )
print(result)
```

**输出:**

```

        GGGGGGGGGGGGG                                       kkkkkkkk           
     GGG::::::::::::G                                       k::::::k           
   GG:::::::::::::::G                                       k::::::k           
  G:::::GGGGGGGG::::G                                       k::::::k           
 G:::::G       GGGGGG    eeeeeeeeeeee        eeeeeeeeeeee    k:::::k    kkkkkkk
G:::::G                ee::::::::::::ee    ee::::::::::::ee  k:::::k   k:::::k 
G:::::G               e::::::eeeee:::::ee e::::::eeeee:::::eek:::::k  k:::::k  
G:::::G    GGGGGGGGGGe::::::e     e:::::ee::::::e     e:::::ek:::::k k:::::k   
G:::::G    G::::::::Ge:::::::eeeee::::::ee:::::::eeeee::::::ek::::::k:::::k    
G:::::G    GGGGG::::Ge:::::::::::::::::e e:::::::::::::::::e k:::::::::::k     
G:::::G        G::::Ge::::::eeeeeeeeeee  e::::::eeeeeeeeeee  k:::::::::::k     
 G:::::G       G::::Ge:::::::e           e:::::::e           k::::::k:::::k    
  G:::::GGGGGGGG::::Ge::::::::e          e::::::::e         k::::::k k:::::k   
   GG:::::::::::::::G e::::::::eeeeeeee   e::::::::eeeeeeee k::::::k  k:::::k  
     GGG::::::GGG:::G  ee:::::::::::::e    ee:::::::::::::e k::::::k   k:::::k 
        GGGGGG   GGGG    eeeeeeeeeeeeee      eeeeeeeeeeeeee kkkkkkkk    kkkkkkk           

```

**代码#9:** 等距 1 字体文本

```
# import pyfiglet module
import pyfiglet

result = pyfiglet.figlet_format("Geeks", font = "isometric1" )
print(result)
```

**输出:**

```

      ___           ___           ___           ___           ___     
     /\  \         /\  \         /\  \         /\__\         /\  \    
    /::\  \       /::\  \       /::\  \       /:/  /        /::\  \   
   /:/\:\  \     /:/\:\  \     /:/\:\  \     /:/__/        /:/\ \  \  
  /:/  \:\  \   /::\~\:\  \   /::\~\:\  \   /::\__\____   _\:\~\ \  \ 
 /:/__/_\:\__\ /:/\:\ \:\__\ /:/\:\ \:\__\ /:/\:::::\__\ /\ \:\ \ \__\
 \:\  /\ \/__/ \:\~\:\ \/__/ \:\~\:\ \/__/ \/_|:|~~|~    \:\ \:\ \/__/
  \:\ \:\__\    \:\ \:\__\    \:\ \:\__\      |:|  |      \:\ \:\__\  
   \:\/:/  /     \:\ \/__/     \:\ \/__/      |:|  |       \:\/:/  /  
    \::/  /       \:\__\        \:\__\        |:|  |        \::/  /   
     \/__/         \/__/         \/__/         \|__|         \/__/    

```

**代码#10:** 字母字体文本

```
# import pyfiglet module
import pyfiglet

result = pyfiglet.figlet_format("Geeks", font = "letters" )
print(result)
```

**输出:**

```
  GGGG                kk           
 GG  GG   eee    eee  kk  kk  sss  
GG      ee   e ee   e kkkkk  s     
GG   GG eeeee  eeeee  kk kk   sss  
 GGGGGG  eeeee  eeeee kk  kk     s 
                              sss  

```

**代码#11:** 鳄鱼字体文本

```
# import pyfiglet module
import pyfiglet

result = pyfiglet.figlet_format("G e e k", font = "alligator" )
print(result)
```

**输出:**

```
      ::::::::        ::::::::::        ::::::::::        :::    ::: 
    :+:    :+:       :+:               :+:               :+:   :+:   
   +:+              +:+               +:+               +:+  +:+     
  :#:              +#++:++#          +#++:++#          +#++:++       
 +#+   +#+#       +#+               +#+               +#+  +#+       
#+#    #+#       #+#               #+#               #+#   #+#       
########        ##########        ##########        ###    ###       

```

**代码#12:** 点阵字体文本

```
# import pyfiglet module
import pyfiglet

result = pyfiglet.figlet_format("Geeks", font = "dotmatrix" )
print(result)
```

**输出:**

```
    _  _  _                                   _                         
 _ (_)(_)(_) _                               (_)                        
(_)         (_)  _  _  _  _     _  _  _  _   (_)     _   _  _  _  _     
(_)    _  _  _  (_)(_)(_)(_)_  (_)(_)(_)(_)_ (_)   _(_)_(_)(_)(_)(_)    
(_)   (_)(_)(_)(_) _  _  _ (_)(_) _  _  _ (_)(_) _(_) (_)_  _  _  _     
(_)         (_)(_)(_)(_)(_)(_)(_)(_)(_)(_)(_)(_)(_)_    (_)(_)(_)(_)_   
(_) _  _  _ (_)(_)_  _  _  _  (_)_  _  _  _  (_)  (_)_   _  _  _  _(_)  
   (_)(_)(_)(_)  (_)(_)(_)(_)   (_)(_)(_)(_) (_)    (_) (_)(_)(_)(_)    

```

**代码#13:** 泡泡字体文本

```
# import pyfiglet module
import pyfiglet

result = pyfiglet.figlet_format("Geeks For Geeks", font = "bubble" )
print(result)
```

**输出:**

```
  _   _   _   _   _     _   _   _     _   _   _   _   _  
 / \ / \ / \ / \ / \   / \ / \ / \   / \ / \ / \ / \ / \ 
( G | e | e | k | s ) ( F | o | r ) ( G | e | e | k | s )
 \_/ \_/ \_/ \_/ \_/   \_/ \_/ \_/   \_/ \_/ \_/ \_/ \_/ 

```

**代码#14:** 泡泡字体文本

```
# import pyfiglet module
import pyfiglet

result = pyfiglet.figlet_format("Geeks For Geeks", font = "bulbhead" )
print(result)
```

**输出:**

```
  ___  ____  ____  _  _  ___    ____  _____  ____ 
 / __)( ___)( ___)( )/ )/ __)  ( ___)(  _  )(  _ \
( (_-. )__)  )__)  )  ( \__ \   )__)  )(_)(  )   /
 \___/(____)(____)(_)\_)(___/  (__)  (_____)(_)\_)
  ___  ____  ____  _  _  ___ 
 / __)( ___)( ___)( )/ )/ __)
( (_-. )__)  )__)  )  ( \__ \
 \___/(____)(____)(_)\_)(___/

```

**代码#15:** 数字字体文本

```
# import pyfiglet module
import pyfiglet

result = pyfiglet.figlet_format("Geeks For Geeks", font = "digital" )
print(result)
```

**输出:**

```
+-+-+-+-+-+ +-+-+-+ +-+-+-+-+-+
|G|e|e|k|s| |F|o|r| |G|e|e|k|s|
+-+-+-+-+-+ +-+-+-+ +-+-+-+-+-+

```