---
layout: pose
title: Python编程从入门到实践
date: 2021-03-26 16:24:04
tags: [Python, 编程语言入门]
categories: Python
---
前言，该博客记录了我从2021.4.3，自颓废10周之久后,打算开始完成毕业设计的过程。想到什么就补充什么吧。首先便是真正开始学习Python之路。

# 2. 变量和简单数据类型

## 2.1 运行 hello_Python.py 时发生的情况

编辑器会使用Python解释器运行.py文件
<!--more-->
### 2.3.1 使用方法修改字符串的大小写

.title() 以首字母大写的方式显示每个单词， .upper()， .lower() 将字符串改为全部大写或全部小写

### 2.3.2 合并字符串

Python使用 “+” 完成拼接字符串

### 2.3.4 删除空白

Python能够找出字符串开头和末尾多余的空白。要确保字符串末尾没有空白，可使用方法 .rstrip()， 可以删除字符串开头的空白，或者剔除字符串两端的空白，分别使用 .lstrip() 和 .strip()

### 2.4.3 使用函数 str()避免类型错误

函数 str() 可以让Python将非字符串值表示为字符串

```python
age = 23
message = "Happy " + str(age) + "rd Birthday!"
print(message)
```

### 2.5.1 编写注释

注释用 # 标识

# 3. 列表简介

## 3.1 列表是什么

列表由一系列按特定顺序排列的元素组成

```python
bicycles = ['trek', 'redline', 'cannondale']
print(bicycles)
```

### 3.1.1 访问列表元素

从列表bicycles中提取第一款自行车

```python
bicycles = ['trek', 'redline', 'cannondale']
print(bicycles[0])
```

## 3.2 修改、添加和删除元素

### 3.2.1 修改列表元素

假设一个摩托车列表，修改其中第一个元素 ‘honda’

```python
motorcycles = ['honda', 'yamaha', 'suzuki']
print(motorcycles)

motorcycles[0] = 'ducati'
print(motorcycles)
```

### 3.2.2 在列表中添加元素

1.列表末尾添加元素
方法 .append()让动态地创建列表更加简单

```python
motorcycles = ['honda', 'yamaha', 'suzuki']
print(motorcycles)

motorcycles.append('ducati')
print(motorcycles)
```

2.在列表中插入元素
使用方法 .insert()可以在列表的任意位置添加新元素，但是为此需要新元素的索引和值

```python
motorcycles = ['honda', 'yamaha', 'suzuki']

motorcycles.insert(0, 'ducati')
print(motorcycles)
```

结果是，值 'ducati' 被插入到了列表开头，这种操作将列表中的既有的每个元素都右移一个位置

### 3.2.3 从列表中删除元素

1.使用 del 语句删除元素
del 可以删除任何位置处的列表元素，条件是知道其索引

```python
motorcycles = ['honda', 'yamaha', 'suzuki']

del motorcycles[0]
print(motorcycles)
```

2.使用方法 pop() 删除元素
方法pop()可删除列表末尾的元素，并能够接着使用它（类似栈中弹出栈顶元素）

```python
motorcycles = ['honda', 'yamaha', 'suzuki']
print(motorcycles)

popped_motorcycle = motorcycles.pop()
print(motorcycles)
print(popped_motorcycle)
```

3.弹出列表中任何位置处的元素
实际上， pop()可以来删除列表中的任何位置的元素，只需在括号中指定要删除的元素的索引即可

```python
motorcycles = ['honda', 'yamaha', 'suzuki']

first_owned = motorcycles.pop(0)
print(motorcycles)
```

结果是，我们弹出了列表中的第一款摩托车，当使用 pop() 时，被弹出的元素就不在列表中了

4.根据值删除元素
只知道要删除的元素的值时，可以使用方法 remove()

```python
motorcycles = ['honda', 'yamaha', 'suzuki', 'ducati']

motorcycles.remove('ducati')
print(motorcycles)
```

使用 remove() 从列表中删除元素的值时，也可以接着使用它的值

```python
motorcycles = ['honda', 'yamaha', 'suzuki', 'ducati']

too_expensive = 'ducati'
motorcycles.remove(too_expensive)
print(motorcycles)
print("\nA " + too_expensive.title() + " is too expensive for me.")
```

## 3.3 组织列表

### 3.3.1 使用方法 sort() 对列表进行永久性排序

Python方法 sort() 能够较为轻松的对列表进行排序。假设一个汽车列表，令其所有值都是小写的，按照字母顺序排列

```python
cars = ['bmw', 'audi', 'toyota', 'subaru']
cars.sort()
print(cars)
```

结果是，方法 sort() 永久性地修改了列表元素的排列顺序。同时，也可以按与字母顺序相反的顺序排列列表元素，为此，只需向 sort() 方法中传递参数 reverse=True 即可

### 3.3.2 使用函数 sorted() 列表进行临时排序

```python
cars = ['bmw', 'audi', 'toyota', 'subaru']

print(cars)
print(sorted(cars))
print(cars)
```

### 3.3.3 倒着打印列表

要反转列表元素的排列顺序，可使用方法 reverse()

```python
cars = ['bmw', 'audi', 'toyota', 'subaru']
print(cars)

cars.reverse()
print(cars)
```

注意， reverse() 不是指按与字母顺序相反的顺序排列列表元素，而是反转列表的排列顺序

### 3.3.4 确定列表的长度

使用函数 len() 可以快速获悉列表的长度

```python
cars = ['bmw', 'audi', 'toyota', 'subaru']
len(cars)
```

# 4. 操作列表

