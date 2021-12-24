# 使用 Python 合并远程服务器中存储的 PDF

> 原文:[https://www . geesforgeks . org/merge-pdf-stored-in-remote-server-use-python/](https://www.geeksforgeeks.org/merge-pdf-stored-in-remote-server-using-python/)

**先决条件:** [使用 Python 中的 PDF 文件](https://www.geeksforgeeks.org/working-with-pdf-files-in-python/)

在 Python 中有许多用于操作 PDF 文件的库，但是当所有的 PDF 文件已经下载到您的本地机器上时，所有的库都在使用。但是如果你的目标 PDF **文件在远程服务器**中，你的机器或计算服务器中只有文件的网址**而没有必需的下载**怎么办。在这里我们将同样讨论这个问题和解决方案。

**安装:**
这里我们使用 Python PyPDF2 的库来合并 PDF。

```
pip install PyPDF2
```

我们将合并同一个 pdf 文件两次。使用的 pdf 文件的链接是[这里是](http://www.africau.edu/images/default/sample.pdf)

下面是实现。

```
from io import BytesIO, SEEK_SET, SEEK_END
import PyPDF2 
import requests

# Create a class which convert PDF in
# BytesIO form
class ResponseStream(object):

    def __init__(self, request_iterator):
        self._bytes = BytesIO()
        self._iterator = request_iterator

    def _load_all(self):
        self._bytes.seek(0, SEEK_END)

        for chunk in self._iterator:
            self._bytes.write(chunk)

    def _load_until(self, goal_position):
        current_position = self._bytes.seek(0, SEEK_END)

        while current_position < goal_position:
            try:
                current_position = self._bytes.write(next(self._iterator))

            except StopIteration:
                break

    def tell(self):
        return self._bytes.tell()

    def read(self, size = None):
        left_off_at = self._bytes.tell()

        if size is None:
            self._load_all()
        else:
            goal_position = left_off_at + size
            self._load_until(goal_position)

        self._bytes.seek(left_off_at)

        return self._bytes.read(size)

    def seek(self, position, whence = SEEK_SET):

        if whence == SEEK_END:
            self._load_all()
        else:
            self._bytes.seek(position, whence)

# Merge PDFs using URL List
url_list = ["lis of URL"]
target_pdf_path = './Merged.pdf'
pdf_writer = PyPDF2.PdfFileWriter()

for url in url_list:

    response = requests.get(url)
    reader = PyPDF2.PdfFileReader(ResponseStream(response.iter_content(64)))

    for page in range(reader.getNumPages()):
        pdf_writer.addPage(reader.getPage(page))

# write to output file
with open(target_pdf_path, 'wb') as g:
    pdf_writer.write(g)
```

**输出:**

创建的合并 pdf 文件在这里是