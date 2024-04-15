## Pyplot

仅作为先导入门,各参数后续有详细讲解

### 引入

```python
import matplotlib.pyplot as plt
```

### 简单使用

```python
plot([x], y, [fmt],)
```

`x` : x坐标 

`y` : y坐标

`fmt` : 可选,定义基本格式(如:颜色,标记和线条样式)

### fmt

**颜色字符 ：**`b` 蓝色，`m` 洋红色，`g` 绿色，`y` 黄色，`r` 红色，`k` 黑色，`w'`白色，`c` 青绿色，`#008000` RGB 颜色符串。多条曲线不指定颜色时，会自动选择不同颜色。

**线型参数：**`‐` 实线，`‐‐` 破折线，`‐.` 点划线，`:` 虚线。

**标记字符：**`.` 点标记，`,` 像素标记(极小点)，`o` 实心圈标记，`v` 倒三角标记，`^` 上三角标记，`>` 右三角标记，`<` 左三角标记...等等    (有时会只显示点)

## 绘图标记

可以使用 `plot()` 方法的 `marker` 参数来定义

```python
plt.plot(xpoint,ypoint,marker='o')
```

### maker

解释不好就不解释了,需要的自行查询吧

| `.`                | ![m00](https://www.runoob.com/images/m00.png) | 点                           |
| ------------------ | --------------------------------------------- | --------------------------- |
| `,`                | ![m01](https://www.runoob.com/images/m01.png) | 像素点                         |
| `o`                | ![m02](https://www.runoob.com/images/m02.png) | 实心圆                         |
| `v`                | ![m03](https://www.runoob.com/images/m03.png) | 下三角                         |
| `^`                | ![m04](https://www.runoob.com/images/m04.png) | 上三角                         |
| `<`                | ![m05](https://www.runoob.com/images/m05.png) | 左三角                         |
| `>`                | ![m06](https://www.runoob.com/images/m06.png) | 右三角                         |
| `1`                | ![m07](https://www.runoob.com/images/m07.png) | 下三叉                         |
| `2`                | ![m08](https://www.runoob.com/images/m08.png) | 上三叉                         |
| `3`                | ![m09](https://www.runoob.com/images/m09.png) | 左三叉                         |
| `4`                | ![m10](https://www.runoob.com/images/m10.png) | 右三叉                         |
| `8`                | ![m11](https://www.runoob.com/images/m11.png) | 八角形                         |
| `s`                | ![m12](https://www.runoob.com/images/m12.png) | 正方形                         |
| `p`                | ![m13](https://www.runoob.com/images/m13.png) | 五边形                         |
| `P`                | ![m23](https://www.runoob.com/images/m23.png) | 加号（填充）                      |
| `*`                | ![m14](https://www.runoob.com/images/m14.png) | 星号                          |
| `h`                | ![m15](https://www.runoob.com/images/m15.png) | 六边形 1                       |
| `H`                | ![m16](https://www.runoob.com/images/m16.png) | 六边形 2                       |
| `+`                | ![m17](https://www.runoob.com/images/m17.png) | 加号                          |
| `x`                | ![m18](https://www.runoob.com/images/m18.png) | 乘号 x                        |
| `X`                | ![m24](https://www.runoob.com/images/m24.png) | 乘号 x (填充)                   |
| `D`                | ![m19](https://www.runoob.com/images/m19.png) | 菱形                          |
| `d`                | ![m20](https://www.runoob.com/images/m20.png) | 瘦菱形                         |
| \|`                | ![m21](https://www.runoob.com/images/m21.png) | 竖线                          |
| `_`                | ![m22](https://www.runoob.com/images/m22.png) | 横线                          |
| 0 (TICKLEFT)       | ![m25](https://www.runoob.com/images/m25.png) | 左横线(输入数字"0"即可)(后续相同)        |
| 1 (TICKRIGHT)      | ![m26](https://www.runoob.com/images/m26.png) | 右横线                         |
| 2 (TICKUP)         | ![m27](https://www.runoob.com/images/m27.png) | 上竖线                         |
| 3 (TICKDOWN)       | ![m28](https://www.runoob.com/images/m28.png) | 下竖线                         |
| 4 (CARETLEFT)      | ![m29](https://www.runoob.com/images/m29.png) | 左箭头                         |
| 5 (CARETRIGHT)     | ![m30](https://www.runoob.com/images/m30.png) | 右箭头                         |
| 6 (CARETUP)        | ![m31](https://www.runoob.com/images/m31.png) | 上箭头                         |
| 7 (CARETDOWN)      | ![m32](https://www.runoob.com/images/m32.png) | 下箭头                         |
| 8 (CARETLEFTBASE)  | ![m33](https://www.runoob.com/images/m33.png) | 左箭头 (中间点为基准)                |
| 9 (CARETRIGHTBASE) | ![m34](https://www.runoob.com/images/m34.png) | 右箭头 (中间点为基准)                |
| 10 (CARETUPBASE)   | ![m35](https://www.runoob.com/images/m35.png) | 上箭头 (中间点为基准)                |
| 11 (CARETDOWNBASE) | ![m36](https://www.runoob.com/images/m36.png) | 下箭头 (中间点为基准)                |
| "None", " " or ""  |                                               | 没有任何标记                      |
| '$...$'            | ![m37](https://www.runoob.com/images/m37.png) | 渲染指定的字符。例如 "$f$" 以字母 f 为标记。 |

### fmt

```python
fmt = '[marker][line][color]'
```

实测可交换位置

`marker` 见上文

`line` 

| `-`  | 实线  |
| ---- | --- |
| `:`  | 虚线  |
| `--` | 破折线 |
| `-.` | 点划线 |

`color`

| `r` | 红色  |
| --- | --- |
| `g` | 绿色  |
| `b` | 蓝色  |
| `c` | 青色  |
| `m` | 品红  |
| `y` | 黄色  |
| `k` | 黑色  |
| `w` | 白色  |

### 大小与颜色

编辑器可能无提示

- `markersize`，简写为`ms`：定义标记的大小     (传入数字)               
- `markerfacecolor`，简写为 **`mfc`**：定义标记内部的颜色(传入颜色值,通格式)
- `markeredgecolor`，简写为 **`mec`**：定义标记边框的颜色(传入颜色值,通格式)

## 绘图线

绘图过程如果我们自定义线的**样式**，包括线的**类型**、**颜色**和**大小**等

### 线的类型

使用 **`linestyle`** 参数来定义，简写为 `ls`

```python
plt.plot(x1,y1,linestyle='dotted')
```

| 类型           | 简写    | 说明  |
| ------------ | ----- | --- |
| `solid` (默认) | `-`   | 实线  |
| `dotted`     | `:`   | 点虚线 |
| `dashed`     | `--`  | 破折线 |
| `dashdot`    | `-.`  | 点划线 |
| `None`       | ` 或 ` | 不画线 |

**使用简写**

```python
plt.plot(x1,y1,ls='-.')
```

### 线的颜色

可以使用 **`color`** 参数来定义，简写为`c`

```python
plt.plot(x1,y1,color='r')
```

| `r` | 红色  |
| --- | --- |
| `g` | 绿色  |
| `b` | 蓝色  |
| `c` | 青色  |
| `m` | 品红  |
| `y` | 黄色  |
| `k` | 黑色  |
| `w` | 白色  |

可使用自定义颜色类型

**使用简写**

```python
plt.plot(x2,y2,c='b')
```

### 线的宽度

可以使用 **`linewidth`** 参数来定义，简写为 `lw`，值可以是**浮点数**

```python
plt.plot(x1,y1,linewidth=5)
```

**使用简写**

```python
plt.plot(x1,y1,lw=5)
```

### 多条线

```python
plt.plot(x1,y1,color='r')
plt.plot(x2,y2,c='b')
```

`x`默认为 `[1,2,3,4,...]`    仅需输入 `y轴坐标`

因此在使用时第一位数对应的是 `1`

## 轴标签和标题

### 注意

无论是轴标签还是标题

都需放置在`show`前

不然会无法显示

### 轴标签

使用 **`xlabel()`** 和 **`ylabel()`** 方法来设置 x 轴和 y 轴的**标签**

```python
plt.ylabel('y-label',loc='top')
plt.xlabel('x-label',size=20,loc='left') 
```

两者都具有 `size` 或 `fontsize` 控制字体大小

也都具有 `loc` 位置

| `top`    | 顶部     |
| -------- | ------ |
| `bottom` | 底部     |
| `center` | 中间(默认) |
| `left`   | 靠左     |
| `right`  | 靠右     |

### 标题

**使用 `title()`** 方法来设置标题

```python
plt.title('Xiaoxuehua20')
```

## 网格图

使用 `pyplot` 中的 `grid()` 方法来设置图表中的网格线

**语法**

```python
matplotlib.pyplot.grid(b=None, which='major', axis='both', )
```

都为可选参数

- `b`：表示是否显示网格，默认值为True，即显示网格
- `which`：表示哪些网格需要显示，可以是`major`，表示主刻度网格；`minor`，表示次刻度网格；`both`，表示主刻度和次刻度网格。默认值为`major`
- `axis`：表示显示哪些轴的网格，可以是`both`表示显示x轴和y轴网格；`x`表示只显示x轴网格；`y`表示只显示y轴网格。默认值为`both`
- `alpha`：指定网格线的透明度，默认为1

仅讲解常用参数 `axis` 及网格**样式**

`axis` 设置显示线的**方向**

| `y`    | 沿y轴方向   |
| ------ | ------- |
| `x`    | 沿x轴方向   |
| `both` | x,y轴都显示 |

网格样式同**线的样式**都**通用**,可**简写**

## 绘制多图

### 单子图

`subplots()`

```python
fig,ax = plt.subplots()
ax.plot(x,y)
ax.set_title('Part 1')    "标题设置"
```

### 单方向堆叠

#### 纵向堆叠

```python
fig , axs = plt.subplots(2)    "两行"
fig.suptitle('Part 2')   "标题设置"
axs[0].plot(x,y)        "第一个"
axs[1].plot(x,-y)        "第二个"
```

如果只创建**几个**,使用 压缩到**专用变量** 会**方便**许多

```python
fig , (axs1,axs2) = plt.subplots(2)
fig.suptitle('Part 2')
axs1.plot(x,y)
axs2.plot(x,-y)
```

#### 横向堆叠

```python
fig, (ax1, ax2) = plt.subplots(1, 2)
fig.suptitle('Part 3')
ax1.plot(x, y)
ax2.plot(x, -y)
```

传递一行和两列的参数 `1, 2`

### 双方向堆叠

左上角为 `[0,0]`

右下角为 `[N,N]`

```python
fig,axs = plt.subplots(2,2)    """生成 2x2 """
axs[0,0].plot(x,y)            """编辑第一行第一列"""
axs[0,0].set_title('Part1')
axs[0,1].plot(x,y)             """编辑第一行第二列"""
axs[0,1].set_title('Part2')
axs[1,0].plot(x,y)            """编辑第二行第一列"""
axs[1,0].set_title('Part3')
axs[1,1].plot(x,y)            """编辑第二行第列"""
axs[1,1].set_title('Part4')
for ax in axs.flat:
    ax.set(xlabel="x",ylabel='y')
```

如果您必须为**每个**子图**设置参数**，则可以方便地使用.`for ax in axs.flat`

### 共享轴

```python
fig, (ax1, ax2) = plt.subplots(2,sharex='row',sharey=True)
fig.suptitle('Part 5')
ax1.plot(x, y)
ax2.plot(x + 1, -y)
```

`sharex` 共享**方向**

`sharey` 全局共享

| `row`   | 横轴对齐    |
| ------- | ------- |
| `col`   | 纵轴对齐    |
| `all`   | 都对齐     |
| `True`  | 都对齐     |
| `False` | 不对齐(默认) |

### 减小空隙

```python
fig = plt.figure()
gs = fig.add_gridspec(2,2,hspace=0,wspace=2)    # 几个图像宽度
axs = gs.subplots(sharex=True,sharey=True)
fig.suptitle("Part 6")
axs[0,0].plot(x,color='r')
axs[0,1].plot(x*2,color='g')
axs[1,0].plot(x*4-80,color='c')
axs[1,1].plot(x+5,color='k')
```

仍旧是 在 `axs` 上绘制

`fig.add_gridspec(2,2,hspace=0,wspace=2)` 表示 `2x2` 的图

`hspace` 表示间隔高度 几个**图像宽度**

`wspace` 表示间隔宽度 几个**图像宽度**

## 散点图

```python
plt.scatter(x,y)
```

可选参数

| `x`,`y`(必选) | 长度相同的数组             |
| ----------- | ------------------- |
| `s`         | 点的大小,可以是数组,对应每个点的大小 |
| `c`         | 点的颜色                |
| `marker`    | 点的样式                |

## 柱状图

使用 `pyplot` 中的 `bar()` 方法来绘制柱形图

```python
plt.bar(x,height)
```

| `x`      | x轴数据   |
| -------- | ------ |
| `height` | 柱状图的高度 |

**可选**

| `width`  | 柱状图的宽度                                 |
| -------- | -------------------------------------- |
| `bottom` | 底座的y坐标,默认0                             |
| `align`  | 柱状图与x轴的对齐方式,`center`:**中心**,`edge`:左对齐 |
| `color`  | 颜色                                     |

```python
plt.barh(x,heigh,height=0.5)
```

横向柱状图

通过 `heigh` 设置 **高度**,即纵向的宽度

## 饼图

```python
matplotlib.pyplot.pie(x, explode=None, labels=None, colors=None,
autopct=None, pctdistance=0.6, shadow=False, labeldistance=1.1,
 startangle=0, radius=1, counterclock=True, wedgeprops=None,
 textprops=None, center=0, 0, frame=False, rotatelabels=False,
 *, normalize=None, data=None)[source]
```

大部分列表和元组 `[]` 和 `()` 可以**互相转换**

| `x`             | 浮点型数组或列表，用于绘制饼图的数据，表示每个扇形的面积                                                     |
| --------------- | -------------------------------------------------------------------------------- |
| `explode`       | 数组，表示各个扇形之间的间隔，默认值为0                                                             |
| `labels`        | 列表，各个扇形的标签，默认值为 None                                                             |
| `colors`        | 数组，表示各个扇形的颜色，默认值为 None(单值表全部)                                                    |
| `autopct`       | 设置饼图内各个扇形百分比显示格式，`%d%%` 整数百分比，`%0.1f` 一位小数， `%0.1f%%` 一位小数百分比， `%0.2f%%` 两位小数百分比 |
| `labeldistance` | 标签标记的**绘制位置**，相对于**半径的比例**，默认值为 1.1，如 <1则绘制在饼图内侧                                 |
| `shadow`        | 布尔值 True 或 False，设置饼图的**阴影**，默认为 False，不设置阴影                                     |
| `radius`        | 饼图的半径，默认为 1                                                                      |
| `startangle`    | 指定饼图的起始角度，默认为从 **x 轴正方向逆时针**画起，如设定 =90 则从 **y 轴正方向**画起                           |
| `counterclock`  | 布尔值，用于指定是否**逆时针绘制扇形**，默认为 True，即逆时针绘制，False 为顺时针                                 |
| `wedgeprops`    | 字典类型 `wedgeprops={'linewidth':5}` 设置 wedge 线宽为5                                  |
| `textprops`     | 字典属性,文本标签属性 `{'fontsize':15,'color':'b'}`                                        |
| `center`        | 浮点类型的列表，用于指定饼图的中心位置，默认值：(0,0)                                                    |
| `frame`         | 布尔类型，用于指定是否绘制饼图的边框，默认值：False。如果是 True，绘制带有表的轴框架(外围框架)                            |

### 凸显数据例子

```python
y = np.array([10,30,40,20])
plt.pie(y,explode=[0,0,0.1,0],autopct='%d%%')
plt.show()
```

## 直方图

使用 `pyplot` 中的 `hist()` 方法来绘制直方图

### 概览

除 `x` 外 都为可选参数

```python
matplotlib.pyplot.hist(x, bins=None, range=None, density=False, 
weights=None, cumulative=False, bottom=None, histtype='bar', 
align='mid', orientation='vertical', rwidth=None, log=False, 
color=None, label=None, stacked=False, **kwargs)
```

| `x`           | 表示要绘制直方图的数据,可以是一个一维数组或列表(建议通过随机数生成)                        |
| ------------- | ---------------------------------------------------------- |
| `bins`        | 表示直方图的箱数。默认为10                                             |
| `range`       | 直方图的值域范围(传入含有两个数的列表或元组,表示最大值和最小值)                          |
| `density`     | 是否将直方图归一化。默认为False(True时,y轴将显示所占比例的浮点数)                    |
| `weights`     | 表示每个数据点的权重。默认为None(up不懂____)                               |
| `cumulative`  | 是否绘制累积分布图。默认为False(将前面的所有数相加)                              |
| `bottom`      | 起始高度                                                       |
| `histtype`    | 直方图的类型，可以是`bar`、`barstacked`、`step`、`stepfilled`等。默认为`bar` |
| `align`       | 对齐方式，可以是`left`、`mid`、`right`。默认为`mid`                      |
| `orientation` | 直方图的方向，可以是`vertical`(纵)、`horizontal`(横)。默认为'vertical'      |
| `rwidth`      | 箱宽                                                         |
| `log`         | 是否在y轴上使用对数刻度。默认为False                                      |
| `color`       | 颜色                                                         |
| `label`       | 直方图标签(图例)(需搭配 `legend()` 开启图例来使用)                          |
| `stacked`     | 是否堆叠不同的直方图。默认为False                                        |
| `alpha`       | 透明度(0<=N<=1)                                               |

### 数据生成

```python
np.random.randint(0,50,400)
```

随机数的方式生成 在`numpy`中使用随机数生成 最后一位数为数据量

### `bins`

```python
plt.hist(data,bins=20)        # 显示多少个数据
```

`alpha`

```python
plt.hist(data,alpha=0.2)      # 透明度
```

### `range`

```python
plt.hist(data,range=(10,40))  # 最大值和最小值
```

### `density`

```python
plt.hist(data,density=True)   # 占总数的比值为y轴
```

### `weights`

```python
plt.hist(data,weights=np.random.randint(10,400,400)) # 数据量要相同
```

### `cumulative`

```python
plt.hist(data,cumulative=True)    # 累积分布图
```

`bottom`

```python
plt.hist(data,bottom=200)         # 起始高度
```

### 直方图类型

```python
fig,axs = plt.subplots(2,2)
axs[0,0].hist(data,histtype='barstacked',alpha=0.5,color='g')
axs[0,1].hist(data,histtype='bar',alpha=0.5,color='b')
axs[1,0].hist(data,histtype='step',alpha=0.5,color='k')    # 空心
axs[1,1].hist(data,histtype='stepfilled',alpha=0.5,color='y')
```

### 对齐方式

```python
fig,axs = plt.subplots(1,3)
axs[0].hist(data,align='left')
axs[1].hist(data,align='mid')
axs[2].hist(data,align='right')
```

### 直方图方向

```python
fig,axs = plt.subplots(2)
axs[0].hist(data,orientation='horizontal')  # 横向
axs[1].hist(data,orientation='vertical')    # 纵向(默认)
```

### `rwidth`

```python
plt.hist(data,rwidth=10)    # 箱宽
```

### `log`

```python
plt.hist(data,log=True)     # y轴使用对数
```

### `color`

```python
plt.hist(data,color='k')    # 颜色
```

### `label`

```python
plt.hist(data,label='Part1')    # 直方图标签(图例)
plt.legend()                    # 显示图例
```
