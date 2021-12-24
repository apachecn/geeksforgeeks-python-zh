# 如何用 Python 打印上标和下标？

> 原文:[https://www . geesforgeks . org/如何用 python 打印上标和下标/](https://www.geeksforgeeks.org/how-to-print-superscript-and-subscript-in-python/)

每当我们使用公式时，可能需要以给定的格式编写给定的公式，这可能需要下标或上标。Python 中有几种方法可以打印下标和上标。我们将在下面讨论其中的两个–

**使用 maketrans()和 translate() :**

我们可以制作两个字符串，一个用于普通字符，另一个用于下标/上标字符。之后，我们可以使用 **maketrans()** 方法返回一个映射，该映射可以与 **translate()** 方法一起使用来替换指定的字符。它可以为上标实现为

## 蟒蛇 3

```py
# function to convert to superscript
def get_super(x):
    normal = "ABCDEFGHIJKLMNOPQRSTUVWXYZabcdefghijklmnopqrstuvwxyz0123456789+-=()"
    super_s = "ᴬᴮᶜᴰᴱᶠᴳᴴᴵᴶᴷᴸᴹᴺᴼᴾQᴿˢᵀᵁⱽᵂˣʸᶻᵃᵇᶜᵈᵉᶠᵍʰᶦʲᵏˡᵐⁿᵒᵖ۹ʳˢᵗᵘᵛʷˣʸᶻ⁰¹²³⁴⁵⁶⁷⁸⁹⁺⁻⁼⁽⁾"
    res = x.maketrans(''.join(normal), ''.join(super_s))
    return x.translate(res)

# display superscipt
print(get_super('GeeksforGeeks')) #ᴳᵉᵉᵏˢᶠᵒʳᴳᵉᵉᵏˢ
```

**输出:**

```py
ᴳᵉᵉᵏˢᶠᵒʳᴳᵉᵉᵏˢ
```

对于下标，我们可以将其实现为

## Python3

```py
# function to convert to subscript
def get_sub(x):
    normal = "ABCDEFGHIJKLMNOPQRSTUVWXYZabcdefghijklmnopqrstuvwxyz0123456789+-=()"
    sub_s = "ₐ₈CDₑբGₕᵢⱼₖₗₘₙₒₚQᵣₛₜᵤᵥwₓᵧZₐ♭꜀ᑯₑբ₉ₕᵢⱼₖₗₘₙₒₚ૧ᵣₛₜᵤᵥwₓᵧ₂₀₁₂₃₄₅₆₇₈₉₊₋₌₍₎"
    res = x.maketrans(''.join(normal), ''.join(sub_s))
    return x.translate(res)

# display subscript
print('H{}SO{}'.format(get_sub('2'),get_sub('4'))) #H₂SO₄
```

**输出:**

```py
H₂SO₄
```

**使用 Unicode 下标和上标:**

下表给出了 Unicode 字符的下标和上标:

<figure class="table">

|   | Zero | one | Two | three | four | five | six | seven | eight | nine | A | B | C | D | E | F |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| U+207x | *本文件迟交 | -好的 |   |   | ㈧ | ㈨ | (一) | -你好 | 我是说... | (三) | 我是说... | *本文件迟交 | ⁼ | ⊿岿 | ⁾ | 你是谁 |
| U+208x | ₀ | ₁ | ₂ | ⊿岿 | (二) | ₅ | ₆ | ₇ | ₈ | ₉ | *本文件迟交 | ₋ | ₌ | (三) | 我是说... |   |
| U+209x | ₐ | ₑ | ₒ | ₓ | ₔ | ₕ | 自 | ₗ | ₘ | ₙ | -是吗 | ₛ | ⊿岿⊿⊿⊿⊿⊿⊿⊿⊿⊿τ |   |   |   |

</figure>

在 Unicode 字符的帮助下，我们可以在代码中实现这一点，如–

## 蟒蛇 3

```py
# subscript
print(u'H\u2082SO\u2084')  # H₂SO₄

# superscript
print("x\u00b2 + y\u00b2 = 2")  # x² + y² = 2
```

**输出:**

```py
H₂SO₄
x² + y² = 2
```