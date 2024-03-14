## 这里有python入门的120个基础练习（1~40），希望对你有用。

## 01-Hello World

> python的语法逻辑完全靠缩进，建议缩进4个空格。 如果是顶级代码，那么必须顶格书写，哪怕只有一个空格也会有语法错误。 下面示例中，满足if条件要输出两行内容，这两行内容必须都缩进，而且具有相同的缩进级别。

```text
print('hello world!')
	
	if 3 > 0:
	    print('OK')
	    print('yes')
	
	x = 3; y = 4   # 不推荐，还是应该写成两行
	print(x + y)
```

## 02-print

```text
	print('hello world!')
	print('hello', 'world!')  # 逗号自动添加默认的分隔符：空格
	print('hello' + 'world!')  # 加号表示字符拼接
	print('hello', 'world', sep='***')  # 单词间用***分隔
	print('#' * 50)  # *号表示重复50遍
	print('how are you?', end='') # 默认print会打印回车，end=''表示不要回车
```

## 03-基本运算

运算符可以分为：算术运算符、比较运算符和逻辑运算符。优先级是：算术运算符>比较运算符>逻辑运算符。最好使用括号，增加了代码的可读性。

```text
	print(5 / 2)  # 2.5
	print(5 // 2)  # 丢弃余数，只保留商
	print(5 % 2)  # 求余数
	print(5 ** 3)  # 5的3次方
	print(5 > 3)  # 返回True
	print(3 > 5)  # 返回False
	print(20 > 10 > 5)  # python支持连续比较
	print(20 > 10 and 10 > 5)  # 与上面相同含义
	print(not 20 > 10)  # False
```

## 04-input

```text
	number = input("请输入数字: ")  # input用于获取键盘输入
	print(number)
	print(type(number))  # input获得的数据是字符型
	
	print(number + 10)  # 报错，不能把字符和数字做运算
	print(int(number) + 10)  # int可将字符串10转换成数字10
	print(number + str(10))  # str将10转换为字符串后实现字符串拼接
```



## 05-输入输出基础练习

```text
	username = input('username: ')
	print('welcome', username)   # print各项间默认以空格作为分隔符
	print('welcome ' + username)  # 注意引号内最后的空格
```



## 06-字符串使用基础

> python中，单双引号没有区别，表示一样的含义

```text
sentence = 'tom\'s pet is a cat'  # 单引号中间还有单引号，可以转义
	sentence2 = "tom's pet is a cat"  # 也可以用双引号包含单引号
	sentence3 = "tom said:\"hello world!\""
	sentence4 = 'tom said:"hello world"'
	# 三个连续的单引号或双引号，可以保存输入格式，允许输入多行字符串
	words = """
	hello
	world
	abcd"""
	print(words)
	
	py_str = 'python'
	len(py_str)  # 取长度
	py_str[0]  # 第一个字符
	'python'[0]
	py_str[-1]  # 最后一个字符
	# py_str[6]  # 错误，下标超出范围
	py_str[2:4]  # 切片，起始下标包含，结束下标不包含
	py_str[2:]  # 从下标为2的字符取到结尾
	py_str[:2]  # 从开头取到下标是2之前的字符
	py_str[:]  # 取全部
	py_str[::2]  # 步长值为2，默认是1
	py_str[1::2]  # 取出yhn
	py_str[::-1]  # 步长为负，表示自右向左取
	
	py_str + ' is good'  # 简单的拼接到一起
	py_str * 3  # 把字符串重复3遍
	
	't' in py_str  # True
	'th' in py_str  # True
	'to' in py_str  # False
	'to' not in py_str  # True
```



## 07-列表基础

> 列表也是序列对象，但它是容器类型，列表中可以包含各种数据

```text
	**alist = [10, 20, 30, 'bob', 'alice', [1,2,3]]
	len(alist)
	alist[-1]  # 取出最后一项
	alist[-1][-1]  # 因为最后一项是列表，列表还可以继续取下标
	[1,2,3][-1]  # [1,2,3]是列表，[-1]表示列表最后一项
	alist[-2][2]  # 列表倒数第2项是字符串，再取出字符下标为2的字符
	alist[3:5]   # ['bob', 'alice']
	10 in alist  # True
	'o' in alist  # False
	100 not in alist # True
	alist[-1] = 100  # 修改最后一项的值
	alist.append(200)  # 向**列表中追加一项
```



## 08-元组基础

> 元组与列表基本上是一样的，只是元组不可变，列表可变。

```text
	atuple = (10, 20, 30, 'bob', 'alice', [1,2,3])
	len(atuple)
	10 in atuple
	atuple[2]
	atuple[3:5]
	# atuple[-1] = 100  # 错误，元组是不可变的
```



## 09-字典基础

```text
	# 字典是key-value(键－值）对形式的，没有顺序，通过键取出值
	adict = {'name': 'bob', 'age': 23}
	len(adict)
	'bob' in adict  # False
	'name' in adict  # True
	adict['email'] = 'bob@tedu.cn'  # 字典中没有key，则添加新项目
	adict['age'] = 25  # 字典中已有key，修改对应的value
```



## 10-基本判断

> 单个的数据也可作为判断条件。 任何值为0的数字、空对象都是False，任何非0数字、非空对象都是True。

```text
	if 3 > 0:
	    print('yes')
	    print('ok')
	
	if 10 in [10, 20, 30]:
	    print('ok')
	
	if -0.0:
	    print('yes')  # 任何值为0的数字都是False
	
	if [1, 2]:
	    print('yes')  # 非空对象都是True
	
	if ' ':
	    print('yes')  # 空格字符也是字符，条件为True
```

## 11-条件表达式、三元运算符

```text
	a = 10
	b = 20
	
	if a < b:
	    smaller = a
	else:
	    smaller = b
	
	print(smaller)
	
	s = a if a < b else b  # 和上面的if-else语句等价
	
	print(s)
```



## 12-判断练习：用户名和密码是否正确

```text
	import getpass  # 导入模块
	
	username = input('username: ')
	# getpass模块中，有一个方法也叫getpass
	password = getpass.getpass('password: ')
	
	if username == 'bob' and password == '123456':
	    print('Login successful')
	else:
	    print('Login incorrect')
```



## 13-猜数：基础实现

```text
	import random
	
	num = random.randint(1, 10) # 随机生成1－10之间的数字
	answer = int(input('guess a number: '))  # 将用户输入的字符转成整数
	if answer > num:
	    print('猜大了')
	elif answer < num:
	    print('猜小了')
	else:
	    print('猜对了')
	
	print('the number:', num)
```



## 14-成绩分类1

```text
	score = int(input('分数: '))
	
	if score >= 90:
	    print('优秀')
	elif score >= 80:
	    print('好')
	elif score >= 70:
	    print('良')
	elif score >= 60:
	    print('及格')
	else:
	    print('你要努力了')
```



## 15-成绩分类2

```text
	score = int(input('分数: '))
	
	if score >= 60 and score < 70:
	    print('及格')
	elif 70 <= score < 80:
	    print('良')
	elif 80 <= score < 90:
	    print('好')
	elif score >= 90:
	    print('优秀')
	else:
	    print('你要努力了')
```



## 16-石头剪刀布

```text
	import random
	
	all_choices = ['石头', '剪刀', '布']
	computer = random.choice(all_choices)
	player = input('请出拳: ')
	
	# print('Your choice:', player, "Computer's choice:", computer)
	print("Your choice: %s, Computer's choice: %s" % (player, computer))
	if player == '石头':
	    if computer == '石头':
	        print('平局')
	    elif computer == '剪刀':
	        print('You WIN!!!')
	    else:
	        print('You LOSE!!!')
	elif player == '剪刀':
	    if computer == '石头':
	        print('You LOSE!!!')
	    elif computer == '剪刀':
	        print('平局')
	    else:
	        print('You WIN!!!')
	else:
	    if computer == '石头':
	        print('You WIN!!!')
	    elif computer == '剪刀':
	        print('You LOSE!!!')
	    else:
	        print('平局')
```



## 17-改进的石头剪刀布

```text
	import random
	
	all_choices = ['石头', '剪刀', '布']
	win_list = [['石头', '剪刀'], ['剪刀', '布'], ['布', '石头']]
	prompt = """(0) 石头
	(1) 剪刀
	(2) 布
	请选择(0/1/2): """
	computer = random.choice(all_choices)
	ind = int(input(prompt))
	player = all_choices[ind]
	
	print("Your choice: %s, Computer's choice: %s" % (player, computer))
	if player == computer:
	    print('\033[32;1m平局\033[0m')
	elif [player, computer] in win_list:
	    print('\033[31;1mYou WIN!!!\033[0m')
	else:
	    print('\033[31;1mYou LOSE!!!\033[0m')
```



## 18-猜数，直到猜对

```text
	import random
	
	num = random.randint(1, 10)
	running = True
	
	while running:
	    answer = int(input('guess the number: '))
	    if answer > num:
	        print('猜大了')
	    elif answer < num:
	        print('猜小了')
	    else:
	        print('猜对了')
	        running = False
```



## 19-猜数，5次机会

```text
	import random
	
	num = random.randint(1, 10)
	counter = 0
	
	while counter < 5:
	    answer = int(input('guess the number: '))
	    if answer > num:
	        print('猜大了')
	    elif answer < num:
	        print('猜小了')
	    else:
	        print('猜对了')
	        break
	    counter += 1
	else:  # 循环被break就不执行了，没有被break才执行
	    print('the number is:', num)
```



## 20-while循环，累加至100

> 因为循环次数是已知的，实际使用时，建议用for循环

```text
	sum100 = 0
	counter = 1
	
	while counter < 101:
	    sum100 += counter
	    counter += 1
	
	print(sum100)
```



## 21-while-break

> break是结束循环，break之后、循环体内代码不再执行。

```text
	while True:
	    yn = input('Continue(y/n): ')
	    if yn in ['n', 'N']:
	        break
	    print('running...')
```



## 22-while-continue

> 计算100以内偶数之和。
> continue是跳过本次循环剩余部分，回到循环条件处。

```text
	sum100 = 0
	counter = 0
	
	while counter < 100:
	    counter += 1
	    # if counter % 2:
	    if counter % 2 == 1:
	        continue
	    sum100 += counter
	
	print(sum100)
```



## 23-for循环遍历数据对象

```text
	astr = 'hello'
	alist = [10, 20, 30]
	atuple = ('bob', 'tom', 'alice')
	adict = {'name': 'john', 'age': 23}
	
	for ch in astr:
	    print(ch)
	
	for i in alist:
	    print(i)
	
	for name in atuple:
	    print(name)
	
	for key in adict:
	    print('%s: %s' % (key, adict[key]))
```



## 24-range用法及数字累加

```text
	# range(10)  # [0, 1, 2, 3, 4, 5, 6, 7, 8, 9]
	# >>> list(range(10))
	# range(6, 11)  # [6, 7, 8, 9, 10]
	# range(1, 10, 2)  # [1, 3, 5, 7, 9]
	# range(10, 0, -1)  # [10, 9, 8, 7, 6, 5, 4, 3, 2, 1]
	sum100 = 0
	
	for i in range(1, 101):
	    sum100 += i
	
	print(sum100)
```



## 25-列表实现斐波那契数列

> 列表中先给定两个数字，后面的数字总是前两个数字之和。

```text
	fib = [0, 1]
	
	for i in range(8):
	    fib.append(fib[-1] + fib[-2])
	
	print(fib)
```



## 26-九九乘法表

```text
	for i in range(1, 10):
	    for j in range(1, i + 1):
	        print('%s*%s=%s' % (j, i, i * j), end=' ')
	    print()
	
	# i=1 ->j: [1]
	# i=2 ->j: [1,2]
	# i=3 ->j: [1,2,3]
	＃由用户指定相乘到多少
	n = int(input('number: '))
	
	for i in range(1, n + 1):
	    for j in range(1, i + 1):
	        print('%s*%s=%s' % (j, i, i * j), end=' ')
	    print()
```



## 27-逐步实现列表解析

```text
	# 10+5的结果放到列表中
	[10 + 5]
	# 10+5这个表达式计算10次
	[10 + 5 for i in range(10)]
	# 10+i的i来自于循环
	[10 + i for i in range(10)]
	[10 + i for i in range(1, 11)]
	# 通过if过滤，满足if条件的才参与10+i的运算
	[10 + i for i in range(1, 11) if i % 2 == 1]
	[10 + i for i in range(1, 11) if i % 2]
	# 生成IP地址列表
	['192.168.1.%s' % i for i in range(1, 255)]
```



## 28-三局两胜的石头剪刀布

```text
	import random
	
	all_choices = ['石头', '剪刀', '布']
	win_list = [['石头', '剪刀'], ['剪刀', '布'], ['布', '石头']]
	prompt = """(0) 石头
	(1) 剪刀
	(2) 布
	请选择(0/1/2): """
	cwin = 0
	pwin = 0
	
	while cwin < 2 and pwin < 2:
	    computer = random.choice(all_choices)
	    ind = int(input(prompt))
	    player = all_choices[ind]
	
	    print("Your choice: %s, Computer's choice: %s" % (player, computer))
	    if player == computer:
	        print('\033[32;1m平局\033[0m')
	    elif [player, computer] in win_list:
	        pwin += 1
	        print('\033[31;1mYou WIN!!!\033[0m')
	    else:
	        cwin += 1
	        print('\033[31;1mYou LOSE!!!\033[0m')
```



## 29-文件对象基础操作

```text
	# 文件操作的三个步骤：打开、读写、关闭
	# cp /etc/passwd /tmp
	f = open('/tmp/passwd')  # 默认以r的方式打开纯文本文件
	data = f.read()  # read()把所有内容读取出来
	print(data)
	data = f.read()  # 随着读写的进行，文件指针向后移动。
	# 因为第一个f.read()已经把文件指针移动到结尾了，所以再读就没有数据了
	# 所以data是空字符串
	f.close()
	
	f = open('/tmp/passwd')
	data = f.read(4)  # 读4字节
	f.readline()  # 读到换行符\n结束
	f.readlines()  # 把每一行数据读出来放到列表中
	f.close()
	
	################################
	f = open('/tmp/passwd')
	for line in f:
	    print(line, end='')
	f.close()
	
	##############################
	f = open('图片地址', 'rb')  # 打开非文本文件要加参数b
	f.read(4096)
	f.close()
	
	##################################
	f = open('/tmp/myfile', 'w')  # 'w'打开文件，如果文件不存在则创建
	f.write('hello world!\n')
	f.flush()  # 立即将缓存中的数据同步到磁盘
	f.writelines(['2nd line.\n', 'new line.\n'])
	f.close()  # 关闭文件的时候，数据保存到磁盘
	
	##############################
	with open('/tmp/passwd') as f:
	    print(f.readline())
	
	#########################
	f = open('/tmp/passwd')
	f.tell()  # 查看文件指针的位置
	f.readline()
	f.tell()
	f.seek(0, 0)  # 第一个数字是偏移量，第2位是数字是相对位置。
	              # 相对位置0表示开头，1表示当前，2表示结尾
	f.tell()
	f.close()
```



## 30-拷贝文件

> 拷贝文件就是以r的方式打开源文件，以w的方式打开目标文件，将源文件数据读出后，写到目标文件。
> 以下是【不推荐】的方式，但是可以工作：

```text
	f1 = open('/bin/ls', 'rb')
	f2 = open('/root/ls', 'wb')
	
	data = f1.read()
	f2.write(data)
	
	f1.close()
	f2.close()
```



## 31-拷贝文件

> 每次读取4K，读完为止：

```text
	src_fname = '/bin/ls'
	dst_fname = '/root/ls'
	
	src_fobj = open(src_fname, 'rb')
	dst_fobj = open(dst_fname, 'wb')
	
	while True:
	    data = src_fobj.read(4096)
	    if not data:
	        break
	    dst_fobj.write(data)
	
	src_fobj.close()
	dst_fobj.close()
```



## 32-位置参数

> 注意：位置参数中的数字是字符形式的

```text
	import sys
	
	print(sys.argv)  # sys.argv是sys模块里的argv列表
	
	# python3 position_args.py
	# python3 position_args.py 10
	# python3 position_args.py 10 bob
```



## 33-函数应用-斐波那契数列

```text
	def gen_fib(l):
	    fib = [0, 1]
	
	    for i in range(l - len(fib)):
	        fib.append(fib[-1] + fib[-2])
	
	    return fib  # 返回列表，不返回变量fib
	
	a = gen_fib(10)
	print(a)
	print('-' * 50)
	n = int(input("length: "))
	print(gen_fib(n))  # 不会把变量n传入，是把n代表的值赋值给形参
```



## 34-函数-拷贝文件

```text
	import sys
	
	def copy(src_fname, dst_fname):
	    src_fobj = open(src_fname, 'rb')
	    dst_fobj = open(dst_fname, 'wb')
	
	    while True:
	        data = src_fobj.read(4096)
	        if not data:
	            break
	        dst_fobj.write(data)
	
	    src_fobj.close()
	    dst_fobj.close()
	
	copy(sys.argv[1], sys.argv[2])
	# 执行方式
	# cp_func.py /etc/hosts /tmp/zhuji.txt
```



## 35-函数-九九乘法表

```text
	def mtable(n):
	    for i in range(1, n + 1):
	        for j in range(1, i + 1):
	            print('%s*%s=%s' % (j, i, i * j), end=' ')
	        print()
	
	mtable(6)
	mtable(9)
```

## 36-模块基础

> 每一个以py作为扩展名的文件都是一个模块。

```text
star.py：


	hi = 'hello world!'
	
	def pstar(n=50):
	    print('*' * n)
	
	if __name__ == '__main__':
	    pstar()
	    pstar(30)
	在call_star.py中调用star模块：
	
	import star
	
	print(star.hi)
	star.pstar()
	star.pstar(30)
```



## 37-生成密码/验证码

> 此文件名为：[randpass.py](https://link.zhihu.com/?target=http%3A//randpass.py)
> 思路：
> 1、设置一个用于随机取出字符的基础字符串，本例使用大小写字母加数字
> 2、循环n次，每次随机取出一个字符
> 3、将各个字符拼接起来，保存到变量result中

```text
	from random import choice
	import string
	
	all_chs = string.ascii_letters + string.digits  # 大小写字母加数字
	
	def gen_pass(n=8):
	    result = ''
	
	    for i in range(n):
	        ch = choice(all_chs)
	        result += ch
	
	    return result
	
	if __name__ == '__main__':
	    print(gen_pass())
	    print(gen_pass(4))
	    print(gen_pass(10))
```



## 38-序列对象方法

```text
	from random import randint
	
	alist = list()  # []
	list('hello')  # ['h', 'e', 'l', 'l', 'o']
	list((10, 20, 30))  # [10, 20, 30]  元组转列表
	astr = str()  # ''
	str(10)  # '10'
	str(['h', 'e', 'l', 'l', 'o'])  # 将列表转成字符串
	atuple = tuple()  # ()
	tuple('hello')  # ('h', 'e', 'l', 'l', 'o')
	num_list = [randint(1, 100) for i in range(10)]
	max(num_list)
	min(num_list)
```



## 39-序列对象方法2

```text
	alist = [10, 'john']
	# list(enumerate(alist))  # [(0, 10), (1, 'john')]
	# a, b = 0, 10   # a->0  ->10
	
	for ind in range(len(alist)):
	    print('%s: %s' % (ind, alist[ind]))
	
	for item in enumerate(alist):
	    print('%s: %s' % (item[0], item[1]))
	
	for ind, val in enumerate(alist):
	    print('%s: %s' % (ind, val))
	
	atuple = (96, 97, 40, 75, 58, 34, 69, 29, 66, 90)
	sorted(atuple)
	sorted('hello')
	for i in reversed(atuple):
	    print(i, end=',')
```



## 40-字符串方法

```text
	py_str = 'hello world!'
	py_str.capitalize()
	py_str.title()
	py_str.center(50)
	py_str.center(50, '#')
	py_str.ljust(50, '*')
	py_str.rjust(50, '*')
	py_str.count('l')  # 统计l出现的次数
	py_str.count('lo')
	py_str.endswith('!')  # 以!结尾吗？
	py_str.endswith('d!')
	py_str.startswith('a')  # 以a开头吗？
	py_str.islower()  # 字母都是小写的？其他字符不考虑
	py_str.isupper()  # 字母都是大写的？其他字符不考虑
	'Hao123'.isdigit()  # 所有字符都是数字吗？
	'Hao123'.isalnum()  # 所有字符都是字母数字？
	'  hello\t    '.strip()  # 去除两端空白字符，常用
	'  hello\t    '.lstrip()
	'  hello\t    '.rstrip()
	'how are you?'.split()
	'hello.tar.gz'.split('.')
	'.'.join(['hello', 'tar', 'gz'])
	'-'.join(['hello', 'tar', 'gz'])
```

## 41-字符串格式化

```text
	"%s is %s years old" % ('bob', 23)  # 常用
	"%s is %d years old" % ('bob', 23)  # 常用
	"%s is %d years old" % ('bob', 23.5)  # %d是整数 常用
	"%s is %f years old" % ('bob', 23.5)
	"%s is %5.2f years old" % ('bob', 23.5)  # %5.2f是宽度为5，2位小数
	"97 is %c" % 97
	"11 is %#o" % 11  # %#o表示有前缀的8进制
	"11 is %#x" % 11
	"%10s%5s" % ('name', 'age')  # %10s表示总宽度为10，右对齐, 常用
	"%10s%5s" % ('bob', 25)
	"%10s%5s" % ('alice', 23)
	"%-10s%-5s" % ('name', 'age')  # %-10s表示左对齐, 常用
	"%-10s%-5s" % ('bob', 25)
	"%10d" % 123
	"%010d" % 123
	
	"{} is {} years old".format('bob', 25)
	"{1} is {0} years old".format(25, 'bob')
	"{:<10}{:<8}".format('name', 'age')
```



## 42-shutil模块常用方法

```text
	import shutil
	
	with open('/etc/passwd', 'rb') as sfobj:
	    with open('/tmp/mima.txt', 'wb') as dfobj:
	        shutil.copyfileobj(sfobj, dfobj) # 拷贝文件对象
	
	shutil.copyfile('/etc/passwd', '/tmp/mima2.txt')
	shutil.copy('/etc/shadow', '/tmp/')  # cp /etc/shadow /tmp/
	shutil.copy2('/etc/shadow', '/tmp/')  # cp -p /etc/shadow /tmp/
	shutil.move('/tmp/mima.txt', '/var/tmp/')  # mv /tmp/mima.txt /var/tmp/
	shutil.copytree('/etc/security', '/tmp/anquan') # cp -r /etc/security /tmp/anquan
	shutil.rmtree('/tmp/anquan')  # rm -rf /tmp/anquan
	# 将mima2.txt的权限设置成与/etc/shadow一样
	shutil.copymode('/etc/shadow', '/tmp/mima2.txt')
	# 将mima2.txt的元数据设置成与/etc/shadow一样
	# 元数据使用stat /etc/shadow查看
	shutil.copystat('/etc/shadow', '/tmp/mima2.txt')
	shutil.chown('/tmp/mima2.txt', user='zhangsan', group='zhangsan')
```



## 43-练习：生成文本文件

```text
	import os
	
	def get_fname():
	    while True:
	        fname = input('filename: ')
	        if not os.path.exists(fname):
	            break
	        print('%s already exists. Try again' % fname)
	
	    return fname
	
	def get_content():
	    content = []
	    print('输入数据，输入end结束')
	    while True:
	        line = input('> ')
	        if line == 'end':
	            break
	        content.append(line)
	
	    return content
	
	def wfile(fname, content):
	    with open(fname, 'w') as fobj:
	        fobj.writelines(content)
	
	if __name__ == '__main__':
	    fname = get_fname()
	    content = get_content()
	    content = ['%s\n' % line for line in content]
	    wfile(fname, content)
```



## 44-列表方法

```text
	alist = [1, 2, 3, 'bob', 'alice']
	alist[0] = 10
	alist[1:3] = [20, 30]
	alist[2:2] = [22, 24, 26, 28]
	alist.append(100)
	alist.remove(24)  # 删除第一个24
	alist.index('bob')  # 返回下标
	blist = alist.copy()  # 相当于blist = alist[:]
	alist.insert(1, 15)  # 向下标为1的位置插入数字15
	alist.pop()  # 默认弹出最后一项
	alist.pop(2) # 弹出下标为2的项目
	alist.pop(alist.index('bob'))
	alist.sort()
	alist.reverse()
	alist.count(20)  # 统计20在列表中出现的次数
	alist.clear()  # 清空
	alist.append('new')
	alist.extend('new')
	alist.extend(['hello', 'world', 'hehe'])
```



## 45-检查合法标识符

```text
	import sys
	import keyword
	import string
	
	first_chs = string.ascii_letters + '_'
	all_chs = first_chs + string.digits
	
	def check_id(idt):
	    if keyword.iskeyword(idt):
	        return "%s is keyword" % idt
	
	    if idt[0] not in first_chs:
	        return "1st invalid"
	
	    for ind, ch in enumerate(idt[1:]):
	        if ch not in all_chs:
	            return "char in postion #%s invalid" % (ind + 2)
	
	    return "%s is valid" % idt
	
	
	if __name__ == '__main__':
	    print(check_id(sys.argv[1]))  # python3 checkid.py abc@123
```



## 46-创建用户，设置随机密码

> randpass模块参见《37-生成密码/验证码》

```text
	import subprocess
	import sys
	from randpass import gen_pass
	
	def adduser(username, password, fname):
	    data = """user information:
	%s: %s
	"""
	    subprocess.call('useradd %s' % username, shell=True)
	    subprocess.call(
	        'echo %s | passwd --stdin %s' % (password, username),
	        shell=True
	    )
	    with open(fname, 'a') as fobj:
	        fobj.write(data % (username, password))
	
	if __name__ == '__main__':
	    username = sys.argv[1]
	    password = gen_pass()
	    adduser(username, password, '/tmp/user.txt')
	# python3 adduser.py john
```



## 47-列表练习：模拟栈操作

```text
	stack = []
	
	def push_it():
	    item = input('item to push: ')
	    stack.append(item)
	
	def pop_it():
	    if stack:
	        print("from stack popped %s" % stack.pop())
	
	def view_it():
	    print(stack)
	
	def show_menu():
	    cmds = {'0': push_it, '1': pop_it, '2': view_it}  # 将函数存入字典
	    prompt = """(0) push it
	(1) pop it
	(2) view it
	(3) exit
	Please input your choice(0/1/2/3): """
	
	    while True:
	        # input()得到字符串，用strip()去除两端空白，再取下标为0的字符
	        choice = input(prompt).strip()[0]
	        if choice not in '0123':
	            print('Invalid input. Try again.')
	            continue
	
	        if choice == '3':
	            break
	
	        cmds[choice]()
	
	
	if __name__ == '__main__':
	    show_menu()
```



## 48-实现Linux系统中unix2dos功能

```text
	import sys
	
	def unix2dos(fname):
	    dst_fname = fname + '.txt'
	
	    with open(fname) as src_fobj:
	        with open(dst_fname, 'w') as dst_fobj:
	            for line in src_fobj:
	                line = line.rstrip() + '\r\n'
	                dst_fobj.write(line)
	
	
	if __name__ == '__main__':
	    unix2dos(sys.argv[1])
```



## 49-动画程序：@从一行#中穿过

> \r是回车不换行

```text
	import time
	
	length = 19
	count = 0
	
	while True:
	    print('\r%s@%s' % ('#' * count, '#' * (length - count)), end='')
	    try:
	        time.sleep(0.3)
	    except KeyboardInterrupt:
	        print('\nBye-bye')
	        break
	    if count == length:
	        count = 0
	    count += 1
```





## 50-字典基础用法

```text
	adict = dict()  # {}
	dict(['ab', 'cd'])
	bdict = dict([('name', 'bob'),('age', 25)])
	{}.fromkeys(['zhangsan', 'lisi', 'wangwu'], 11)
	
	for key in bdict:
	    print('%s: %s' % (key, bdict[key]))
	
	print("%(name)s: %(age)s" % bdict)
	
	bdict['name'] = 'tom'
	bdict['email'] = 'tom@tedu.cn'
	
	del bdict['email']
	bdict.pop('age')
	bdict.clear()
```



## 51-字典常用方法

```text
	adict = dict([('name', 'bob'),('age', 25)])
	len(adict)
	hash(10)  # 判断给定的数据是不是不可变的，不可变数据才能作为key
	adict.keys()
	adict.values()
	adict.items()
	# get方法常用，重要
	adict.get('name')  # 取出字典中name对应的value，如果没有返回None
	print(adict.get('qq'))  # None
	print(adict.get('qq', 'not found'))  # 没有qq，返回指定内容
	print(adict.get('age', 'not found'))
	adict.update({'phone': '13455667788'})
```



## 52-集合常用方法

```text
# 集合相当于是无值的字典，所以也用{}表示
	myset = set('hello')
	len(myset)
	for ch in myset:
	    print(ch)
	
	aset = set('abc')
	bset = set('cde')
	aset & bset  # 交集
	aset.intersection(bset)  # 交集
	aset | bset  # 并集
	aset.union(bset)  # 并集
	aset - bset  # 差补
	aset.difference(bset)  # 差补
	aset.add('new')
	aset.update(['aaa', 'bbb'])
	aset.remove('bbb')
	cset = set('abcde')
	dset = set('bcd')
	cset.issuperset(dset)  # cset是dset的超集么？
	cset.issubset(dset)  # cset是dset的子集么？
```



## 53-集合实例：取出第二个文件有，第一个文件没有的行

```text
	# cp /etc/passwd .
	# cp /etc/passwd mima
	# vim mima  -> 修改，与passwd有些区别
	
	with open('passwd') as fobj:
	    aset = set(fobj)
	
	with open('mima') as fobj:
	    bset = set(fobj)
	
	with open('diff.txt', 'w') as fobj:
	    fobj.writelines(bset - aset)
```





## 54-字典练习：模拟注册/登陆

```text
	import getpass
	
	userdb = {}
	
	def register():
	    username = input('username: ')
	    if username in userdb:
	        print('%s already exists.' % username)
	    else:
	        password = input('password: ')
	        userdb[username] = password
	
	def login():
	    username = input('username: ')
	    password = getpass.getpass("password: ")
	    if userdb.get(username) != password:
	        print('login failed')
	    else:
	        print('login successful')
	
	
	def show_menu():
	    cmds = {'0': register, '1': login}
	    prompt = """(0) register
	(1) login
	(2) exit
	Please input your choice(0/1/2): """
	
	    while True:
	        choice = input(prompt).strip()[0]
	        if choice not in '012':
	            print('Invalid inupt. Try again.')
	            continue
	        if choice == '2':
	            break
	
	        cmds[choice]()
	
	if __name__ == '__main__':
	    show_menu()
```





## 55-计算千万次加法运算时间

```text
	import time
	
	result = 0
	start = time.time()  # 返回运算前时间戳
	for i in range(10000000):
	    result += i
	end = time.time()   # 返回运算后时间戳
	print(result)
	print(end - start)
```



## 56-时间相关模块常用方法

```text
	import time
	
	t = time.localtime()  # 返回当前时间的九元组
	time.gmtime()  # 返回格林威治0时区当前时间的九元组
	time.time()  # 常用，与1970-1-1 8:00之间的秒数，时间戳
	time.mktime(t)  # 把九元组时间转成时间戳
	time.sleep(1)
	time.asctime()  # 如果有参数，是九元组形式
	time.ctime()  # 返回当前时间，参数是时间戳，常用
	time.strftime("%Y-%m-%d") # 常用
	time.strptime('2018-07-20', "%Y-%m-%d")  # 返回九元组时间格式
	time.strftime('%H:%M:%S')
	
	###########################################
	from datetime import datetime
	from datetime import timedelta
	datetime.today()  # 返回当前时间的datetime对象
	datetime.now()  # 同上，可以用时区作参数
	datetime.strptime('2018/06/30', '%Y/%m/%d')  # 返回datetime对象
	dt = datetime.today()
	datetime.ctime(dt)
	datetime.strftime(dt, "%Y%m%d")
	
	days = timedelta(days=90, hours=3)  # 常用
	dt2 = dt + days
	dt2.year
	dt2.month
	dt2.day
	dt2.hour
```

## 57-os模块常用方法

```text
	import os
	
	os.getcwd()  # 显示当前路径
	os.listdir()  # ls -a
	os.listdir('/tmp')  # ls -a /tmp
	os.mkdir('/tmp/mydemo')  # mkdir /tmp/mydemo
	os.chdir('/tmp/mydemo')  # cd /tmp/mydemo
	os.listdir()
	os.mknod('test.txt')  # touch test.txt
	os.symlink('/etc/hosts', 'zhuji')  # ln -s /etc/hosts zhuji
	os.path.isfile('test.txt')  # 判断test.txt是不是文件
	os.path.islink('zhuji')  # 判断zhuji是不是软链接
	os.path.isdir('/etc')
	os.path.exists('/tmp')  # 判断是否存在
	os.path.basename('/tmp/abc/aaa.txt')
	os.path.dirname('/tmp/abc/aaa.txt')
	os.path.split('/tmp/abc/aaa.txt')
	os.path.join('/home/tom', 'xyz.txt')
	os.path.abspath('test.txt')  # 返回当前目录test.txt的绝对路径
```



## 58-pickle存储器

```text
	import pickle
	"""以前的文件写入，只能写入字符串，如果希望把任意数据对象(数字、列表等)写入文件，
	取出来的时候数据类型不变，就用到pickle了
	"""
	
	# shop_list = ["eggs", "apple", "peach"]
	# with open('/tmp/shop.data', 'wb') as fobj:
	#     pickle.dump(shop_list, fobj)
	
	with open('/tmp/shop.data', 'rb') as fobj:
	    mylist = pickle.load(fobj)
	
	print(mylist[0], mylist[1], mylist[2])
```



## 59-异常处理基础

```text
	try:   # 把有可能发生异常的语句放到try里执行
	    n = int(input("number: "))
	    result = 100 / n
	    print(result)
	except ValueError:
	    print('invalid number')
	except ZeroDivisionError:
	    print('0 not allowed')
	except KeyboardInterrupt:
	    print('Bye-bye')
	except EOFError:
	    print('Bye-bye')
	
	print('Done')
```



## 60-异常处理完整语法

```text
	try:
	    n = int(input("number: "))
	    result = 100 / n
	except (ValueError, ZeroDivisionError):
	    print('invalid number')
	except (KeyboardInterrupt, EOFError):
	    print('\nBye-bye')
	else:
	    print(result)  # 异常不发生时才执行else子句
	finally:
	    print('Done')  # 不管异常是否发生都必须执行的语句
	
	# 常用形式有try-except和try-finally
```