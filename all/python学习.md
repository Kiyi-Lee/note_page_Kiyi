# Python编程：从入门到实践 



## 第一部分 基础知识 

### 第一章 起步 

### 第二章 变量和简单数据类型 

#### 变量的命名与使用 

<p> 由字符、数字、下划线组成。开头不能是数字，不能包括空格，通常用下划线用于分隔单词，尽量将名字设置为具有明确意义性 </p>

#### 字符串

<p> 在python中用引号括起来的都是字符串，其中引号可以是单引号也可以是双引号。 </p>

###### 使用方法修改字符串的大小写 

<p> 方法是python可对数据执行的操作 </p>

- title() 以首字母大写的方式显示每个单词， 即将每个单词的首字母都改为大写
- upper()将字符串大写
- lower()将字符串小写

```python
name = 'test'
print(name)
print(name.title())
print(name.upper())
print(name.lower())

***
	test
	Test
	TEST
	test
***
```

###### 合并拼接字符串

<p> python使用加号（+）拼接字符串 </p>

###### 使用制表符或换行符来添加空白

- \t 添加制表符
- \n 换行

###### 删除空白

- 删除字符串前端多余空白，lstrip()
- 删除字符串后端多余空白，rstrip()
- 删除字符串两端多余空白，strip()

```python
str = ' python '
print(str)
print(str.lstrip())
print(str.rstrip())
print(str.strip())
'''
	 python 
	python 
 	python
	python
'''
```

###### 使用字符串时避免语法错误

#### 数字

###### 整数

<p> 在python中可对整数执行加(+)减(-)乘(*)除(/)运算 </p>

- python中使用 ** 表示乘方运算，使用 // 表示地板除法，使用 % 表示取模运算

```python
print(5/2)
print(5//2)
print(5%2)
'''
    2.5
    2
    1
'''
```

###### 浮点数

<p> python将带有小数点的数都称为浮点数 </p>

###### 使用函数str()避免类型错误

<p> 使用str()将其它数据类型转化为str类型 </p>

###### python2中的整数

<p> 在python2中，整数除法的结果只包含整数部分，小数部分被删除。请注意，计算整数结果时，采取的方法不是四舍五入，而是将小数部分直接删除。 </p>

<p> 在python2中，若要避免这种情况，务必确保至少有一个操作数为浮点数，这样结果也为浮点数 </p>

```python
3 / 2
'''
	1
'''
```

#### 注释

<p> 在python中注释用井号(#)标识 </p>

#### Python之禅

```python
import this
'''
    The Zen of Python, by Tim Peters

    Beautiful is better than ugly.
    Explicit is better than implicit.
    Simple is better than complex.
    Complex is better than complicated.
    Flat is better than nested.
    Sparse is better than dense.
    Readability counts.
    Special cases aren't special enough to break the rules.
    Although practicality beats purity.
    Errors should never pass silently.
    Unless explicitly silenced.
    In the face of ambiguity, refuse the temptation to guess.
    There should be one-- and preferably only one --obvious way to do it.
    Although that way may not be obvious at first unless you're Dutch.
    Now is better than never.
    Although never is often better than *right* now.
    If the implementation is hard to explain, it's a bad idea.
    If the implementation is easy to explain, it may be a good idea.
    Namespaces are one honking great idea -- let's do more of those!
'''
```

### 第三章 列表简介

#### 列表是什么？

<p> 列表 由一系列按特定顺序排列的元素组成 </p>

<p> 在python中用方括号([])来表示列表，并用逗号(,)来分隔其中的元素 </p>

#### 访问列表元素

<p> 列表是有序集合，因此要访问列表的任何元素，只需要将该元素的位置或索引告诉python即可 </p>

<p> 要访问列表元素，可指出列表的名称，再指出元素的索引，并将其放在方括号内。 </p>

**索引从0开始而不是从1开始，可以用索引-1访问最后一个元素，-2访问倒数第二个元素**

#### 使用列表中的各个值

可像使用其他变量一样使用列表中的各个值。

#### 修改、添加和删除元素

##### 修改列表元素

修改列表元素的语法与访问列表元素的语法相似。

要修改列表元素，可指定列表名和要修改的元素的索引，再指定该元素的新值。

```python
foods = ['cake', 'rice', 'noodle']
print(foods)

foods[0] = 'cafe'
print(foods)

'''
	['cake', 'rice', 'noodle']
	['cafe', 'rice', 'noodle']
'''
```

##### 在列表中添加元素

append()在列表尾部添加元素
insert(index,value)可以在任意位置添加元素
extend()添加多个元素

```python
fruits = ['apple', 'orange', 'lemon']
print(fruits)
print(fruits[1])
print(fruits[1].title())
print(fruits[-1].upper())
fruits.append('pear')
print(fruits)

'''
	['apple', 'orange', 'lemon']
    orange
    Orange
    LEMON
    ['apple', 'orange', 'lemon', 'pear']
'''
```

```python
countries = []
countries.append('China')
countries.append('America')
print(countries)
countries.insert(1,'Canada')
print(countries)
countries.extend(['Japan','England'])
print(countries)

'''
	['China', 'America']
    ['China', 'Canada', 'America']
    ['China', 'Canada', 'America', 'Japan', 'England']
'''
```

##### 从列表中删除元素

可以利用del删除列表中元素，前提是知道索引，也可以用del直接删除列表
可以通过remove()通过元素的值删除元素，方法remove() 只删除第一个指定的值。如果要删除的值可能在列表中出现多次，就需要使用循环来判断是否删除了所有这样的值。
可以利用pop()删除元素，默认为尾部，可以输入索引弹出特定值，允许你接着使用它

```python
color = ['red', 'blue', 'black', 'cyan' ,'green']
print(color)
del color[0]
print(color)
color.remove('cyan')
print(color)
pop_color = color.pop(2)
print(pop_color)
print(color)

'''
    ['red', 'blue', 'black', 'cyan', 'green']
    ['blue', 'black', 'cyan', 'green']
    ['blue', 'black', 'green']
    green
    ['blue', 'black']
'''
```

#### 组织列表

##### 使用方法sort()对列表进行永久性排序

使用方法sort() 对列表进行永久性排序，默认为从小到大。可以在括号内添加 reverse=True得到从大到小的列表

##### 使用函数sorted()对列表进行临时排序

使用函数sorted() 对列表进行临时排序，不改变原列表顺序。如果想要按与字母顺序相反的顺序显示列表，也可向函数sorted()传递参数reverse = True

```python
animals = ['pig', 'sheep', 'bird', 'fish']
print(animals)
print('sorted:')
print(sorted(animals))
print(animals)
animals.sort()
print('sort:')
print(animals)
animals.sort(reverse=True)
print('sort(reverse=True):')
print(animals)

'''
    ['pig', 'sheep', 'bird', 'fish']
    sorted:
    ['bird', 'fish', 'pig', 'sheep']
    ['pig', 'sheep', 'bird', 'fish']
    sort:
    ['bird', 'fish', 'pig', 'sheep']
    sort(reverse=True):
    ['sheep', 'pig', 'fish', 'bird']
'''
```



##### 倒着打印列表

方法reverse() 可以逆序列表，会永久性地修改列表元素的排列顺序， 但可随时恢复到原来的排列顺序， 为此只需对列表再次调用reverse() 即可

##### 确定列表的长度

使用函数len()可快速获悉列表的长度

```python
seasons = ['Spring', 'Summer', 'Autumn', 'Winter']
print(seasons)
seasons.reverse()
print(seasons)
seasons.reverse()
print(seasons)
print(len(seasons))

'''
    ['Spring', 'Summer', 'Autumn', 'Winter']
    ['Winter', 'Autumn', 'Summer', 'Spring']
    ['Spring', 'Summer', 'Autumn', 'Winter']
    4
'''
```

##### 使用列表时避免索引错误

### 第四章 操作列表

#### 遍历整个列表

用for循环遍历整个列表

**tips：**

- 选择描述单个列表元素的有意义的名称大有帮助
- 使用单数和复数式名称，可帮助判断代码段处理的是单个列表元素还是整个列表

```python
magicians = ['alice', 'jack', 'ben']
for magician in magicians:
    print(magician.title()+' is a great perfomer!')
    
'''
    Alice is a great perfomer!
    Jack is a great perfomer!
    Ben is a great perfomer!
'''
```

#### 避免缩进错误

#### 创建数值列表

##### 使用函数range()

python函数range()能够轻松地生成一系列数字

```python
for i in range(1, 6):
    print(i)
    
'''
    1
    2
    3
    4
    5
'''
```

##### 使用range()创建数字列表

要创建数字列表，可使用函数list()将range()的结果直接转换为列表。

如果将range()作为list()的参数，输出将为一个数字列表。

```python
numbers = list(range(1, 6))
print(numbers)

'''
    [1, 2, 3, 4, 5]
'''
```

使用函数range()时，还可以指定步长。

```python
# 打印1~10内偶数
even_numbers = list(range(2, 11, 2))
print(even_numbers)

'''
    [2, 4, 6, 8, 10]
'''
```

```python
# 创建一个列表，包括前十个整数(1~10)的平方
squares = []
for value in range(1, 11):
    square = value**2
    squares.append(square)
print(squares)

'''
    [1, 4, 9, 16, 25, 36, 49, 64, 81, 100]
'''

# 优化↑
# 创建一个列表，包括前十个整数(1~10)的平方
squares = []
for value in range(1, 11):
    squares.append(value**2)
print(squares)

'''
    [1, 4, 9, 16, 25, 36, 49, 64, 81, 100]
'''
```

##### 对数字列表执行简单的统计计算

几个专门用于处理数字列表的python函数

```python
digits = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
print(min(digits))
print(max(digits))
print(sum(digits))

'''
    1
    10
    55
'''
```

##### 列表解析

列表解析 将for 循环和创建新元素的代码合并成一行， 并自动附加新元素

```python
squares = [value**2 for value in range(1, 11)]
print(squares)

'''
	[1, 4, 9, 16, 25, 36, 49, 64, 81, 100]
'''

squares = [value**3 for value in range(1, 4)]
print(squares)

'''
    [1, 8, 27]
'''
```

要使用这种语法，首先只当一个描述性的列表名，如squares；然后指定一个左方括号，用于生成你要存储到列表中的值。

在这个示例中，表达式为value**2,它计算平方值。接下来，编写一个for循环，用于给表达式提供值，再加上右方括号。

在这个示例中，for循环为for value in range(1, 11)，它将值1~10提供给表达式value**2。请注意，这里的for语句末尾没有冒号。

#### 使用列表的一部分

##### 切片：处理列表的部分元素

创建切片，可指定第一个元素和最后一个元素的索引。与函数range一样，python在到达你指定第二个索引的前一个元素停止。

通过切片可以得到列表的子集，或者[:]得到列表的拷贝。name[start:end],start默认为0，end默认为结束。

如果没有指定第一个索引，python将自动从列表开头开始。要让切片终止于列表末尾，可省略第二个索引。

负数索引返回离列表末尾相应距离的元素，names[-3:]

```python
players = ['charlie', 'tom', 'lily', 'susan', 'tomas']
print(players[1:])
print(players[1:4])
print(players[:3])
print(players[-3:-1])
print(players[-3:])

'''
    ['tom', 'lily', 'susan', 'tomas']
    ['tom', 'lily', 'susan']
    ['charlie', 'tom', 'lily']
    ['lily', 'susan']
    ['lily', 'susan', 'tomas']
'''
```

##### 遍历切片

如果要遍历列表的部分元素，可在for循环中使用切片。

```python
for player in players[:-3]:
    print(player.title())
    
'''
	Charlie
	Tom
'''
```

##### 复制列表

要复制列表，可创建一个包含整个列表的切片。方法是省略开始索引和终止索引。

```python
my_foods = ['meat', 'crisp', 'garlic', 'watermelon']
print(my_foods)
friend_foods = my_foods[:]
print(friend_foods)
my_foods.append('ice-cream')
print(my_foods)
friend_foods.append('burger')
print(friend_foods)

'''
    ['meat', 'crisp', 'garlic', 'watermelon']
    ['meat', 'crisp', 'garlic', 'watermelon']
    ['meat', 'crisp', 'garlic', 'watermelon', 'ice-cream']
    ['meat', 'crisp', 'garlic', 'watermelon', 'burger']
'''

my_foods = ['meat', 'crisp', 'garlic', 'watermelon']
print(my_foods)
# 行不通
friend_foods = my_foods # 【1】
print(friend_foods)
my_foods.append('ice-cream')
print(my_foods)
print(friend_foods)
friend_foods.append('burger')
print(friend_foods)
print(my_foods)

'''
    ['meat', 'crisp', 'garlic', 'watermelon']
    ['meat', 'crisp', 'garlic', 'watermelon']
    ['meat', 'crisp', 'garlic', 'watermelon', 'ice-cream']
    ['meat', 'crisp', 'garlic', 'watermelon', 'ice-cream']
    ['meat', 'crisp', 'garlic', 'watermelon', 'ice-cream', 'burger']
    ['meat', 'crisp', 'garlic', 'watermelon', 'ice-cream', 'burger']
'''
```

【1】这里将my_foods 赋值给 friend_foods ，而不是将my_foods 副本存储到friend_foods 中。这种语法实际上

是让python 将新变量friend_foods 关联到包含my_foods 中的列表，因此这两个变量都指向同一个列表。

#### 元组

列表适合用于存储在程序运行期间可能变化的数据集，列表是可以修改的。

python将不能修改的值称为不可变的，而不可变的列表被称为元组。

##### 定义元组

不可变的列表被称为元组，通常使用圆括号 () 标识，可以通过索引来访问元素

##### 遍历元组中的程序

同列表一样，元组使用for循环进行遍历

```python
dimensions = (20, 5)
print(dimensions[0])
print(dimensions[1])

for dimension in dimensions:
    print(dimension)
    
'''
    20
    5
    20
    5
'''
```

##### 修改元组变量

虽然不能修改元组的元素， 但可以给存储元组的变量赋值，即可重新定义元组。

```python
dimensions = (20, 5) 
print("Original：")
print(dimensions)
for dimension in dimensions:
	print(dimension)
	
dimensions = (69, 7) 
print("Modified：")
print(dimensions)
for dimension in dimensions:
	print(dimension)
    
'''
    Original：
    (20, 5)
    20
    5
    Modified：
    (69, 7)
    69
    7
'''
```

### 第五章 if语句

#### 条件测试

每条if语句的核心都是一个值为True和False的表达式，这种表达式被称为条件测试。

##### 检查是否相等

使用两个等号（==）——相等运算符，相等时返回True，否则返回False

##### 检查是否相等时不考虑大小写

在python中检查是否相等时区分大小写，例如，两个大小写不同的值会被视为不相等：

```python
car = 'Audi'
car == 'audi'

'''
	False
'''
```

如果大小写无关紧要，只想检查变量的值，可使用lower()函数，将变量的值转换为小写，再进行比较。

函数lower()不会修改存储在变量中car的值。

网站采用类似形式测试用户名唯一性。

##### 检查是否不相等

判断两个值是否不相等使用（!=）

##### 条件语句可使用各种数学比较，例如（>，<，>=，<=）等

##### 检查多个条件

1.使用and检查多个条件

2.使用or检查多个条件

##### 使用关键字 in 检查特定值是否在列表中







