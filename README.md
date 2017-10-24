# Python-100
100道Python编程题

#1：有1、2、3、4个数字，能组成多少个互不相同且无重复数字的三位数？都是多少？
```Python
m=0
for i in range(1,5):
    for j in range(1,5):
        for k in range(1,5):
            if(i!=j)and(i!=k)and(j!=k):
                m+=1
                print(i,j,k,m)
print("次数是m",format(m))
```
#2： 整型、浮点型、字符串型如何定义和格式化的方法？
```Python
age = 20
name = 'Swaroop'

print('{0} was {1} years old when he wrote this book'.format(name, age))
print('Why is {0} playing with that python?'.format(name))

Swaroop was 20 years old when he wrote this book
Why is Swaroop playing with that python?
```

#3： 转义序列（Escape Sequence） 如何输出特殊字符串？

你想要的字符串是 "What's your name?"

包含单引号（'）的字符串，你应该如何指定这串字符串？

方法1：你通过 \ 来指定单引号：要注意它可是反斜杠。现在，你可以将字符串指定为 'What\'s your name?'。<br />
方法2： 双引号 这样的： "What's your name?"

|    转义序列    | 实际含义 |举例 |
| ------- | --- |--- |
| \\ |  指定反斜杠本身 ||
| \n |  表示新一行的开始 |'This is the first line\nThis is the second line'|
| \t |  制表符 ||
| \' |  单引号 ||
| \" |  双引号 ||
| \r |  回车 ||
| \ |  一个放置在末尾的反斜杠表示字符串将在<br />下一行继续，但不会添加新的一行。 |"This is the first sentence. <font color=red>反斜杠</font>This is the second sentence."<br />相当于<br />"This is the first sentence. This is the second sentence."|

#4: 什么是Python中的“u”和“r”字符串标记，什么是raw字符串文字？
```Python
>>> p1 = "pattern"
>>> p2 = u"pattern"
>>> p3 = r"pattern"
>>> p4 = ur"pattern" # it's ur"", not ru"" btw
>>> p1 == p2 == p3 == p4
True
```
While these constructs look different, they all do the same thing.they create a string object<br />
p1 and p3 a str and p2 and p4 a unicode object in Python 2.x, containing the value "pattern".<br />
The u,  r and ur just tell the parser, how to interpret the following quoted string, namely as a unicode text (u) and/or a raw text (r) where backslashes to encode other characters are ignored. <br />
However in the end it doesn't matter how a string was created, being it a raw string or not, internally it is stored the same.

#5： 字符串如何连接和复制？
```Python
>>> 'Elsa' + 'mandy'
>>> 'Elsamandy'
```
> *错误示范*
```Python
>>> 'Elsa' + 100  # Elsa同学加100块钱
TypeError:Cannot convert 'int' object to str implictly
```
接下来呢？
```Python
>>> 'Elsa' * 5
>>> 'ElsaElsaElsaElsaElsa'
```
* 操作符用于一个字符串和一个整型值时，变成了"字符串复制"操作符。

#6： 变量中的赋值语句？
```Python
>>>spam = 40
>>> spam
40
>>> eggs = 2
>>> eggs + spam
42
>>> eggs + spam + spam
?
>>> spam= spam + 2
?
>>> spam= 'Hello'
?
```
>变量只需被赋予某一值。不需要声明或定义数据类型。

#7：变量名的规则有哪些？<br />
1.只能一个词。<br />
2.只能包含字母、数字和下划线。<br />
3.不能以数字开头。<br />
spam\SPAM\Spam\SpAm 是4个不同的变量，小写字母开头是Python的惯例。


#8： print()函数输出括号内的字符串？
```Python
i = 5
print(i)
i = i + 1
print(i)

s = '''This is a multi-line string.
This is the second line.'''
print(s)


输出：

5
6
This is a multi-line string.
This is the second line.

```
#9： 缩进（Indentation）与块（block）重要吗？

空白区6在 Python 中十分重要。实际上，空白区在各行的开头非常重要。这被称作 缩进（Indentation）。在逻辑行的开头留下空白区（使用空格或制表符）用以确定各逻辑行的缩进级别，而后者又可用于确定语句的分组。
这意味着放置在一起的语句必须拥有相同的缩进。每一组这样的语句被称为 块（block）。我们将会在后文章节的案例中了解块这一概念是多么重要。

> 有一件事你需要记住：错误的缩进可能会导致错误。
```Python
i = 5
# 下面将发生错误，注意行首有一个空格
 print('Value is', i)
print('I repeat, the value is', i)

当你运行这一程序时，你将得到如下错误：
  File "whitespace.py", line 3
    print('Value is', i)
    ^
IndentationError: unexpected indent   # 缩进错误：意外缩进
```

>如何缩进

>使用四个空格来缩进。这是来自 Python 语言官方的建议。好的编辑器会自动为你完成这一工作。请确保你在缩进中使用数量一致的空格，否则你的程序将不会运行，或引发不期望的行为。

>针对静态编程语言程序员的提示

>Python 将始终对块使用缩进，并且绝不会使用大括号。你可以通过运行 from __future__ import braces 来了解更多信息。


#10: 如何在屏幕输出自己的名字？ input() len()
```Python
myName = input()
print('It is good to meet you,' + myName)
len(myName)
?
```
#11： 文本和数字是否相等？

```Python
>>> 42 == '42'
False
>>>42 == 42.0
True
>>> 42.0 == 0042.00
True
```
字符串是文本，整型和浮点型是数字。

#12: 四则运算有哪些？

### 算术运算符 


|    运算符    | 描述 |实例 |
| ---------- | --- |--- |
| + |  加 - 两个对象相加 |a + b 输出结果 30 |
| - |  减 - 得到负数或是一个数减去另一个数 |a - b 输出结果 -10 |
| * |  乘 - 两个数相乘或是返回一个被重复若干次的字符串 |a * b 输出结果 200 |
| / |  除 - x除以y|b / a 输出结果 2 |
| % |  取模 - 返回除法的余数 |b % a 输出结果 0 |
| // | 取整除 - 返回商的整数部分  | 9//2 输出结果 4 , 9.0//2.0 输出结果 4.0|


```Python

# !python2
#!/usr/bin/python
# -*- coding: UTF-8 -*-
 
a = 21
b = 10
c = 0
 
c = a + b
print "1 - c 的值为：", c
 
c = a - b
print "2 - c 的值为：", c 
 
c = a * b
print "3 - c 的值为：", c 
 
c = a / b
print "4 - c 的值为：", c 
 
c = a % b
print "5 - c 的值为：", c
 
# 修改变量 a 、b 、c
a = 2
b = 3
c = a**b 
print "6 - c 的值为：", c
 
a = 10
b = 5
c = a//b 
print "7 - c 的值为：", c



1 - c 的值为： 31
2 - c 的值为： 11
3 - c 的值为： 210
4 - c 的值为： 2
5 - c 的值为： 1
6 - c 的值为： 8
7 - c 的值为： 2
```
注意：Python2.x 里，整数除整数，只能得出整数。如果要得到小数部分，把其中一个数改成浮点数即可。
```Python
>>> 1/2
0
>>> 1.0/2
0.5
>>> 1/float(2)
0.5
```
### 比较运算符 

|    运算符    | 描述 |实例 |
| ---------- | --- |--- |
| == |  等于 - 比较对象是否相等 |(a == b) 返回 False。 |
| != |  不等于 - 比较两个对象是否不相等 |(a != b) 返回 true. |
| <> |  不等于 - 比较两个对象是否不相等 |(a <> b) 返回 true。这个运算符类似 != 。 |
| > | 大于 - 返回x是否大于y|(a > b) 返回 False。 |
| < |  小于 - 返回x是否小于y。所有比较运算符返回1表示真，返回0表示假。<br />这分别与特殊的变量True和False等价。注意，这些变量名的大写。 |(a < b) 返回 true|
| >= | 大于等于	- 返回x是否大于等于y。  | (a >= b) 返回 False。|
| <= | 小于等于 - 返回x是否小于等于y。  | (a <= b) 返回 true。|

```Python

#! Python2
#!/usr/bin/python
# -*- coding: UTF-8 -*-
 
a = 21
b = 10
c = 0
 
if ( a == b ):
   print "1 - a 等于 b"
else:
   print "1 - a 不等于 b"
 
if ( a != b ):
   print "2 - a 不等于 b"
else:
   print "2 - a 等于 b"
 
if ( a <> b ):
   print "3 - a 不等于 b"
else:
   print "3 - a 等于 b"
 
if ( a < b ):
   print "4 - a 小于 b" 
else:
   print "4 - a 大于等于 b"
 
if ( a > b ):
   print "5 - a 大于 b"
else:
   print "5 - a 小于等于 b"
 
# 修改变量 a 和 b 的值
a = 5
b = 20
if ( a <= b ):
   print "6 - a 小于等于 b"
else:
   print "6 - a 大于  b"
 
if ( b >= a ):
   print "7 - b 大于等于 a"
else:
   print "7 - b 小于 a"
   
以上实例输出结果：

1 - a 不等于 b
2 - a 不等于 b
3 - a 不等于 b
4 - a 大于等于 b
5 - a 大于 b
6 - a 小于等于 b
7 - b 大于等于 a

```

### 赋值运算符

|    运算符    | 描述 |实例 |
| ---------- | --- |--- |
| = |  赋值运算符 |c = a + b 将 a + b 的运算结果赋值为 c |
| += |  加法赋值运算符 |c += a 等效于 c = c + a |
| -= |  减法赋值运算符 |c -= a 等效于 c = c - a |
| * = | 乘法赋值运算符|c * = a 等效于 c = c * a |
| /= |  除法赋值运算符 |c /= a 等效于 c = c / a|
| %= | 取模赋值运算符  | c %= a 等效于 c = c % a|
| //= | 取整除赋值运算符  | c //= a 等效于 c = c // a|

```Python
#!/usr/bin/python
# -*- coding: UTF-8 -*-
 
a = 21
b = 10
c = 0
 
c = a + b
print "1 - c 的值为：", c
 
c += a
print "2 - c 的值为：", c 
 
c *= a
print "3 - c 的值为：", c 
 
c /= a 
print "4 - c 的值为：", c 
 
c = 2
c %= a
print "5 - c 的值为：", c
 
c **= a
print "6 - c 的值为：", c
 
c //= a
print "7 - c 的值为：", c

以上实例输出结果：

1 - c 的值为： 31
2 - c 的值为： 52
3 - c 的值为： 1092
4 - c 的值为： 52
5 - c 的值为： 2
6 - c 的值为： 2097152
7 - c 的值为： 99864

```


