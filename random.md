## 字节数据用

```python
print(random.randbytes(5))    # randbytes(n) 生成n个随机字节
>>> b'\xc2Ef\x86\x03'
```

## 整数用

```python
print(random.randrange(0,1000,6))
>>> 114

print(random.randint(0,20))
>>> 20
```

### 用法

```python
randrange(stop)
randrange(start,stop[,step])    # 此情况下可选 step

'返回从 range(start, stop, step) 中随机选择的一个元素'

'这大致等价于 choice(range(start, stop, step))''


randint(a,b)

'返回随机整数 N 满足 a <= N <= b'

'相当于' randrange(a,b+1)
```

### 注意

```python
'''关键字参数不应被使用
因为它们可能以预料之外的方式被解读 
例如 randrange(start=100) 会被解读为 randrange(0, 100, 1)'''
```

## 序列用

### 前提

所给序列**不能为空**

序列**包含** : **列表**,**元组**,**集合**,**字典**,**字符串**

### 使用

#### `choice`

```python
# 存在序列
x = [1,2,3,4,5,6,7,8,9]
```

```python
print(random.choice(x))    # choice(seq) 
>>> 6                    # 从非空序列 seq 返回一个随机元素
```

#### `choices`

```python
print(random.choices(x,weights=[5,9,6,4,5,8,3,6,7],k=10))
>>> [9, 2, 9, 8, 4, 8, 6, 8, 9, 9]
'''choices(population,weights=None,cum_weights=None,k=1)
从 population 中有重复地随机选取元素，返回大小为 k 的元素列表

如果指定了 weight 序列，则根据相对权重进行选择(weight=[])
如果给出 cum_weights 序列，则根据累积权重进行选择
都未指定则以相同概率选择
'''
```

##### 相对权重与累计权重

```python
都以 [] 表示

例子讲解 [1,5,4,6,8]
相对权重每个值指 1/(1+5+4+6+8) 5/(1+5+4+6+8) 4/(1+5+4+6+8) 6/(1+5+4+6+8) 8/(1+5+4+6+8)
转换为累计权重 [1,6,10,16,24]

即 相对权重[a,b,c,d] 转换为 累计权重[a,a+b,a+b+c,a+b+c+d]
```

##### 注意

1. 在内部,相对权重在进行**选择之前**会**转换为累积权重**,因此**提供累积权重**可以**节省工作量**
2. 如果提供了权重序列,则它必须与 `population` 序列的**长度相同**

#### `shuffle`

```python
random.shuffle(x)
print(x)
>>> [2, 1, 9, 6, 5, 4, 3, 7, 8]
'''shuffle(x)
就地将可变序列 x 随机打乱位置(改变序列本身)

要改变一个不可变的序列并返回一个新的打乱列表，请使用 sample(x, k=len(x))'''
```

#### `sample`

```python
print(random.sample(x,k=3))
'''
sample(population, k,counts=None)
返回从总体序列中选取的唯一元素的长度为 k 的列表  用于无重复的随机抽样(不改变序列本身)
"无重复" : 当前语句选择后 便在当前 剔除已选择的值

重复的元素可以一个个地直接列出，或使用可选的仅限关键字形参 counts 来指定  
例如 sample(['red', 'blue'], counts=[4, 2], k=5) 
等价于 sample(['red', 'red', 'red', 'red', 'blue', 'blue'], k=5)

快速且节省空间: sample(range(10000000), k=60)
在10000000中随机抽取60个不重复的值

与random.choices()的区别:
一个是选取k次,一个是选取k个,选取k次的相当于选取后又放回,选取k个则选取后不放回 故random.sample()的k值不能超出集群的元素个数
'''
```

## 实值分布

**多用于 数学 统计学 所以仅介绍常用的函数**

```python
print(random.random())    # 返回 0 <= N <= 1 内的随机浮点数
>>> 0.004982341573777638
```

```python
print(random.uniform(100,50))    # 返回 a <= N <= b (a,b 大小位置不论,可自动更换)
>>> 93.3123155720933
```
