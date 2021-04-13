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

可以在字典中嵌套字典。例如，如果有多个网站用户，每个都有独特的用户名，可在字典中将用户名作为键，然后将每位用户的信息存储在一个字典中，并将该字典作为与用户名相关联的值。如下，对于每位用户，我们都存储了其三项信息：名、姓和居住地；为访问这些信息，我们遍历所有的用户名，并访问与每个用户名相关两的信息字典

```python
users = {
    'aeinstein': {
        'first': 'albert',
        'last': 'einstein',
        'location': 'princeton',
    },

    'mcurie': {
        'first': 'marie',
        'last': 'curie',
        'location': 'paris',
    },

}
```

# 7. 用户输入和while循环

## 7.1 函数 input() 的工作原理

函数 input() 让程序暂停运行，等待用户输入一些文本。获取用户输入后，Python将其存储在一个变量中以便使用

```python
message = input("Tell me something, and I will repeat it back to you: ")
print(message)
```

有时，提示可能超过一行，此时可以将提示存储在一个变量中，再将该变量传递给函数 input()

```python
prompt = "If you tell me who you are, we can personlize the messages you see."
prompt += "\nWhat is your first name? "
```

结果显示如下，

```python
If you tell me who you are, we can personalize the messages you see.
What is your first name? Eric

Hello, Eric!
```

### 7.1.2 使用 int() 来获取数值输入

使用函数 input() 时，Python将用户输入解读为字符串

```bash
>>> age = input("How old are you?")
How old are you?
>>> age
'21'
```

函数 int() 将数字的字符串转换为数值表示，如下

```bash
>>> age = input("How old are you?")
How old are you? 21
>>> age = int(age)
>>> age >= 18
True
```

## 7.2 while循环简介

### 7.2.1 使用while循环

使用while循环输出1~5

```python
current_number = 1
while current_number <=5:
    print(current_number)
    current_number += 1
```

### 7.2.3 使用标志(flag)

在要求很多条件都满足才能继续运行的程序中，可定义一个变量，用于判断整个程序是否处于活动状态，这个变量成为**标志**，可以让程序在标志为 True 时继续运行，并在任何事件导致标志的值为 False 时让程序停止运行

```python
prompt = "If you tell me who you are, we can personlize the messages you see."
prompt += "\nWhat is your first name? "

active = True
while active:
    message = input(prompt)

    if message = 'quit':
        active = False
    else:
        print(message)
```

### 7.2.4 break与continue

break: 立即退出while循环，不再运行 循环中余下的代码，也不管条件测试结果如何

continue: 要返回到循环开头，并根据条件测试结果决定是否继续执行循环

## 7.3 使用while循环来处理列表和字典

for循环是一种遍历列表的有效方式，但在for循环中不应修改列表，否则将导致Python难以跟踪其中的元素。要在遍历列表的同时对其进行修改，可使用while循环。

通过将while循环同列表和字典结合起来使用，,可收集、存储并组织大量输入，供以后查看和显示

### 7.3.1 在列表之间移动元素

使用一个while循环，在验证用户的同时将其从未验证用户列表中提取出来，再将其加入到另一个已验证用户列表中

```python
unconfirmed_users = ['alice', 'brian', 'candace']
confirmed_users = []

while unconfirmed_users:
    current_user = unconfirmed_users.pop()
    confirmed_users.append(current_user)
```

### 7.3.2 删除包含特定值的所有列表元素

第三章中使用了 remove() 来删除列表中的特定值，前提是要删除的值再列表中只出现了一次

要删除所有这类元素，可不断运行一个while循环，直到列表不再包含值'cat'

```python
pets = ['dog', 'cat', 'dog', 'goldfish', 'cat', 'rabbit', 'cat']
print(pets)

while 'cat' in pets:
    pets.remove('cat')

print(pets)
```

### 7.3.3 使用用户输入来填充字典

可使用while循环提示用户输入任意数量的信息

下面创建一个调查程序，其中的循环每执行时都提示输入被调查者的名字和回答

```python
responses = []
# 设置一个标志，指出调查是否继续
polling_active = True

while polling_active:
    # 提示输入被调查者的名字和回答
    name = input("\nWhat is your name?")
    response = input("Which moutain would you like to climb someday? ")
    # 将答卷存储在字典中
    responses[name] = response
    # 看是否还有人要参与调查
    repeat = input("Would you like to let another person respond? (yes/no) ")
    if repeat == 'no':
        polling_active = False

# 调查结束，显示结果
print("\n--- Poll Results ---")
for name, response in responses.items():
    print(name + " would like to climb " + response + ".")
```

# 8. 函数

## 8.1 定义函数

关键字def、函数名、括号、定义以结尾冒号结束

"""xxx""" 为文档字符串(docstring)

```python
def greet_user():
    """显示简单的问候语"""
    print("Hello")

greet_user()
```

### 8.1.1 向函数传递信息

在函数定义def greet_user()的括号内添加username，通过在这里添加username，可以让函数接受给username指定的任意值

```python
def greet_user(username):
    print("Hello, " + username.title() + "!")

greet_user('jesse')
```

结果，

```python
Hello, Jesse!
```

### 8.1.2 实参与虚参

在上面greet_user()的定义中，变量username是一个形参————**函数完成其工作所需的一项信息**

在代码greet_user('jesse')中，值'jesse'是一个实参————**调用函数时传递给函数的信息**

我们调用函数时，将要让函数使用的信息放在括号中内。在greet_user('jesse')中，将实参'jesse'传递给了函数greet_user()，这个值被存储在形参username中

## 8.2 传递实参

函数定义中可能有多个形参，故函数调用中也可能包含多个实参。向函数传递实参的方式：

1.位置实参：要求实参的顺序与形参的顺序相同

2.关键字实参：其中每个实参都由变量名和值组成

3.还可以使用列表和字典

### 8.2.1 位置实参

在调用函数过程中，Python必须将函数调用中的每个实参都关联到函数定义中的一个形参。为此，最简单的关联方式是基于实参的顺序————位置实参

```python
def describe_pet(animal_type, pet_name):
    """显示宠物的信息"""
    print("\nI have a " + animal_type + ".")
    print("My " + animal_type + "'s name is " + pet_name.title() + ".")

describe_pet('hamster', 'harry')
```

函数的定义表明，需要一种动物类型和一个名字。调用describe_pet()时，，需要按顺序提供一种动物类型和一个名字。如上述，实参'hamster'存储在形参animal_type中，而实参'harry'存储在形参pet_name中。

结果，输出描述了一只名为Harry的仓鼠

1.调用函数多次

```python
def describe_pet(animal_type, pet_name):
    """显示宠物的信息"""
    print("\nI have a " + animal_type + ".")
    print("My " + animal_type + "'s name is " + pet_name.title() + ".")

describe_pet('hamster', 'harry')

describe_pet('dog', 'willie')
```

在函数中，可根据需要次数使用任意数量的位置实参，Python将按顺序将函数调用中的实参关联到函数定义中相应的形参

2.位置实参的顺序很重要

### 8.2.2 关键字实参

关键字实参时传递给函数的名称-值对。关键字实参使我们无需考虑函数调用中的实参顺序，还清楚地指出了函数调用中各个值的用途

```python
def describe_pet(animal_type, pet_name):
    """显示宠物的信息"""
    print("\nI have a " + animal_type + ".")
    print("My " + animal_type + "'s name is " + pet_name.title() + ".")

describe_pet(animal_type='hamster', pet_name='harry')
# 等价于
describe_pet(pet_name='harry', animal_type='hamster')
```

关键字实参的顺序无关紧要，弹药准确地指定函数定义中的形参名

### 8.2.3 默认值

在调用函数中给形参提供了实参时，Python将使用指定的实参值；否则，则使用形参的默认值

```python
def describe_pet(pet_name, animal_type='dog'):
    """显示宠物的信息"""
    print("\nI have a " + animal_type + ".")
    print("My " + animal_type + "'s name is " + pet_name.title() + ".")

# describe_pet('hamster', 'harry')

describe_pet('dog', 'willie')
```

注意，在这个函数定义中，修改了形参的排列顺序。由于给animal_type指定了默认值，无需通过实参来指定动物类型，因此在函数调用中只包含一个实参————宠物的名字。但是，Python仍将这个实参视为位置实参，因此如果函数调用中只包含宠物的名字，这个实参将关联到函数定义中的第一个形参。这就是将pet_name放在形参列表开头的原因。

1.在调用中只提供小狗的名字

```python
describe_pet('willie')
```

只提供了一个实参————'willie'，这个实参将关联到函数定义中的第一个形参————pet_name。由于没有给animal_type提供实参，因此Python使用其默认值'dog'

2.描述的不是小狗

```python
describe_pet(pet_name='harry', animal_type='hamster')
```

由于显式地给animal_type提供了实参，因此Python将忽略这个形参的默认值

### 8.2.4 等效的函数调用

可以混合使用位置实参、关键字实参和默认值

```python
def describe_pet(pet_name, animal_type='dog'):

# 一条名为Willie的小狗
describe_pet('willie')
describe_pet(pet_name='willie')

# 一只名为Harry的仓鼠
describe_pet('harry','hamster')
describe_pet(pet_name='harry', animal_type='hamster')
describe_pet(animal_type='hamster', pet_name='harry')
```

这些函数调用都可以

## 8.3 返回值

在函数中，可使用return语句将值返回到调用函数的代码行。

### 8.3.1 返回简单值

函数接受名和姓并返回整洁的姓名:

```python
def get_formatted_name(first_name, last_name):
    """返回整洁的姓名"""
    full_name = first_name + last_name
    return full_name.title()

musician = get_formatted_name('jimi', 'hendrix')
print(musician)
```

结果，

```python
Jimi Hendrix
```

### 8.3.2 让实参变成可选的

可通过使用默认值来让实参变成可选的

扩展get_formatted_name，使其还处理中间名

```






























