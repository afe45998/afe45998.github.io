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

## 4.1 遍历整个列表

使用for循环

```python
magicians = ['alice', 'david', 'carolina']
for magician in magicians:
    print(magician)
```

## 4.3 创建数字列表

函数range()可以生成一系列数字

```python
for value in range(1,5)
    print(value)
```

结果是，打印出了数字1-4

### 4.3.2 使用range()创建数字列表

1.创建数字列表，可以使用函数list()将range()的结果直接转换为列表。如果将range()作为list()的参数，输出将为一个数字列表

```python
numbers = list(range(1,6))
print(numbers)
```

结果是，

```python
[1, 2, 3, 4, 5]
```

2.使用函数range()还可以指定步长。如下打印1-10间的偶数

```python
even_number = list(range(2,11,2))
print(even_number)
```

### 4.3.4 列表解析

列表解析将for循环和创建新元素的代码合并成一行，并自动附加新元素。如下，创建平方数列表

```python
squares = [value**2 for value in range(1,11)]

# 或者
squares = []
for value in range(1,11)
    square = value**2
    squares.append(square)
print(squares)
```

要使用列表解析，首先制定一个*描述性*的*列表名*，如squares；然后，制定一个左方括号，并定义一个表达式，用于生成要存储到列表中的值。在该实例中，表达式为value **2。接下来，编写一个for循环，用于给表达式提供值，再加上右方括号。在该实例中，for循环为for value in range(1,11)，它将值1-10提供给表达式value **2。

## 4.4 使用列表的一部分

### 4.4.1 切片

要创建切片，可指定要使用的第一个元素的索引和最后一个元素的索引加1.如下，创建切片

```python
players = ['charles', 'martina', 'michael', 'florence', 'eli']
print(players[0:3]) #  打印包含前三位运动员
print(players[:4]) #  从表头开始至表尾
print(players[2:]) #  从第三个元素到表尾
print(players[-3:]) #  输出名单最后三位

```

### 4.4.2 遍历切片

若要遍历列表的部分元素，可以在for循环中使用切片

```python
players = ['charles', 'martina', 'michael', 'florence', 'eli']

for player in players[:3]:
    print(players.title())

```

### 4.4.3 复制列表

要复制列表，可*创建一个包含整个列表的切片*。简单地将变量赋给变量是没有用的。

```python
my_foods = ['pizza', 'falafel', 'carrot cake']
friend_foods = my_foods[:] #  可行
#  friedn_foods = my_foods 赋值无用

my_foods.append('canoli')
friend_foods.append('ice cream')
```

## 4.5 元组

列表用于存储在程序运行期间可能变化的数据集，即可修改的。Python称不能修改的值为不可变的，而不可变的列表成为元组。

### 4.5.1 定义元组

使用圆括号，类似列表。如下，

```python
dimensions = (200, 50)
print(dimension[0])
print(dimension[1])
```

### 4.5.2 遍历元组中的所有值

与列表一样，使用for循环遍历元组

### 4.5.3 修改元组变量

尽管不能修改元组的元素，但是可以给存储元组的变量*赋值*，如下

```python
dimensions = (200, 50)
print(dimensions)
dimensions = (400, 100)
print(dimensions)
```

# 5. if语句

## 5.2 条件测试

### 5.2.5 检查多个条件

1.使用and检查多个条件

2.使用or检查多个条件

### 5.2.6 检查特定值是否包含在列表中

判断特定的值是否已包含在列表中，可使用关键字in，如下

```bash
>>> requested_toppings = ['mushroom', 'onions', 'pineapple']
>>> 'mushroom' in requested_toppings
True
```

## 5.3 if 语句

### 5.3.1 简单的 if 语句

```python
if conditional_test:
    do something
```

### 5.3.2 if-else 语句

```python
if conditional_test:
    do something
else:
    do something
```

### 5.3.3 if-elif-else 结构

```python
if conditional_test:
    do something
elif:
    do something
else: 
    do something
```

### 5.4.2 确认列表不是空的

在运行for循环前确定列表是否为空很重要

```python
requested_toppings = []

if requested_topping:
    for requested_topping in requested_toppings:
        print("Adding " + requested_topping + ".")
    print("\nFinished making your pizza!")
else:
    print("Are you sure you want a plain pizza?")
```

# 6. 字典

## 6.1 一个简单的字典

alien.py

```python
alien_0 = {'color': 'green', 'points': 5}

print(alien_0['color'])
print(alien_0['points'])
```

## 6.2 使用字典

在python中，字典是一系列*键-值*对，每个键都与一个值关联，可以使用键来访问与之相关联的值。事实上，可以将**任何Python对象作为字典中的值**。

```python
alien_0 = ['color': 'green']
```

### 6.2.1 访问字典中的值

要获取与键相关联的值，可依次指定字典名和放在方括号内的键

```python
alien_0 = ['color': 'green']
print(alien_0['color'])
```

### 6.2.2 添加键值对

字典是一种动态结构，要添加键值对，可依次指定字典名、用方括号起的的键和相关联的值

```python
alien_0 = {'color': 'green', 'points': 5}
print(alien_0)

alien_0['x_positon'] = 0
alien_0['y_postion'] = 25
print(alien_0)
```

### 6.2.3 先创建一个空字典

有时，在空字典中添加键-值对是为了方便，有时则必须如此。

```python
alien_0 = {}

alien_0['color'] = 'green'
alien_0['points'] = 5

print(alien_0)
```

### 6.2.4 修改字典中的值

要修改字典中的值，可依次指定字典名、用方括号括起的键以及与该键相关联的新值

```python
alien_0 = {'color': 'green'}

alien_0['color'] = 'yellow'
print(alien_0)
```

### 6.2.5 删除键值对

使用 del 依据将相应的键值对彻底删除。使用 del 语句时，必须要指定字典名和要删除的键

```python
alien_0 = {'color': 'green', 'points': 5}
print(alien_0)

del alien_0['points']
print(alien_0)
```

### 6.2.6 由类似对象组成的字典

使用字典来存储众多对象的同一信息，如下

```python
favorite_languages = {
    'jen': 'python',
    'sarah': 'c',
    'edward': 'ruby',
    'phil': 'python',
}
```

## 6.3 遍历字典

### 6.3.1 遍历所有的键值对

如下字典存储了一名用户的用户名、姓和名

```python
user_0 = {
    'username': 'efermi',
    'first': 'enrico',
    'last': 'fermi',
}

for key, value in user_0.items():
    print("\nKey: " + key)
    print("Value: " + value)
```

**注意**：方法 items()，它返回一个键-值对列表

### 6.3.2 遍历字典中的所有键

不需要使用字典中的值时，方法 keys() 很有用。如下

```python
favorite_languages = {
    'jen': 'python',
    'sarah': 'c',
    'edward': 'ruby',
    'phil': 'python',
}

for name in favorite_languages.keys():
    print(name.title())
```

结果是，输出代码提取字典favorite_languages中的所有键，并依次将他们存储到遍历变量name中。同时，遍历字典时，会默认遍历所有的键，因此，上述代码可以替换成 for name in favorite_languages:，输出不变。

### 6.3.3 按顺序遍历字典中的所有值

字典总是明确地记录键值之间的关联关系，但获取字典的元素时，获取顺序是不可预测的。要以特定的顺序返回元素，一种方法便是在 for 循环中对返回的键进行排序，可以使用函数 sorted() 来获得按特定顺序排列的键列表的副本

```python
favorite_languages = {
    'jen': 'python',
    'sarah': 'c',
    'edward': 'ruby',
    'phil': 'python',
}

for name in sorted(favorite_languages.keys()):
    print(name.title())
```

### 6.3.4 遍历字典中的所有值

使用方法 values() 它返回一个值列表，而不包含任何建。但是这种做法提取了字典中的所有值，没有考虑是否重复。为剔除重复项，可使用集合 set，集合类似于列表，但每个元素都必须是独一无二的

```python
favorite_languages = {
    'jen': 'python',
    'sarah': 'c',
    'edward': 'ruby',
    'phil': 'python',
}

for language in set(favorite_languages.values()):
    print(name.title())
```

## 6.4 嵌套

### 6.4.1 字典列表

字典 alien_0 包含了一个外星人的各种信息，但是无法管理成群结队的外星人。如下，创建一个包含三个外星人的列表

```python
alien_0 = {'color': 'green', 'points': 5}
alien_1 = {'color': 'yellow', 'points': 10}
alien_2 = {'color': 'red', 'points': 15}

aliens = [alien_0, alien_1, alien_2]

for alien in aliens:
    print(alien)
```

### 6.4.2 在字典中存储列表

将列表存储在字典中。如下，存储了比萨的两方面信息：外皮类型和配料列表。其中的配料列表是一个与键'topping'相关联的值。要访问该列表，我们使用字典名和键'toppings'。这将返回一个配料列表，而不是单个值。

pizza.py

```python
pizza = {
    'crust': 'thick',
    'toppings': ['mushrooms', 'extra cheese'],
}
```

结果，每当需要在**字典中将一个键关联到多个值时，都可以在字典中嵌套一个列表**。

### 6.4.3 在字典中存储字典

可以在字典中嵌套字典。例如，如果有多个网站用户，每个都有独特的用户名，可在字典中将用户名作为键，然后将每位用户的信息