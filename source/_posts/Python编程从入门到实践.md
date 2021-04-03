---
layout: pose
title: Python编程从入门到实践
date: 2021-03-26 16:24:04
tags: [Python, 编程语言入门]
categories: Python
---
前言，该博客记录了我从2021.4.3，自颓废10周之久后,打算开始完成毕业设计的过程。想到什么就补充什么吧。
# 2. 变量和简单数据类型
## 2.1 运行 hello_Python.py 时发生的情况
1. 编辑器会使用Python解释器运行.py文件
## 2.3.1 使用方法修改字符串的大小写
1. .title() 以首字母大写的方式显示每个单词， .upper()， .lower() 将字符串改为全部大写或全部小写
## 2.3.2 合并字符串
1. Python使用 “+” 完成拼接字符串
## 2.3.4 删除空白
1. Python能够找出字符串开头和末尾多余的空白。要确保字符串末尾没有空白，可使用方法 .rstrip()， 可以删除字符串开头的空白，或者剔除字符串两端的空白，分别使用 .lstrip() 和 .strip()
## 2.4.3 使用函数 str()避免类型错误
1. 函数 str() 可以让Python将非字符串值表示为字符串
```python
age = 23
message = "Happy " + str(age) + "rd Birthday!"
print(message)
```
## 2.5.1 编写注释
1. 注释用 # 标识



<!--more-->