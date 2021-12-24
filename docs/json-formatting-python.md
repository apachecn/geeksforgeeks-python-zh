# Python 中的 JSON 格式

> 原文:[https://www.geeksforgeeks.org/json-formatting-python/](https://www.geeksforgeeks.org/json-formatting-python/)

缩写为 JSON 的 Javascript 对象符号是一种轻量级的数据交换格式。它将 Python 对象编码为 JSON 字符串，并将 JSON 字符串解码为 Python 对象。

*   许多像 [Github](https://developer.github.com/v3/#schema) 这样的 API。以这种格式发送他们的结果。在 AJAX 应用程序中，JSON 可能最广泛地用于网络服务器和客户端之间的通信，但不限于这个问题领域。
*   例如，如果您试图构建一个像[这样令人兴奋的项目](https://www.geeksforgeeks.org/building-a-terminal-based-online-dictionary-with-python-and-bash/)，我们需要格式化 JSON 输出以呈现必要的结果。因此，让我们深入到 Python 为格式化 json 输出而提供的 **json** 模块。

**功能**

*   **json.dump(obj，fileObj)** :将 *obj* 作为 json 格式的流序列化为 *fileObj* 。*   **json.dumps(obj)** :将 *obj* 序列化为 json 格式的字符串。*   **json.load(JSONfile)** :将 *JSONfile* 反序列化为 Python 对象。*   **json.loads(JSONfile)** : De-serializes *JSONfile*(type: string) to a Python object.

    **类**

    *   **JSONEncoder:** 一个将 Python 对象转换为 JSON 格式的编码器类。*   **JSONDecoder:** A decoder class to convert JSON format file into Python obj.

    转换基于此[转换表](https://docs.python.org/3/library/json.html#json-to-py-table)。

     **实施**

    **编码**
    我们将使用 dump()、dump()和 JSON。编码器类。

    ```
    #Code will run in Python 3

    from io import StringIO
    import json

    fileObj = StringIO()
    json.dump(["Hello", "Geeks"], fileObj)
    print("Using json.dump(): "+str(fileObj.getvalue()))

    class TypeEncoder(json.JSONEncoder):
        def default(self, obj):
            if isinstance(obj, type):
                return str(obj)

    print("Using json.dumps(): "+str(json.dumps(type(str), cls=TypeEncoder)))
    print("Using json.JSONEncoder().encode"+
          str(TypeEncoder().encode(type(list))))
    print("Using json.JSONEncoder().iterencode"+
          str(list(TypeEncoder().iterencode(type(dict)))))
    ```

    输出:

    ```
    Using json.dump(): ["Hello", "Geeks"]
    Using json.dumps(): ""
    Using json.JSONEncoder().encode"<class>"
    Using json.JSONEncoder().iterencode['"<class>"']</class></class> 
    ```

    **解码**
    我们将使用 load()，loads()和 JSON。解码器类。

    ```
    #Code will run in Python 3

    from io import StringIO
    import json

    fileObj = StringIO('["Geeks for Geeks"]')
    print("Using json.load(): "+str(json.load(fileObj)))
    print("Using json.loads(): "+str(json.loads('{"Geeks": 1, "for": 2, "Geeks": 3}')))
    print("Using json.JSONDecoder().decode(): " +
        str(json.JSONDecoder().decode('{"Geeks": 1, "for": 2, "Geeks": 3}')))
    print("Using json.JSONDecoder().raw_decode(): " +
        str(json.JSONDecoder().raw_decode('{"Geeks": 1, "for": 2, "Geeks": 3}')))
    ```

    输出:

    ```
    Using json.load(): ['Geeks for Geeks']
    Using json.loads(): {'for': 2, 'Geeks': 3}
    Using json.JSONDecoder().decode(): {'for': 2, 'Geeks': 3}
    Using json.JSONDecoder().raw_decode(): ({'for': 2, 'Geeks': 3}, 34)

    ```

    **参考:**

    *   [https://docs.python.org/3/library/json.html](https://docs.python.org/3/library/json.html)

    本文由**斯里·桑凯·乌帕拉帕蒂**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

    如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。