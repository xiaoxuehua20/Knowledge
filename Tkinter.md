## 来源

**总结自网络教程** : https://www.cnblogs.com/shwee/p/9427975.html

**Python官网** : https://docs.python.org/zh-cn/3/library/tkinter.html

## 简要说明

**Button：**一个简单的**按钮**，用来执行一个命令或别的操作

**Canvas：**组织图形。这个部件可以用来绘制图表和图，创建图形编辑器，实现定制窗口部件        (过于复杂,请至教程网址自行学习)

csdn博客 : https://blog.csdn.net/dhjabc_1/article/details/105449496

极客笔记 : https://deepinout.com/tkinter/tkinter-canvas/tkinter-canvas-draw-lines.html

**Checkbutton：**代表一个**变量**，它有两个不同的值。点击这个按钮将会在这两个值间切换

**Entry：**文本输入域

**Frame：**一个容器窗口部件。帧可以有边框和背景，当创建一个应用程序或dialog(对话）版面时，帧被用来组织其它的窗口部件

**Label：**显示一个**文本**或**图象**

**Listbox：**显示供选方案的一个**列表**。listbox能够被配置来得到radiobutton或checklist的行为

**Menu：**菜单条。用来实现下拉和弹出式菜单

**Menubutton：**菜单按钮。用来实现下拉式菜单

**Message：**显示一文本。类似label窗口部件，但是能够自动地调整文本到给定的宽度或比率

**Radiobutton：**代表一个变量，它可以有多个值中的一个。点击它将为这个变量设置值，并且清除与这同一变量相关的其它radiobutton

**Scale：**允许你通过滑块来设置一数字值

**Scrollbar：**为配合使用canvas, entry, listbox, and text窗口部件的标准滚动条

**Text：**格式化文本显示。允许你用不同的样式和属性来显示和编辑文本。同时支持内嵌图象和窗口

**Toplevel：**一个容器窗口部件，作为一个单独的、最上面的窗口显示

**messageBox**：消息框，用于显示你应用程序的消息框。(Python2中为tkMessagebox)

注意在Tkinter中窗口部件类没有分级；所有的窗口部件类在树中都是兄弟关系。

## 创建主窗口

```python
import tkinter as tk

# 第1步,实例化object,建立窗口window
window = tk.Tk()

# 第2步,给窗口的可视化起名字
window.title("一个Tkinter程序")

# 第3步,设定窗口的大小(长 * 宽)
window.geometry("500x400")  # 注意是小写"x"

# 第4步,在图形界面上设定标签

# 第5步,放置标签

# 第6步,主窗口循环显示
window.mainloop()
# 注意，loop因为是循环的意思，window.mainloop就会让window不断的刷新，如果没有mainloop,就是一个静态的window,传入进去的值就不会有循环，mainloop就相当于一个很大的while循环，有个while，每点击一次就会更新一次，所以我们必须要有循环
```

## Label

```python
import tkinter as tk

window = tk.Tk()

window.title("一个Tkinter程序")
window.geometry("500x400") 

l = tk.Label(window,text="你好",bg="green",font=('Arial', 12),width=30,height=2)
# "window":接受对象 "text":显示的文本 "bg":背景颜色 "font":字体 

l.pack()    # 控制组件在其容器中出现的位置

window.mainloop()
```

## Button

```python
import tkinter as tk

window = tk.Tk()
window.title("一个Tkinter程序")
window.geometry("500x400") 

var = tk.StringVar()    # 用于接收可改变的值
l = tk.Label(window,textvariable=var, bg='green', fg='white', font=('Arial', 12), width=30, height=2)
# "textvariable":text变量
l.pack()

def hit_me():
    var.set("你成功点击")   # 设置变量的值

b = tk.Button(window,text="点击我",width=10, height=1,command=hit_me)
# "command":链接函数
b.pack()

window.mainloop()
```

## Entry

```python
# 一个单行文本输入域,用来输入显示一行文本,收集键盘输入
import tkinter as tk

window = tk.Tk()
window.title("一个Tkinter程序")
window.geometry("500x400") 

e1 = tk.Entry(window,show="*")  # 密文形式,不一定是"*"
e2 = tk.Entry(window,show=None) # 明文形式
e1.pack(expand=1)
e2.pack()

window.mainloop()
```

## Text

```python
# 一个多行文本区域,显示多行文本,可用来收集(或显示)用户输入的文字
import tkinter as tk

window = tk.Tk()
window.title("一个Tkinter程序")
window.geometry("500x400") 

e = tk.Entry(window,show=None)
e.pack()

# 函数一定要放在按钮的上面
def insert_point():
    var = e.get()   # Entry获取
    t.insert("insert",var)  # 在焦点处输入
def insert_end():
    var = e.get()
    t.insert("end",var) # 在尾部输入

b1 = tk.Button(window,text="在焦点处输入",width=10,height=2,command=insert_point)
b2 = tk.Button(window,text="在尾部处输入",width=10,height=2,command=insert_end)
b1.pack()
b2.pack()

t = tk.Text(window,height=3)
t.pack()

window.mainloop()
```

## Listbox

```python
# 列表框部件 显示供选方案的一个列表
'''提供一个选项列表,点击按纽后,添加选中的值到显示框中'''
import tkinter as tk

window = tk.Tk()
window.title("一个Tkinter程序")
window.geometry("500x400") 

var1 = tk.StringVar()
l = tk.Label(window,textvariable=var1,bg="green",font=('Arial', 12),width=30,height=2)
l.pack()

def pr():
    value = lb.get(lb.curselection())   # 获取当前选中文本的值
    var1.set(value)

b = tk.Button(window,text="点击我",width=15,height=2,command=pr)
b.pack()

var2 = tk.StringVar()
var2.set((1,2,3,4))
lb = tk.Listbox(window,listvariable=var2)   
lb.insert(1,"第一个参数")   # 在索引处添加元素
lb.insert(2,"第二个参数")
lb.delete(2)    # 删除索引处的元素
lb.pack()

window.mainloop()# 列表框部件 显示供选方案的一个列表
'''提供一个选项列表,点击按纽后,添加选中的值到显示框中'''
import tkinter as tk

window = tk.Tk()
window.title("一个Tkinter程序")
window.geometry("500x400") 

var1 = tk.StringVar()
l = tk.Label(window,textvariable=var1,bg="green",font=('Arial', 12),width=30,height=2)
l.pack()

def pr():
    value = lb.get(lb.curselection())   # 获取当前选中文本的值
    var1.set(value)

b = tk.Button(window,text="点击我",width=15,height=2,command=pr)
b.pack()

var2 = tk.StringVar()
var2.set((1,2,3,4))
lb = tk.Listbox(window,listvariable=var2)   
lb.insert(1,"第一个参数")   # 在索引处添加元素
lb.insert(2,"第二个参数")
lb.delete(2)    # 删除索引处的元素
lb.pack()

window.mainloop()
```

## Radiobutton

```python
# 代表一个变量 多个值中的一个 可连接函数
# 显示为单选按钮
'''提供单选按钮,通过显示框显示所选项'''
import tkinter as tk

window = tk.Tk()
window.title("一个Tkinter程序")
window.geometry("500x400") 

var = tk.StringVar()
l = tk.Label(window,textvariable=var,bg="green",font=('Arial', 12),width=30,height=2)
l.pack()

def pr():
    l.config(var)

# "text":显示的值 "value":表示的值 "variable":传出的对象
r1 = tk.Radiobutton(window,text="A",variable=var,value="A",command=pr)
r1.pack()
r2 = tk.Radiobutton(window,text="B",variable=var,value="B",command=pr)
r2.pack()
r3 = tk.Radiobutton(window,text="C",variable=var,value="C",command=pr)
r3.pack()

window.mainloop()
```

## Checkbutton

```python
# 代表一个变量 有两个不同的值 选择和取消选择 会在这两个值间切换
# 显示为多选框
'''提供多选框 选择后在显示框上显示"both"或单个值'''
import tkinter as tk

window = tk.Tk()
window.title("一个Tkinter程序")
window.geometry("500x400") 

l = tk.Label(window,text="Empty",bg="green",font=('Arial', 12),width=30,height=2)
l.pack()

def pr():
    if (var1.get()==1) and (var2.get()==0): # 选中c1,未选c2
        l.config(text='Python')
    elif (var1.get()==0) and (var2.get()==1):   # 未选c2,选中c1
        l.config(text='C')
    elif (var1.get()==0) and (var2.get()==0):   # 都未选中
        l.config(text='Empty')
    else:
        l.config(text='Both')   # 都选中

var1 = tk.IntVar()  # 整型变量用来存放选择行为返回值
var2 = tk.IntVar()
c1 = tk.Checkbutton(window,text='Python',variable=var1,onvalue=1,offvalue=0,command=pr)
c2 = tk.Checkbutton(window,text='C',variable=var2,onvalue=1,offvalue=0,command=pr)
c1.pack()
c2.pack()

window.mainloop()
```

## Scale

```python
# 尺度(拉动条) 允许你通过滑块来设置一数字值
'''提供一个尺度条,并展示所选值'''
import tkinter as tk

window = tk.Tk()
window.title("一个Tkinter程序")
window.geometry("500x400") 

l = tk.Label(window, bg='green', fg='white', width=20, text='0.00')
l.pack()

def pr(v):
    l.config(text=v)

s = tk.Scale(window,label="这是一个尺度条",from_=0,to=100,orient=tk.VERTICAL,length=500,showvalue=1,tickinterval=2,resolution=4,command=pr)
# 从0到100 竖向,"HORIZONTAL"为横向 展示长度500 展示当前值 刻度为2 精度为4
s.pack()

window.mainloop()
```

## Menu

```python
# 菜单条 实现下拉和弹出式菜单 点下菜单后弹出的一个选项列表 可以从中选择
'''
为方便理解 设置了多级菜单及元素 菜单及层级 元素是由函数绑定的可操作模块
采用变量名 未使用显示名
'''
import tkinter as tk

window = tk.Tk()
window.title("一个Tkinter程序")
window.geometry("500x400") 

l = tk.Label(window,text='      ',bg='green')
l.pack()

# "menubar"属于"window" 级别:一级菜单
menubar = tk.Menu(window)

# "filemenu"属于"menubar" 级别:二级菜单
filemenu = tk.Menu(menubar,tearoff=0)   # 默认不下拉
menubar.add_cascade(label='File',menu=filemenu)

# 每多操作一次 显示次数加一
counter = 0
def do_job():
    global counter
    l.config(text='do '+ str(counter))
    counter += 1

# 在File中加入New,Open,Save等小菜单 即我们平时看到的下拉菜单 每一个小菜单对应命令操作
# 都是"filemenu"的元素 级别:元素
filemenu.add_command(label='New',command=do_job)
filemenu.add_command(label='Open',command=do_job)
filemenu.add_command(label='Save',command=do_job)
filemenu.add_separator()    # 添加一条分隔线
filemenu.add_command(label='Exit', command=window.quit) # 用tkinter里面自带的quit()函数

# "editmenu"属于"menubar" 级别:二级菜单
editmenu = tk.Menu(menubar, tearoff=0)
menubar.add_cascade(label='Edit', menu=editmenu)

# 都是"editmenu"的元素 级别:元素
editmenu.add_command(label='Cut', command=do_job)
editmenu.add_command(label='Copy', command=do_job)
editmenu.add_command(label='Paste', command=do_job)

# "submenu"属于"filemenu" 级别:三级菜单
submenu = tk.Menu(filemenu)
filemenu.add_cascade(label='Import', menu=submenu, underline=0) 
# "Submenu_1"是"submenu"的元素 级别:元素
submenu.add_command(label='Submenu_1', command=do_job)

window.config(menu=menubar) # 创建菜单栏完成后，配置让菜单栏menubar显示出来

window.mainloop()
```

## Frame

```python
# 一种容器 用来承载放置其他GUI元素 同时一个 Frame 上也能再分成两个 Frame
import tkinter as tk

window = tk.Tk()
window.title("一个Tkinter程序")
window.geometry("500x400") 

tk.Label(window,text='on the window',bg='red', font=('Arial', 16)).pack()# 和前面部件分开创建和放置不同，其实可以创建和放置一步完成

frame = tk.Frame(window)    # 接受容器为"window"
frame.pack()

frame_1 = tk.Frame(frame)   # 接受容器为"frame"
frame_2 = tk.Frame(frame)   # 接受容器为"frame"
frame_1.pack(side='left')
frame_2.pack(side='right')

tk.Label(frame_1, text='on the frame_l1', bg='green').pack()    # 接受容器为"frame1"
tk.Label(frame_1, text='on the frame_l2', bg='green').pack()    # 接受容器为"frame1"
tk.Label(frame_1, text='on the frame_l3', bg='green').pack()    # 接受容器为"frame1"
tk.Label(frame_2, text='on the frame_r1', bg='yellow').pack()   # 接受容器为"frame2"
tk.Label(frame_2, text='on the frame_r2', bg='yellow').pack()   # 接受容器为"frame2"
tk.Label(frame_2, text='on the frame_r3', bg='yellow').pack()   # 接受容器为"frame2"

window.mainloop()
```

## Messagebox

```python
# 消息框 显示你应用程序的消息框
import tkinter as tk
import tkinter.messagebox  # 要使用messagebox先要导入模块

window = tk.Tk()
window.title("一个Tkinter程序")
window.geometry("500x400") 

def hit_me():
    # "title":标题 "message":显示内容
    tkinter.messagebox.showinfo(title='Hi', message='你好！')              # 提示信息对话窗
    # tkinter.messagebox.showwarning(title='Hi', message='有警告！')       # 提出警告对话窗
    # tkinter.messagebox.showerror(title='Hi', message='出错了！')         # 提出错误对话窗
    # print(tkinter.messagebox.askquestion(title='Hi', message='你好！'))  # 询问选择对话窗return 'yes', 'no'
    # print(tkinter.messagebox.askyesno(title='Hi', message='你好！'))     # return 'True', 'False'
    # print(tkinter.messagebox.askokcancel(title='Hi', message='你好！'))  # return 'True', 'False'

tk.Button(window, text='hit me', bg='green', font=('Arial', 14), command=hit_me).pack()

window.mainloop()
```

## Canvas

**组织图形 这个部件可以用来绘制图表和图 创建图形编辑器 实现定制窗口部件**

### 创建画布

```python
cv = tk.Canvas(window,width=200,height=200)
cv.pack(fill="both",expand=1)
```

### 线条

**用法**

```python
create_line(x1, y1, x2, y2, ... xn, yn, options)
```

线条将会沿着（x1,y1）,（x2,y2）, …绘制下去

```python
cv.create_line(
    10,10,10,200,
    fill="green",            # 填充颜色
    dash=(10,2,10,1,10,1),   # 形如此元素 第一位表示虚线长度,第二位表示间隔距离 后续以此类推 
                             # 至多三组,多了不起效果 会先展示大的长度,后续展示小长度
    # 以下仅适用于"create_line"
    arrow="both",   # 直线两端是否有箭头    "first":开始端有箭头 "None":两端无箭头 "last":结束端有箭头 "both":两端都有箭头
    arrowshape="20 20 10"   # 箭头形状 形如"20 20 10"的字符串 依次表示:填充长度,箭头长度,箭头宽度
```

### 矩形

```python
create_rectangle(x1, y1, x2, y2, options)
```

（x1,y1）和（x2,y2）是矩形左上角和右下角的坐标

```python
cv.create_rectangle(
    10,10,500,500       # x1,y1,x2,y2 左上角坐标,右下角坐标
    # fill      拥有填充颜色
    # dash      虚线
    # outline   边界颜色
    # width     边界宽度
)
```

## 包装器

**包装器**

控制组件在其容器中出现的位置

可理解为下文的**通用**属性    (其实是pack参数,但大部分通用)

但独有属性优先

知乎讲解 : https://zhuanlan.zhihu.com/p/431052225

### 参数

#### anchor

anchor 类型        表示包装器要放置的每个从属组件的位置

`n` : **北**

`s` : **南**

`w` : **西**

`e` : **东**

`center` : **中心**

`nw` : **西北**

`ne` : **东北**

`se` : **东南**

`sw` : **西南**

#### expand

组件的"势力范围"是否扩大到"扩展范围"

"势力范围" : 元素所占区域,其它元素不可进入 

"扩展范围" : 整个区域,其它元素可进入

布尔型，`0` 或 `1`

#### fill

是否填充及填充方向

`'x'`  : 横向填充

`'y'`  : 纵向填充

`'both'`  : 横向和纵向都填充

`'none'` : 横向和纵向都不填充

#### ipadx 和 ipady

距离值，指定从属部件的内边距

#### padx 和 pady

距离值，指定从属部件的外边距

#### side

合法值为：`'left'`、 `'right'` 、 `'top'`、 `'bottom'`    # 常用

## 三种放置方式及特殊值

### Grid

```python
import tkinter as tk

window = tk.Tk()
window.title("一个Tkinter程序")
window.geometry("500x400") 

'''
grid放置
所有的内容会被放在这些规律的方格中
'''
for i in range(3):
    for j in range(3):
        tk.Label(window, text=1).grid(row=i, column=j, padx=10, pady=10, ipadx=10, ipady=10)
# "row":行 "column":列 "padx":单元格左右间距 "pady":单元格上下间距 "ipadx":单元格内部元素与单元格的左右间距 "ipady":单元格内部元素与单元格的上下间距

window.mainloop()
```

### Pack

```python
import tkinter as tk

window = tk.Tk()
window.title("一个Tkinter程序")
window.geometry("500x400") 

'''
按照上下左右的方式排列
'''

tk.Label(window,text="上",fg="red").pack(side="top")        # 上
tk.Label(window,text="下",fg="green").pack(side="bottom")   # 下
tk.Label(window,text="左",fg="blue").pack(side="left")      # 左
tk.Label(window,text="右",fg="black").pack(side="right")    # 右


window.mainloop()
```

### Place

```python
import tkinter as tk

window = tk.Tk()
window.title("一个Tkinter程序")
window.geometry("500x400") 

'''
给精确的坐标来定位
'''

tk.Label(window,text="PI").place(x=200,y=50)

window.mainloop()
```

## 总结

### Label

```python
var = tk.StringVar()
l = tk.Label(window,textvariable=var,bg='green')
l.pack()
var.set('123')
print(var.get())
```

`StringVar()` : 

可通过`textvariable`显示

通过`set()`设置值

需通过`get()`以获取字符串    (`Entry Text`同样适用,可见上)

```python
l = tk.Label(window,text=123,bg='green')
l.pack()
l.config(text='456')
```

`text` : 可通过`config`设置值

### Text

```python
t = tk.Text(window,height=3)
t.pack()
t.insert("end",'你好')
```

`insert` : 插入值

​    `insert` : 当前位置(焦点处)

​    `end` : 尾部

### Listbox

```python
var2 = tk.StringVar()
lb = tk.Listbox(window,listvariable=var2) 
lb.pack()
lb.get(lb.curselection())
lb.insert(2,"第二个参数")
lb.delete(2)
```

`listvariable` : 接受`StringVar()`

`get(变量名.curselection())` : 获取值

`insert(2,"第二个参数")` : `insert(索引 , 文本)`        # 插入

`delete(2)` : `delete(索引)`        # 删除

### Checkbutton

```python
var1 = tk.IntVar()    # 整型变量用来存放选择行为返回值
c1 = tk.Checkbutton(window,text='Python',variable=var1,onvalue=1,offvalue=0,command=pr)
var1.get()
```

`variable` : 接受`IntVar()`

`get()` : 获取字符串

### 修改值

#### 对象创建时

**使用关键字参数**

```python
l = tk.Label(window,text="你好",bg="green",font=('Arial', 12),width=30,height=2)
l.pack()    
```

#### 对象创建后

**将参数名用作字典索引**

```python
l = tk.Label(window,text="你好",bg="green",font=('Arial', 12),width=30,height=2)
l["height"] = 50
l.pack() 
```

#### 修改多个属性

利用 `config()` 方法

```python
l = tk.Label(window,text="你好",bg="green",font=('Arial', 12),width=30,height=2)
l.config(width=10,height=20)
l.pack()    
```
