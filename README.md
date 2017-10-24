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
gg


