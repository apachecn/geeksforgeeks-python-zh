# 使用 Tkinter

制作记事本

> 原文:[https://www.geeksforgeeks.org/make-notepad-using-tkinter/](https://www.geeksforgeeks.org/make-notepad-using-tkinter/)

让我们看看如何使用 Tkinter 在 Python 中创建一个简单的记事本。这个记事本图形用户界面将包括各种菜单，如文件和编辑，使用它可以完成所有功能，如保存文件，打开文件，编辑，剪切和粘贴。

现在为了创建这个记事本，Python 3 和 Tkinter 应该已经安装在您的系统中了。可以根据系统需求下载合适的 [python 包](https://www.python.org/downloads/)。成功安装 python 后，您需要安装 Tkinter(Python 的图形用户界面包)。

**使用此命令安装 Tkinter :**

```
pip install python-tk
```

**导入 Tkinter :**

## 计算机编程语言

```
import tkinter
import os
from tkinter import *

# To get the space above for message
from tkinter.messagebox import *

# To get the dialog box to open when required
from tkinter.filedialog import *
```

**注意:** *消息框*用于将消息写在名为记事本的白色框中，*文件对话框*用于当您从系统中的任何位置打开文件或将文件保存在特定位置或地方时，对话框出现。

**添加菜单:**

## 计算机编程语言

```
# Add controls(widget)

self.__thisTextArea.grid(sticky = N + E + S + W)

# To open new file
self.__thisFileMenu.add_command(label = "New",
                                command = self.__newFile)

# To open a already existing file
self.__thisFileMenu.add_command(label = "Open",
                                command = self.__openFile)

# To save current file
self.__thisFileMenu.add_command(label = "Save",
                                command = self.__saveFile)

# To create a line in the dialog
self.__thisFileMenu.add_separator()

# To terminate
self.__thisFileMenu.add_command(label = "Exit",
                                command = self.__quitApplication)
self.__thisMenuBar.add_cascade(label = "File",
                               menu = self.__thisFileMenu)

# To give a feature of cut
self.__thisEditMenu.add_command(label = "Cut",
                                command = self.__cut)

# To give a feature of copy
self.__thisEditMenu.add_command(label = "Copy",
                                command = self.__copy)

# To give a feature of paste
self.__thisEditMenu.add_command(label = "Paste",
                                command = self.__paste)

# To give a feature of editing
self.__thisMenuBar.add_cascade(label = "Edit",
                               menu = self.__thisEditMenu)

# To create a feature of description of the notepad
self.__thisHelpMenu.add_command(label = "About Notepad",
                                command = self.__showAbout)
self.__thisMenuBar.add_cascade(label = "Help",
                               menu = self.__thisHelpMenu)

self.__root.config(menu = self.__thisMenuBar)

self.__thisScrollBar.pack(side = RIGHT, fill = Y)

# Scrollbar will adjust automatically
# according to the content
self.__thisScrollBar.config(command = self.__thisTextArea.yview)
self.__thisTextArea.config(yscrollcommand = self.__thisScrollBar.set)
```

有了这段代码，我们将在记事本的窗口中添加菜单，并将复制、粘贴、保存等操作添加到其中。

**增加功能:**

## 计算机编程语言

```
def __quitApplication(self):
    self.__root.destroy()
    # exit()

def __showAbout(self):
    showinfo("Notepad", "Mrinal Verma")

def __openFile(self):

    self.__file = askopenfilename(defaultextension=".txt",
                                  filetypes=[("All Files","*.*"),
                                      ("Text Documents","*.txt")])

    if self.__file == "":

        # no file to open
        self.__file = None
    else:
        # try to open the file
        # set the window title
        self.__root.title(os.path.basename(self.__file) + " - Notepad")
        self.__thisTextArea.delete(1.0,END)

        file = open(self.__file,"r")

        self.__thisTextArea.insert(1.0,file.read())

        file.close()

def __newFile(self):
    self.__root.title("Untitled - Notepad")
    self.__file = None
    self.__thisTextArea.delete(1.0,END)

def __saveFile(self):

    if self.__file == None:
        #save as new file
        self.__file = asksaveasfilename(initialfile='Untitled.txt',
                                        defaultextension=".txt",
                                        filetypes=[("All Files","*.*"),
                                            ("Text Documents","*.txt")])

        if self.__file == "":
            self.__file = None
        else:

            # try to save the file
            file = open(self.__file,"w")
            file.write(self.__thisTextArea.get(1.0,END))
            file.close()
            # change the window title
            self.__root.title(os.path.basename(self.__file) + " - Notepad")

    else:
        file = open(self.__file,"w")
        file.write(self.__thisTextArea.get(1.0,END))
        file.close()

def __cut(self):
    self.__thisTextArea.event_generate("<<Cut>>")

def __copy(self):
    self.__thisTextArea.event_generate("<<Copy>>")

def __paste(self):
    self.__thisTextArea.event_generate("<<Paste>>")
```

在这里，我们已经添加了记事本中需要的所有功能，您也可以在这里添加其他功能，如字体大小、字体颜色、粗体、下划线等。

**全部合并后的主代码:**

## 计算机编程语言

```
import tkinter
import os   
from tkinter import *
from tkinter.messagebox import *
from tkinter.filedialog import *

class Notepad:

    __root = Tk()

    # default window width and height
    __thisWidth = 300
    __thisHeight = 300
    __thisTextArea = Text(__root)
    __thisMenuBar = Menu(__root)
    __thisFileMenu = Menu(__thisMenuBar, tearoff=0)
    __thisEditMenu = Menu(__thisMenuBar, tearoff=0)
    __thisHelpMenu = Menu(__thisMenuBar, tearoff=0)

    # To add scrollbar
    __thisScrollBar = Scrollbar(__thisTextArea)    
    __file = None

    def __init__(self,**kwargs):

        # Set icon
        try:
                self.__root.wm_iconbitmap("Notepad.ico")
        except:
                pass

        # Set window size (the default is 300x300)

        try:
            self.__thisWidth = kwargs['width']
        except KeyError:
            pass

        try:
            self.__thisHeight = kwargs['height']
        except KeyError:
            pass

        # Set the window text
        self.__root.title("Untitled - Notepad")

        # Center the window
        screenWidth = self.__root.winfo_screenwidth()
        screenHeight = self.__root.winfo_screenheight()

        # For left-align
        left = (screenWidth / 2) - (self.__thisWidth / 2)

        # For right-align
        top = (screenHeight / 2) - (self.__thisHeight /2)

        # For top and bottom
        self.__root.geometry('%dx%d+%d+%d' % (self.__thisWidth,
                                              self.__thisHeight,
                                              left, top))

        # To make the textarea auto resizable
        self.__root.grid_rowconfigure(0, weight=1)
        self.__root.grid_columnconfigure(0, weight=1)

        # Add controls (widget)
        self.__thisTextArea.grid(sticky = N + E + S + W)

        # To open new file
        self.__thisFileMenu.add_command(label="New",
                                        command=self.__newFile)   

        # To open a already existing file
        self.__thisFileMenu.add_command(label="Open",
                                        command=self.__openFile)

        # To save current file
        self.__thisFileMenu.add_command(label="Save",
                                        command=self.__saveFile)   

        # To create a line in the dialog       
        self.__thisFileMenu.add_separator()                                        
        self.__thisFileMenu.add_command(label="Exit",
                                        command=self.__quitApplication)
        self.__thisMenuBar.add_cascade(label="File",
                                       menu=self.__thisFileMenu)    

        # To give a feature of cut
        self.__thisEditMenu.add_command(label="Cut",
                                        command=self.__cut)            

        # to give a feature of copy   
        self.__thisEditMenu.add_command(label="Copy",
                                        command=self.__copy)        

        # To give a feature of paste
        self.__thisEditMenu.add_command(label="Paste",
                                        command=self.__paste)        

        # To give a feature of editing
        self.__thisMenuBar.add_cascade(label="Edit",
                                       menu=self.__thisEditMenu)    

        # To create a feature of description of the notepad
        self.__thisHelpMenu.add_command(label="About Notepad",
                                        command=self.__showAbout)
        self.__thisMenuBar.add_cascade(label="Help",
                                       menu=self.__thisHelpMenu)

        self.__root.config(menu=self.__thisMenuBar)

        self.__thisScrollBar.pack(side=RIGHT,fill=Y)                   

        # Scrollbar will adjust automatically according to the content       
        self.__thisScrollBar.config(command=self.__thisTextArea.yview)    
        self.__thisTextArea.config(yscrollcommand=self.__thisScrollBar.set)

    def __quitApplication(self):
        self.__root.destroy()
        # exit()

    def __showAbout(self):
        showinfo("Notepad","Mrinal Verma")

    def __openFile(self):

        self.__file = askopenfilename(defaultextension=".txt",
                                      filetypes=[("All Files","*.*"),
                                        ("Text Documents","*.txt")])

        if self.__file == "":

            # no file to open
            self.__file = None
        else:

            # Try to open the file
            # set the window title
            self.__root.title(os.path.basename(self.__file) + " - Notepad")
            self.__thisTextArea.delete(1.0,END)

            file = open(self.__file,"r")

            self.__thisTextArea.insert(1.0,file.read())

            file.close()

    def __newFile(self):
        self.__root.title("Untitled - Notepad")
        self.__file = None
        self.__thisTextArea.delete(1.0,END)

    def __saveFile(self):

        if self.__file == None:
            # Save as new file
            self.__file = asksaveasfilename(initialfile='Untitled.txt',
                                            defaultextension=".txt",
                                            filetypes=[("All Files","*.*"),
                                                ("Text Documents","*.txt")])

            if self.__file == "":
                self.__file = None
            else:

                # Try to save the file
                file = open(self.__file,"w")
                file.write(self.__thisTextArea.get(1.0,END))
                file.close()

                # Change the window title
                self.__root.title(os.path.basename(self.__file) + " - Notepad")

        else:
            file = open(self.__file,"w")
            file.write(self.__thisTextArea.get(1.0,END))
            file.close()

    def __cut(self):
        self.__thisTextArea.event_generate("<<Cut>>")

    def __copy(self):
        self.__thisTextArea.event_generate("<<Copy>>")

    def __paste(self):
        self.__thisTextArea.event_generate("<<Paste>>")

    def run(self):

        # Run main application
        self.__root.mainloop()

# Run main application
notepad = Notepad(width=600,height=400)
notepad.run()
```

要运行此代码，请通过扩展名**保存它。py** 然后打开 cmd(命令提示符)，移动到保存文件的位置，然后写下以下内容

```
python "filename".py 
```

然后按回车键，它就会运行。或者只需双击**即可直接运行。py** 扩展名文件。