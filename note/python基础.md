# pycharm快捷键

crtl+alt+s; 打开软件设置

crtl+d:复制当前行代码

crtl+alt+上下;将当前代码行上移或下移

crtl+shift+f10：运行当前代码文件

shift+f6:重命名文件

crtl+a:全选

crtl+c\v\x；复制粘贴剪切

crtl+f;搜索

```python
if __name__=='__main__': 
```

# python基础语法

### 等待用户输入

```python
#!/usr/bin/python3
 
input("\n\n按下 enter 键后退出。")
```

Python 可以在同一行中使用多条语句，语句之间使用分号 **;** 分割

### 多个变量赋值

```python
#Python允许你同时为多个变量赋值
a = b = c = 1
#为多个对象指定多个变量
a, b, c = 1, 2, "runoob"
```

## 字面量

### 数字(Number)

```markdown
整数int
浮点数gloat
复数complex
布尔bool；Flase(0)   True（1）
```

### 字符串（String)

### 列表(List)

### 元组（Tuple）

### 集合（Set）

### 字典（Dictionary）

```markdown
print(输出)
```

### 查看类型

 type() 函数可以用来查询变量所指的对象类型，还可以用 isinstance 来判断。

```python
type(A)
isinstance(a,int)
```

isinstance 和 type 的区别在于：

- type()不会认为子类是一种父类类型。
- isinstance()会认为子类是一种父类类型。

## 注释

单行

```python
#
```

多行

```python
"""


"""
```

## 变量

变量没有类型

```markdown
变量名=变量值
```

### 数据类型

```python
string
int
float
type(被查看类型的数据)#变量存储的数据类型
```

### 数据类型转换

任何类型都能转换字符串

```python
int(x) 将x转换为一个整数。
float(x) 将x转换到一个浮点数。
complex(x) 将x转换到一个复数，实数部分为 x，虚数部分为 0。
complex(x, y) 将 x 和 y 转换到一个复数，实数部分为 x，虚数部分为 y。x 和 y 是数字表达式。
```

## 标识符

### 内容限定

英文，中文（不推荐），数字（不可以用在开头)，下划线-

### 大小写敏感

### 不可使用关键字

## 运算符

### 赋值运算符

| 运算符 | 描述                                                         | 实例                                                         |
| :----- | :----------------------------------------------------------- | :----------------------------------------------------------- |
| =      | 简单的赋值运算符                                             | c = a + b 将 a + b 的运算结果赋值为 c                        |
| +=     | 加法赋值运算符                                               | c += a 等效于 c = c + a                                      |
| -=     | 减法赋值运算符                                               | c -= a 等效于 c = c - a                                      |
| *=     | 乘法赋值运算符                                               | c *= a 等效于 c = c * a                                      |
| /=     | 除法赋值运算符                                               | c /= a 等效于 c = c / a                                      |
| %=     | 取模赋值运算符                                               | c %= a 等效于 c = c % a                                      |
| **=    | 幂赋值运算符                                                 | c **= a 等效于 c = c ** a                                    |
| //=    | 取整除赋值运算符                                             | c //= a 等效于 c = c // a                                    |
| :=     | 海象运算符，这个运算符的主要目的是在表达式中同时进行赋值和返回赋值的值。**Python3.8 版本新增运算符**。 | 在这个示例中，赋值表达式可以避免调用 len() 两次:`if (n := len(a)) > 10:    print(f"List is too long ({n} elements, expected <= 10)")` |

### 位运算符

| 运算符 | 描述                                                         | 实例                                                         |
| :----- | :----------------------------------------------------------- | :----------------------------------------------------------- |
| &      | 按位与运算符：参与运算的两个值,如果两个相应位都为1,则该位的结果为1,否则为0 | (a & b) 输出结果 12 ，二进制解释： 0000 1100                 |
| \|     | 按位或运算符：只要对应的二个二进位有一个为1时，结果位就为1。 | (a \| b) 输出结果 61 ，二进制解释： 0011 1101                |
| ^      | 按位异或运算符：当两对应的二进位相异时，结果为1              | (a ^ b) 输出结果 49 ，二进制解释： 0011 0001                 |
| ~      | 按位取反运算符：对数据的每个二进制位取反,即把1变为0,把0变为1。**~x** 类似于 **-x-1** | (~a ) 输出结果 -61 ，二进制解释： 1100 0011， 在一个有符号二进制数的补码形式。 |
| <<     | 左移动运算符：运算数的各二进位全部左移若干位，由"<<"右边的数指定移动的位数，高位丢弃，低位补0。 | a << 2 输出结果 240 ，二进制解释： 1111 0000                 |
| >>     | 右移动运算符：把">>"左边的运算数的各二进位全部右移若干位，">>"右边的数指定移动的位数 | a >> 2 输出结果 15 ，二进制解释： 0000 1111                  |

### 逻辑运算符

| 运算符 | 逻辑表达式 | 描述                                                         | 实例                    |
| :----- | :--------- | :----------------------------------------------------------- | :---------------------- |
| and    | x and y    | 布尔"与" - 如果 x 为 False，x and y 返回 x 的值，否则返回 y 的计算值。 | (a and b) 返回 20。     |
| or     | x or y     | 布尔"或" - 如果 x 是 True，它返回 x 的值，否则它返回 y 的计算值。 | (a or b) 返回 10。      |
| not    | not x      | 布尔"非" - 如果 x 为 True，返回 False 。如果 x 为 False，它返回 True。 | not(a and b) 返回 False |

### 成员运算符

| 运算符 | 描述                                                    | 实例                                              |
| :----- | :------------------------------------------------------ | :------------------------------------------------ |
| in     | 如果在指定的序列中找到值返回 True，否则返回 False。     | x 在 y 序列中 , 如果 x 在 y 序列中返回 True。     |
| not in | 如果在指定的序列中没有找到值返回 True，否则返回 False。 | x 不在 y 序列中 , 如果 x 不在 y 序列中返回 True。 |

### 身份运算符

| 运算符 | 描述                                        | 实例                                                         |
| :----- | :------------------------------------------ | :----------------------------------------------------------- |
| is     | is 是判断两个标识符是不是引用自一个对象     | **x is y**, 类似 **id(x) == id(y)** , 如果引用的是同一个对象则返回 True，否则返回 False |
| is not | is not 是判断两个标识符是不是引用自不同对象 | **x is not y** ， 类似 **id(x) != id(y)**。如果引用的不是同一个对象则返回结果 True，否则返回 False。 |

is 与 == 区别：

is 用于判断两个变量引用对象是否为同一个， == 用于判断引用变量的值是否相等。

### 运算符优先级

| 运算符                                                       | 描述                               |
| :----------------------------------------------------------- | :--------------------------------- |
| `(expressions...)`,`[expressions...]`, `{key: value...}`, `{expressions...}` | 圆括号的表达式                     |
| `x[index]`, `x[index:index]`, `x(arguments...)`, `x.attribute` | 读取，切片，调用，属性引用         |
| await x                                                      | await 表达式                       |
| `**`                                                         | 乘方(指数)                         |
| `+x`, `-x`, `~x`                                             | 正，负，按位非 NOT                 |
| `*`, `@`, `/`, `//`, `%`                                     | 乘，矩阵乘，除，整除，取余         |
| `+`, `-`                                                     | 加和减                             |
| `<<`, `>>`                                                   | 移位                               |
| `&`                                                          | 按位与 AND                         |
| `^`                                                          | 按位异或 XOR                       |
| `|`                                                          | 按位或 OR                          |
| `in,not in, is,is not, <, <=, >, >=, !=, ==`                 | 比较运算，包括成员检测和标识号检测 |
| `not x`                                                      | 逻辑非 NOT                         |
| `and`                                                        | 逻辑与 AND                         |
| `or`                                                         | 逻辑或 OR                          |
| `if -- else`                                                 | 条件表达式                         |
| `lambda`                                                     | lambda 表达式                      |
| `:=`                                                         | 赋值表达式                         |



## 字符串拓展

### 三种定义方式

```python
'  '单引号
"  "双引号
"""  “”“三引号，支持换行
转义字符\"或交替
```

### 拼接

```python
+   字符串拼接；变量（字符串）
```

### 字符串格式化

```python
%s
# %我要占位；s将变量变成字符串放入占位的地方
message = "大傻春%s,离谱%s" %（class,average）
#多个变量占位，要用括号括起来，并按照变量顺序填入
```

```python
%d  #整数
%f  #浮点数
```

#### 精度控制

```
m    宽度
.n   小数点精度(四舍五入)
```

| 符  号 | 描述                                 |
| :----- | :----------------------------------- |
| %c     | 格式化字符及其ASCII码                |
| %s     | 格式化字符串                         |
| %d     | 格式化整数                           |
| %u     | 格式化无符号整型                     |
| %o     | 格式化无符号八进制数                 |
| %x     | 格式化无符号十六进制数               |
| %X     | 格式化无符号十六进制数（大写）       |
| %f     | 格式化浮点数字，可指定小数点后的精度 |
| %e     | 用科学计数法格式化浮点数             |
| %E     | 作用同%e，用科学计数法格式化浮点数   |
| %g     | %f和%e的简写                         |
| %G     | %f 和 %E 的简写                      |
| %p     | 用十六进制数格式化变量的地址         |

格式化操作符辅助指令:

| 符号  | 功能                                                         |
| :---- | :----------------------------------------------------------- |
| *     | 定义宽度或者小数点精度                                       |
| -     | 用做左对齐                                                   |
| +     | 在正数前面显示加号( + )                                      |
| <sp>  | 在正数前面显示空格                                           |
| #     | 在八进制数前面显示零('0')，在十六进制前面显示'0x'或者'0X'(取决于用的是'x'还是'X') |
| 0     | 显示的数字前面填充'0'而不是默认的空格                        |
| %     | '%%'输出一个单一的'%'                                        |
| (var) | 映射变量(字典参数)                                           |
| m.n.  | m 是显示的最小总宽度,n 是小数点后的位数(如果可用的话)        |

### 字符串格式化f-string

```python
f"内容{变量}"
#不理会类型；不做精度控制
```

### 对表达式进行格式化

表达式：一条具有明确结果的代码语句

```python
message = "大傻春%s" %（1*1）
f"{表达式}
"%s/%d/%f" % (表达式、表达式、表达式)
```

```python
print(f"我是{aaa}")
print("结果是 %s" % (2*3))
```

## 数据输入

```python
input("提示信息")  #获取的永远是字符串
```

## Python三引号

python三引号允许一个字符串跨多行，字符串中可以包含换行符、制表符以及其他特殊字符

# python判断语句

## 布尔类型和比较运算符

比较运算得到布尔结果

```python
True  1 
False  0
```

```python
> < == >= <= !=
```

##   if语句的基本格式

```python
if age >= 18:
    print("我已经老了")
#归属于if的代码，填充四个空格缩进
```

## if else语句

```python
if age >= 18:
    print("我已经老了")
else:
    print("我没有")
#归属于else的代码，填充四个空格缩进
```

## if elif else语句

```python
if age >= 18:
    print("我已经老了")
elif age >=17:
    print("我还年轻")
elif age >= 16:
    print("我还小")
elsew
    print("我没有")
```

## 判断语句的嵌套

1.嵌套判断语句可以用于多条件、多层次的逻辑判断

2.嵌套判断语句可以根据需求，自由组合if elif else来构建多层次判断

3.嵌套判断语句，一定要注意空格缩进，Python通过空格缩进来决定层次关系 

# python循环语句

## while循环的基础语法

```python
i = 0
while i < 100:
    print("小美，我喜欢你")
	i += 1

```

注意事项
$$
条件需提供布尔类型结果，True继续，False停止
\\
空格缩进不能忘
\\
请规划好循环终止条件，否则将无限循环
$$

## while循环的嵌套

![image-20231215220415011](C:\Users\Lenovo\AppData\Roaming\Typora\typora-user-images\image-20231215220415011.png)

•基于空格缩进来决定层次关系

```python
print("hello",end='')
print("world",end='')
#输出不换行
```



\t 相当于tab键

## for循环的基础语法

•while循环的循环条件是自定义的，自行控制循环条件

•for循环是一种”轮询”机制，是对一批内容进行”逐个处理”

```python
# 定义字符串name
name = ”itheima”
# for循环处理字符串
for x in name: 
       print(x)
#for临时变量in待处理数据集：
	#循环满足条件是执行的代码

```

无法定义循环条件，只能被动取出数据处理

要注意，循环内的语句，需要有空格缩进

## range语句

```python
range(num)
```

获取一个从0开始，到num结束的数字序列（不含num本身）

如range(5)取得的数据是：[0, 1, 2, 3, 4]

```python
range(num1,num2)
```

获得一个从num1开始，到num2结束的数字序列（不含num2本身）

如，range(5, 10)取得的数据是：[5, 6, 7, 8, 9]

```python
range(num1,num2,step)
```

获得一个从num1开始，到num2结束的数字序列（不含num2本身）

数字之间的步长，以step为准（step默认为1）

如，range(5, 10, 2)取得的数据是：[5, 7, 9]

### for循环遍历range序列

```python
for i in range(5): 
       print(i)
```

range语句的功能是：

获得一个数字序列（可迭代类型的一种）

```python
range(num)
range(num1,num2)
range(num1,num2,step)
```

range语句的注意事项：

•语法1从0开始，到num结束（不含num本身）

•语法2从num1开始，到num2结束（不含num2本身）

•语法3从num1开始，到num2结束（不含num2本身），步长以step值为准

### for循环的变量作用域

临时变量，在编程规范上，作用范围（作用域），只限定在for循环内部



如果在for循环外部访问临时变量：

•实际上是可以访问到的

•在编程规范上，是不允许、不建议这么做的

```python
i= 0
for i in range(5):
    print(i)
print(i)
```

如果实在需要在循环外访问循环内的临时变量，可以在循环外预先定义

如图，每一次循环的时候，都会将取出的值赋予i变量。

•由于i变量是在循环之前（外）定义的

•在循环外访问i变量是合理的、允许的

#### 小结

for循环中的临时变量，其作用域限定为：

循环内

这种限定：

•是编程规范的限定，而非强制限定

•不遵守也能正常运行，但是不建议这样做

•如需访问临时变量，可以预先在循环外定义它

### for循环的嵌套应用

### 循环中断 : break和continue

#### continue

continue关键字用于：中断本次循环，直接进入下一次循环

continue可以用于：  for循环和while循环，效果一致

#### break

break关键字用于：直接结束所在循环

break可以用于：  for循环和while循环，效果一致

# python函数

## 简介

1. 函数是：

组织好的、可重复使用的、用来实现特定功能的代码段

2. 使用函数的好处是：

•将功能封装在函数内，可供随时随地重复利用

•提高代码的复用性，减少重复代码，提高开发效率

## 定义

```python
def 函数名（传入参数）：
    函数体
    return 返回值
'''
① 参数如不需要，可以省略（后续章节讲解）
② 返回值如不需要，可以省略（后续章节讲解）
③ 函数必须先定义后使用
'''

```

## 函数的参数

### 例

```python
# 定义2数相加的函数，通过参数接收被计算的2个数字
def add(x, y, z):
    result = x + y + z
    print(f"{x} + {y} + {z}的计算结果是：{result}")

# 调用函数，传入被计算的2个数字
add(5, 6, 7)
```

### 注意事项

•函数定义中的参数，称之为形式参数

•函数调用中的参数，称之为实际参数

•函数的参数数量不限，使用逗号分隔开

•传入参数的时候，要和形式参数一一对应，逗号隔开

## 函数的返回值

### 定义

所谓“返回值”，就是程序中函数完成事情后，最后给调用者的结果

Python中有一个特殊的字面量：None，其类型是：<class 'NoneType'>

无返回值的函数，实际上就是返回了：None这个字面量

```python
# 无return语句的函数返回值
def say_hi():
    print("你好呀")

result = say_hi()
print(f"无返回值函数，返回的内容是：{result}")
print(f"无返回值函数，返回的内容类型是：{type(result)}")

# 主动返回None的函数
def say_hi2():
    print("你好呀")
    return None

result = say_hi2()
print(f"无返回值函数，返回的内容是：{result}")
print(f"无返回值函数，返回的内容类型是：{type(result)}")
# None用于if判断
def check_age(age):
    if age > 18:
        return "SUCCESS"
    else:
        return None

result = check_age(16)
if not result:
    # 进入if表示result是None值 也就是False
    print("未成年，不可以进入")


# None用于声明无初始内容的变量
name = None

```

### None类型的应用场景

•用在**函数无返回**值上

•用在**if判断**上,在if判断中，None等同于False,一般用于在函数中主动返回None，配合if判断做相关处理

•用于**声明无内容的变量上**,定义变量，但暂时不需要变量有具体值，可以用None来代替

## 函数的嵌套调用

## 函数的作用域

### 局部变量

所谓局部变量是定义在函数体内部的变量，即只在函数体内部生效

局部变量的作用：在函数体内部，临时保存数据，即当函数调用完成后，则销毁局部变量

### 全局变量

所谓全局变量，指的是在函数体内、外都能生效的变量

### **global**关键字

使用 global关键字 可以在函数内部声明变量为全局变量

## 函数拓展

### 函数多个返回值

1两个return

只执行了第一个return，原因是因为return可以退出当前函数，

导致return下方的代码不执行

```python
def test_return():
    return 1, "hello", True

x, y, z = test_return()
print(x)
print(y)
print(z)
```

### 函数多种传参方式

**位置参数：**调用函数时根据函数定义的参数位置来传递参数

作用:可以让函数更加清晰、容易使用，同时也清除了参数的顺序需求.

传递的参数和定义的参数的顺序及个数必须一致

```python
def user_info(name, age, gender):
    print(f"姓名是:{name}, 年龄是:{age}, 性别是:{gender}")
# 位置参数 - 默认使用形式
user_info('小明', 20, '男')
```

**关键字参数：**函数调用时通过“键=值”形式传递参数.

作用：当调用函数时没有传递参数, 就会使用默认是用缺省参数对应的值.

​    函数调用时，如果有位置参数时，位置参数必须在关键字参数的前面，但关键字参数之间不存在先后顺序

```python
# 关键字参数
user_info(name='小王', age=11, gender='女')
user_info(age=10, gender='女', name='潇潇')    # 可以不按照参数的定义顺序传参
user_info('甜甜', gender='女', age=9)

```

**缺省参数：**缺省参数也叫默认参数，用于定义函数，为参数提供默认值，调用函数时可不传该默认参数的值（注意：所有位置参数必须出现在默认参数前，包括函数定义和调用）.

作用：当调用函数时没有传递参数, 就会使用默认是用缺省参数对应的值.

函数调用时，如果为缺省参数传值则修改默认参数值, 否则使用这个默认值

```python
def user_info(name, age, gender="女"):
    print(f"姓名是:{name}, 年龄是:{age}, 性别是:{gender}")

user_info('小天', 13, '男')
```

**不定长参数：**不定长参数也叫可变参数. 用于不确定调用的时候会传递多少个参数(不传参也可以)的场景.

作用： 当调用函数时不确定参数个数时, 可以使用不定长参数

类型：     ①位置传递

 传进的所有参数都会被args变量收集，它会根据传进参数的位置合并为一个元组(tuple)，args是元组类型，这就是位置传递

```python
# 不定长 - 位置不定长, *号
# 不定长定义的形式参数会作为元组存在，接收不定长数量的参数传入
def user_info(*args):
    print(f"args参数的类型是：{type(args)}，内容是:{args}")

user_info(1, 2, 3, '小明', '男孩')
```

  	     	 ②关键字传递

参数是“键=值”形式的形式的情况下, 所有的“键=值”都会被kwargs接受, 同时会根据“键=值”组成字典.

```python
# 不定长 - 关键字不定长, **号
def user_info(**kwargs):
    print(f"args参数的类型是：{type(kwargs)}，内容是:{kwargs}")
user_info(name='小王', age=11, gender='男孩')
```

### 匿名函数

#### 函数作为参数传递

1. 函数本身是可以作为参数，传入另一个函数中进行使用的。

2. 将函数传入的作用在于：传入计算逻辑，而非传入数据。

   ```python
   # 定义一个函数，接收另一个函数作为传入参数
   def test_func(compute):
       result = compute(1, 2)  # 确定compute是函数
       print(f"compute参数的类型是:{type(compute)}")
       print(f"计算结果：{result}")
   
   # 定义一个函数，准备作为参数传入另一个函数
   def compute(x, y):
       return x + y
   # 调用，并传入函数
   test_func(compute)
   ```

   ### lambda匿名函数的语法

   函数的定义中

   •def关键字，可以定义带有名称的函数

   •lambda关键字，可以定义匿名函数（无名称）

   有名称的函数，可以基于名称重复使用。

   无名称的匿名函数，只可临时使用一次

   #### 定义

   ```python
   lambda 传入参数：函数体（一行代码）
   ```

   •lambda 是关键字，表示定义匿名函数

   •传入参数表示匿名函数的形式参数，如：x, y 表示接收2个形式参数

   •函数体，就是函数的执行逻辑，要注意：只能写一行，无法写多行代码

   使用def和使用lambda，定义的函数功能完全一致，只是lambda关键字定义的函数是匿名的，无法二次使用

   ```python
   def test_func(compute):
       result = compute(1, 2)
       print(f"结果是:{result}")
   # 通过lambda匿名函数的形式，将匿名函数作为参数传入
   def add(x, y):
       return x + y
   test_func(add)
   test_func(lambda x, y: x + y)
   ```

   

# python数据容器

### 定义

一种可以存储多个元素的Python数据类型

### 分类

列表（list）、元组（tuple）、字符串（str）、集合（set）、字典（dict）

## 列表list

```python
my_list = ["itheima", "itcast", "python"]
```

```python
my_list = ["itheima", 666, True]
print(my_list)
print(type(my_list))
```

以 [] 作为标识

列表内每一个元素之间用, 逗号隔开

列表可以一次存储多个数据，且可以为不同的数据类型，支持嵌套

#### 列表的下表

```python
# 通过下标索引取出对应位置的数据
my_list = ["Tom", "Lily", "Rose"]
# 列表[下标索引], 从前向后从0开始，每次+1，  从后向前从-1开始，每次-1
print(my_list[0])
print(my_list[1])
print(my_list[2])
# 错误示范；通过下标索引取数据，一定不要超出范围
# print(my_list[3])

# 通过下标索引取出数据（倒序取出）
print(my_list[-1])
print(my_list[-2])
print(my_list[-3])
```

列表的每一个元素，都有编号称之为下标索引

从前向后的方向，编号从0开始递增

从后向前的方向，编号从-1开始递减

### 列表的嵌套

```python
# 取出嵌套列表的元素
my_list = [ [1, 2, 3], [4, 5, 6]]
print(my_list[1][1])
```

#### 列表操作

#### 查询下标

功能：查找指定元素在列表的下标，如果找不到，报错ValueError

   语法：列表.index(元素)

```python
mylist = ["itcast", "itheima", "python"]
# 1.1 查找某元素在列表内的下标索引
index = mylist.index("itheima")
print(f"itheima在列表中的下标索引值是：{index}")
# 1.2如果被查找的元素不存在，会报错
# index = mylist.index("hello")
# print(f"hello在列表中的下标索引值是：{index}")
```

#### 查询个数

•统计列表内，有多少元素

   语法：len(列表)

```python
# 10. 统计列表中全部的元素数量
mylist = ["itcast", "itheima", "itcast", "itheima", "python"]
count = len(mylist)
```



##### 修改

•修改特定位置（索引）的元素值：

   语法：列表[下标] = 值

```python
# 2. 修改特定下标索引的值
mylist[0] = "传智教育"
print(f"列表被修改元素值后，结果是：{mylist}")
```

##### 插入

•插入元素：

   语法：列表.insert(下标, 元素)，在指定的下标位置，插入指定的元素

```python
# 3. 在指定下标位置插入新元素
mylist.insert(1, "best")
print(f"列表插入元素后，结果是：{mylist}")
```

##### 追加

###### 单个

•追加元素：

   语法：列表.append(元素)，将指定元素，追加到列表的尾部

```python
# 4. 在列表的尾部追加```单个```新元素
mylist.append("黑马程序员")
print(f"列表在追加了元素后，结果是：{mylist}")
```

###### 一堆

   语法：列表.extend(其它数据容器)，将其它数据容器的内容取出，依次追加到列表尾部

```python
# 5. 在列表的尾部追加```一批```新元素
mylist2 = [1, 2, 3]
mylist.extend(mylist2)
print(f"列表在追加了一个新的列表后，结果是：{mylist}")
```

##### 修改

删除某元素在列表中的第一个匹配项

   语法：列表.remove(元素)

```python
# 7. 删除某元素在列表中的第一个匹配项
mylist = ["itcast", "itheima", "itcast", "itheima", "python"]
mylist.remove("itheima")
print(f"通过remove方法移除元素后，列表的结果是：{mylist}")
```

##### 清空列表内容

•语法：列表.clear()

```python
# 8. 清空列表
mylist.clear()
print(f"列表被清空了，结果是：{mylist}")
```

##### 统计某元素在列表内的数量

   语法：列表.count(元素)

```python
mylist = ["itcast", "itheima", "itcast", "itheima", "python"]
count = mylist.count("itheima")
print(f"列表中itheima的数量是：{count}")
```

##### 删除

方式1：del 列表[下标]

方式2：列表.pop(下标)

```python
# 6. 删除指定下标索引的元素（2种方式）
mylist = ["itcast", "itheima", "python"]

# 6.1 方式1：del 列表[下标]
del mylist[2]
print(f"列表删除元素后结果是：{mylist}")
# 6.2 方式2：列表.pop(下标)
mylist = ["itcast", "itheima", "python"]
element = mylist.pop(2)
print(f"通过pop方法取出元素后列表内容：{mylist}, 取出的元素是：{element}")
```

### Python列表函数&方法

Python包含以下函数:

| 序号 | 函数                                                         |
| :--- | :----------------------------------------------------------- |
| 1    | [len(list)](https://www.runoob.com/python3/python3-att-list-len.html) 列表元素个数 |
| 2    | [max(list)](https://www.runoob.com/python3/python3-att-list-max.html) 返回列表元素最大值 |
| 3    | [min(list)](https://www.runoob.com/python3/python3-att-list-min.html) 返回列表元素最小值 |
| 4    | [list(seq)](https://www.runoob.com/python3/python3-att-list-list.html) 将元组转换为列表 |

Python包含以下方法:

| 序号 | 方法                                                         |
| :--- | :----------------------------------------------------------- |
| 1    | [list.append(obj)](https://www.runoob.com/python3/python3-att-list-append.html) 在列表末尾添加新的对象 |
| 2    | [list.count(obj)](https://www.runoob.com/python3/python3-att-list-count.html) 统计某个元素在列表中出现的次数 |
| 3    | [list.extend(seq)](https://www.runoob.com/python3/python3-att-list-extend.html) 在列表末尾一次性追加另一个序列中的多个值（用新列表扩展原来的列表） |
| 4    | [list.index(obj)](https://www.runoob.com/python3/python3-att-list-index.html) 从列表中找出某个值第一个匹配项的索引位置 |
| 5    | [list.insert(index, obj)](https://www.runoob.com/python3/python3-att-list-insert.html) 将对象插入列表 |
| 6    | [list.pop([index=-1\])](https://www.runoob.com/python3/python3-att-list-pop.html) 移除列表中的一个元素（默认最后一个元素），并且返回该元素的值 |
| 7    | [list.remove(obj)](https://www.runoob.com/python3/python3-att-list-remove.html) 移除列表中某个值的第一个匹配项 |
| 8    | [list.reverse()](https://www.runoob.com/python3/python3-att-list-reverse.html) 反向列表中元素 |
| 9    | [list.sort( key=None, reverse=False)](https://www.runoob.com/python3/python3-att-list-sort.html) 对原列表进行排序 |
| 10   | [list.clear()](https://www.runoob.com/python3/python3-att-list-clear.html) 清空列表 |
| 11   | [list.copy()](https://www.runoob.com/python3/python3-att-list-copy.html) 复制列表 |

### 列表脚本操作符

| Python 表达式                         | 结果                         | 描述                 |
| :------------------------------------ | :--------------------------- | :------------------- |
| len([1, 2, 3])                        | 3                            | 长度                 |
| [1, 2, 3] + [4, 5, 6]                 | [1, 2, 3, 4, 5, 6]           | 组合                 |
| ['Hi!'] * 4                           | ['Hi!', 'Hi!', 'Hi!', 'Hi!'] | 重复                 |
| 3 in [1, 2, 3]                        | True                         | 元素是否存在于列表中 |
| for x in [1, 2, 3]: print(x, end=" ") | 1 2 3                        | 迭代                 |

##### 列表特点

•可以容纳多个元素（上限为2**63-1、9223372036854775807个）

•可以容纳不同类型的元素（混装）

•数据是有序存储的（有下标序号）

•允许重复数据存在

•可以修改（增加或删除元素等）

##### list（列表）的遍历

while

```python
index = 0
while index < len(列表):
	元素 = 列表[index]
    对元素进行处理
    index += 1
```

for

```python
for 临时变量 in 数据容器:
    对临时变量进行处理
```

while循环和for循环的对比

•在循环控制上：

•while循环可以自定循环条件，并自行控制

•for循环不可以自定循环条件，只可以一个个从容器内取出数据

•在无限循环上：

•while循环可以通过条件控制做到无限循环

•for循环理论上不可以，因为被遍历的容器容量不是无限的

•在使用场景上：

•while循环适用于任何想要循环的场景

•for循环适用于，遍历数据容器的场景或简单的固定次数循环场景

## 数据容器：tuple(元组)

元组一旦定义完成，就不可修改

##### 操作

| **编号** | **方法**  | **作用**                                           |
| -------- | --------- | -------------------------------------------------- |
| 1        | index()   | 查找某个数据，如果数据存在返回对应的下标，否则报错 |
| 2        | count()   | 统计某个数据在当前元组出现的次数                   |
| 3        | len(元组) | 统计元组内的元素个数                               |

```python
# 定义元组
t1 = (1, "Hello", True)
t2 = ()
t3 = tuple()
print(f"t1的类型是：{type(t1)}, 内容是：{t1}")
print(f"t2的类型是：{type(t2)}, 内容是：{t2}")
print(f"t3的类型是：{type(t3)}, 内容是：{t3}")

# 定义单个元素的元素
t4 = ("hello", )
print(f"t4的类型是：{type(t4)}, t4的内容是：{t4}")
# 元组的嵌套
t5 = ( (1, 2, 3), (4, 5, 6) )
print(f"t5的类型是：{type(t5)}, 内容是：{t5}")

# 下标索引去取出内容
num = t5[1][2]
print(f"从嵌套元组中取出的数据是：{num}")

# 元组的操作：index查找方法
t6 = ("传智教育", "黑马程序员", "Python")
index = t6.index("黑马程序员")
print(f"在元组t6中查找黑马程序员，的下标是：{index}")
# 元组的操作：count统计方法
t7 = ("传智教育", "黑马程序员", "黑马程序员", "黑马程序员", "Python")
num = t7.count("黑马程序员")
print(f"在元组t7中统计黑马程序员的数量有：{num}个")
# 元组的操作：len函数统计元组元素数量
t8 = ("传智教育", "黑马程序员", "黑马程序员", "黑马程序员", "Python")
num = len(t8)
print(f"t8元组中的元素有：{num}个")
# 元组的遍历：while
index = 0
while index < len(t8):
    print(f"元组的元素有：{t8[index]}")
    # 至关重要
    index += 1

# 元组的遍历：for
for element in t8:
    print(f"2元组的元素有：{element}")

# 修改元组内容
t8[0] = "itcast"
```

##### 例子

```python
# 定义一个元组
t9 = (1, 2, ["itheima", "itcast"])
print(f"t9的内容是：{t9}")
t9[2][0] = "黑马程序员"
t9[2][1] = "传智教育"
print(f"t9的内容是：{t9}")
```

### 元组内置函数

Python元组包含了以下内置函数

| 序号 | 方法及描述                               | 实例                                                         |
| :--- | :--------------------------------------- | :----------------------------------------------------------- |
| 1    | len(tuple) 计算元组元素个数。            | `>>> tuple1 = ('Google', 'Runoob', 'Taobao') >>> len(tuple1) 3 >>> ` |
| 2    | max(tuple) 返回元组中元素最大值。        | `>>> tuple2 = ('5', '4', '8') >>> max(tuple2) '8' >>> `      |
| 3    | min(tuple) 返回元组中元素最小值。        | `>>> tuple2 = ('5', '4', '8') >>> min(tuple2) '4' >>> `      |
| 4    | tuple(iterable) 将可迭代系列转换为元组。 | `>>> list1= ['Google', 'Taobao', 'Runoob', 'Baidu'] >>> tuple1=tuple(list1) >>> tuple1 ('Google', 'Taobao', 'Runoob', 'Baidu')` |

##### 元组特点

•可以容纳多个数据

•可以容纳不同类型的数据（混装）

•数据是有序存储的（下标索引）

•允许重复数据存在

•不可以修改（增加或删除元素等）

•支持for循环

## 数据容器：str(字符串)

**无法修改**

字符串用单引号 **'** 或双引号 **"** 括起来，同时使用反斜杠 **\** 转义特殊字符。

加号 **+** 是字符串的连接符， 星号 ***** 表示复制当前字符串，与之结合的数字为复制的次数

Python 使用反斜杠 转义特殊字符，如果你不想让反斜杠发生转义，可以在字符串前面添加一个 r

### 字符串运算符

| 操作符 | 描述                                                         | 实例                            |
| :----- | :----------------------------------------------------------- | :------------------------------ |
| +      | 字符串连接                                                   | a + b 输出结果： HelloPython    |
| *      | 重复输出字符串                                               | a*2 输出结果：HelloHello        |
| []     | 通过索引获取字符串中字符                                     | a[1] 输出结果 **e**             |
| [ : ]  | 截取字符串中的一部分，遵循**左闭右开**原则，str[0:2] 是不包含第 3 个字符的。 | a[1:4] 输出结果 **ell**         |
| in     | 成员运算符 - 如果字符串中包含给定的字符返回 True             | **'H' in a** 输出结果 True      |
| not in | 成员运算符 - 如果字符串中不包含给定的字符返回 True           | **'M' not in a** 输出结果 True  |
| r/R    | 原始字符串 - 原始字符串：所有的字符串都是直接按照字面的意思来使用，没有转义特殊或不能打印的字符。 原始字符串除在字符串的第一个引号前加上字母 **r**（可以大小写）以外，与普通字符串有着几乎完全相同的语法。 | `print( r'\n' ) print( R'\n' )` |
| %      | 格式字符串                                                   | 请看下一节内容。                |

无法修改

```python
my_str = "itheima and itcast"
# 通过下标索引取值
value = my_str[2]
value2 = my_str[-16]
print(f"从字符串{my_str}取下标为2的元素，。值是：{value},取下标为-16的元素。值是：{value2}")
#从前向后，下标从0开始从后向前，下标从-1开始
# my_str[2] = "H"

# index方法查找
value = my_str.index("and")
print(f"在字符串{my_str}中查找and，其起始下标是：{value}")

# replace方法替换
new_my_str = my_str.replace("it", "程序")
print(f"将字符串{my_str}，进行替换后得到：{new_my_str}")

# split方法分割
my_str = "hello python itheima itcast"
my_str_list = my_str.split(" ")
print(f"将字符串{my_str}进行split切分后得到：{my_str_list}, 类型是：{type(my_str_list)}")
#字符串按照给定的 <空格>进行了分割，变成多个子字符串，并存入一个列表对象中。

# strip方法(去前后空格)
my_str = "  itheima and itcast  "
new_my_str = my_str.strip() # 不传入参数，去除首尾空格
print(f"字符串{my_str}被strip后，结果：{new_my_str}")
#去前后字符串
my_str = "12itheima and itcast21"
new_my_str = my_str.strip("12")
print(f"字符串{my_str}被strip('12')后，结果：{new_my_str}")

# 统计字符串中某字符串的出现次数, count
my_str = "itheima and itcast"
count = my_str.count("it")
print(f"字符串{my_str}中it出现的次数是：{count}")
# 统计字符串的长度, len()
num = len(my_str)
print(f"字符串{my_str}的长度是：{num}")
```

| **编号** | **操作**                             | **说明**                                                     |
| -------- | ------------------------------------ | ------------------------------------------------------------ |
| 1        | 字符串[下标]                         | 根据下标索引取出特定位置字符                                 |
| 2        | 字符串.index(字符串）                | 查找给定字符的第一个匹配项的下标                             |
| 3        | 字符串.replace(字符串1, 字符串2)     | 将字符串内的全部字符串1，替换为字符串2  不会修改原字符串，而是得到一个新的 |
| 4        | 字符串.split(字符串)                 | 按照给定字符串，对字符串进行分隔  不会修改原字符串，而是得到一个新的列表 |
| 5        | 字符串.strip()  字符串.strip(字符串) | 移除首尾的空格和换行符或指定字符串                           |
| 6        | 字符串.count(字符串)                 | 统计字符串内某字符串的出现次数                               |
| 7        | len(字符串)                          | 统计字符串的字符个数                                         |

```python
# 字符串的遍历：while
my_str = "东北大学"
index = 0
while index < len(my_str):
    print(f"元组的元素有：{my_str[index]}")
    # 至关重要
    index += 1

# 字符串的遍历：for
for element in my_str:
    print(f"2元组的元素有：{element}")
```

##### 特点

•只可以存储字符串

•长度任意（取决于内存大小）

•支持下标索引

•允许重复字符串存在

•不可以修改（增加或删除元素等）

•支持for循环

### Python 转义字符

| 转义字符    | 描述                                                         | 实例                                                         |
| :---------- | :----------------------------------------------------------- | :----------------------------------------------------------- |
| \(在行尾时) | 续行符                                                       | `>>> print("line1 \ ... line2 \ ... line3") line1 line2 line3 >>> ` |
| \\          | 反斜杠符号                                                   | `>>> print("\\") \`                                          |
| \'          | 单引号                                                       | `>>> print('\'') '`                                          |
| \"          | 双引号                                                       | `>>> print("\"") "`                                          |
| \a          | 响铃                                                         | `>>> print("\a")`执行后电脑有响声。                          |
| \b          | 退格(Backspace)                                              | `>>> print("Hello \b World!") Hello World!`                  |
| \000        | 空                                                           | `>>> print("\000") >>> `                                     |
| \n          | 换行                                                         | `>>> print("\n")  >>>`                                       |
| \v          | 纵向制表符                                                   | `>>> print("Hello \v World!") Hello        World! >>>`       |
| \t          | 横向制表符                                                   | `>>> print("Hello \t World!") Hello    World! >>>`           |
| \r          | 回车，将 **\r** 后面的内容移到字符串开头，并逐一替换开头部分的字符，直至将 **\r** 后面的内容完全替换完成。 | `>>> print("Hello\rWorld!") World! >>> print('google runoob taobao\r123456') 123456 runoob taobao` |
| \f          | 换页                                                         | `>>> print("Hello \f World!") Hello        World! >>> `      |
| \yyy        | 八进制数，y 代表 0~7 的字符，例如：\012 代表换行。           | `>>> print("\110\145\154\154\157\40\127\157\162\154\144\41") Hello World!` |
| \xyy        | 十六进制数，以 \x 开头，y 代表的字符，例如：\x0a 代表换行    | `>>> print("\x48\x65\x6c\x6c\x6f\x20\x57\x6f\x72\x6c\x64\x21") Hello World!` |
| \other      | 其它的字符以普通格式输出                                     |                                                              |

使用 **\r** 实现百分比进度

## 序列

序列是指：内容连续、有序，可使用下标索引的一类数据容器；列表、元组、字符串，均可以可以视为序列。

序列支持切片，即：列表、元组、字符串，均支持进行切片操作

### 切片

切片：从一个序列中，取出一个子序列

语法：序列[起始下标:结束下标:步长]

```markdown
表示从序列中，从指定位置开始，依次取出元素，到指定位置结束，得到一个新序列：
起始下标表示从何处开始，可以留空，留空视作从头开始
结束下标（不含）表示何处结束，可以留空，留空视作截取到结尾
步长表示，依次取元素的间隔
步长1表示，一个个取元素
步长2表示，每次跳过1个元素取
步长N表示，每次跳过N-1个元素取
步长为负数表示，反向取（注意，起始下标和结束下标也要反向标记）

```

```python
# 对list进行切片，从1开始，4结束，步长1
my_list = [0, 1, 2, 3, 4, 5, 6]
result1 = my_list[1:4]      # 步长默认是1，所以可以省略不写
print(f"结果1：{result1}")

# 对tuple进行切片，从头开始，到最后结束，步长1
my_tuple = (0, 1, 2, 3, 4, 5, 6)
result2 = my_tuple[:]     # 起始和结束不写表示从头到尾，步长为1可以省略
print(f"结果2：{result2}")

# 对str进行切片，从头开始，到最后结束，步长2
my_str = "01234567"
result3 = my_str[::2]
print(f"结果3：{result3}")


# 对str进行切片，从头开始，到最后结束，步长-1
my_str = "01234567"
result4 = my_str[::-1]          # 等同于将序列反转了
print(f"结果4：{result4}")


# 对列表进行切片，从3开始，到1结束，步长-1
my_list = [0, 1, 2, 3, 4, 5, 6]
result5 = my_list[3:1:-1]
print(f"结果5：{result5}")


# 对元组进行切片，从头开始，到尾结束，步长-2
my_tuple = (0, 1, 2, 3, 4, 5, 6)
result6 = my_tuple[::-2]
print(f"结果6：{result6}")
```

```
结果1：[1, 2, 3]
结果2：(0, 1, 2, 3, 4, 5, 6)
结果3：0246
结果4：76543210
结果5：[3, 2]
结果6：(6, 4, 2, 0)
```



#### 拓展  字符串大小比较

1. 字符串如何比较

从头到尾，一位位进行比较，其中一位大，后面就无需比较了。

2. 单个字符之间如何确定大小？

通过ASCII码表，确定字符对应的码值数字来确定大小

## 数据容器：set(集合)

不支持元素的重复（自带去重功能）、并且内容无序

创建一个空集合必须用 **set()** 而不是 **{ }**，因为 **{ }** 是用来创建一个空字典。

```python
my_set = {"传智教育", "黑马程序员", "itheima", "传智教育", "黑马程序员", "itheima", "传智教育", "黑马程序员", "itheima"}
my_set_empty = set()        # 定义空集合
print(f"my_set的内容是：{my_set}, 类型是：{type(my_set)}")
print(f"my_set_empty的内容是：{my_set_empty}, 类型是：{type(my_set_empty)}")
```

##### 集合的常用操作

```python
# 添加新元素
my_set.add("Python")
my_set.add("传智教育")      #
print(f"my_set添加元素后结果是：{my_set}")
# 移除元素
my_set.remove("黑马程序员")
print(f"my_set移除黑马程序员后，结果是：{my_set}")
# 随机取出一个元素
my_set = {"传智教育", "黑马程序员", "itheima"}
element = my_set.pop()
print(f"集合被取出元素是：{element}, 取出元素后：{my_set}")

# 清空集合, clear
my_set.clear()
print(f"集合被清空啦，结果是：{my_set}")
```

##### 集合操作

```python
# 取2个集合的差集
set1 = {1, 2, 3}
set2 = {1, 5, 6}
set3 = set1.difference(set2)
print(f"取出差集后的结果是：{set3}")
print(f"取差集后，原有set1的内容：{set1}")
print(f"取差集后，原有set2的内容：{set2}")


# 消除2个集合的差集
set1 = {1, 2, 3}
set2 = {1, 5, 6}
set1.difference_update(set2)
print(f"消除差集后，集合1结果：{set1}")
print(f"消除差集后，集合2结果：{set2}")

# 2个集合合并为1个
set1 = {1, 2, 3}
set2 = {1, 5, 6}
set3 = set1.union(set2)
print(f"2集合合并结果：{set3}")
print(f"合并后集合1：{set1}")
print(f"合并后集合2：{set2}")

# 统计集合元素数量len()
set1 = {1, 2, 3, 4, 5, 1, 2, 3, 4, 5}
num = len(set1)
print(f"集合内的元素数量有：{num}个")
```

##### 集合的遍历

```python
# 集合不支持下标索引，不能用while循环
# 可以用for循环
set1 = {1, 2, 3, 4, 5}
for element in set1:
    print(f"集合的元素有：{element}")
```

### 集合内置方法完整列表

| 方法                                                         | 描述                                                         |
| :----------------------------------------------------------- | :----------------------------------------------------------- |
| [add()](https://www.runoob.com/python3/ref-set-add.html)     | 为集合添加元素                                               |
| [clear()](https://www.runoob.com/python3/ref-set-clear.html) | 移除集合中的所有元素                                         |
| [copy()](https://www.runoob.com/python3/ref-set-copy.html)   | 拷贝一个集合                                                 |
| [difference()](https://www.runoob.com/python3/ref-set-difference.html) | 返回多个集合的差集                                           |
| [difference_update()](https://www.runoob.com/python3/ref-set-difference_update.html) | 移除集合中的元素，该元素在指定的集合也存在。                 |
| [discard()](https://www.runoob.com/python3/ref-set-discard.html) | 删除集合中指定的元素                                         |
| [intersection()](https://www.runoob.com/python3/ref-set-intersection.html) | 返回集合的交集                                               |
| [intersection_update()](https://www.runoob.com/python3/ref-set-intersection_update.html) | 返回集合的交集。                                             |
| [isdisjoint()](https://www.runoob.com/python3/ref-set-isdisjoint.html) | 判断两个集合是否包含相同的元素，如果没有返回 True，否则返回 False。 |
| [issubset()](https://www.runoob.com/python3/ref-set-issubset.html) | 判断指定集合是否为该方法参数集合的子集。                     |
| [issuperset()](https://www.runoob.com/python3/ref-set-issuperset.html) | 判断该方法的参数集合是否为指定集合的子集                     |
| [pop()](https://www.runoob.com/python3/ref-set-pop.html)     | 随机移除元素                                                 |
| [remove()](https://www.runoob.com/python3/ref-set-remove.html) | 移除指定元素                                                 |
| [symmetric_difference()](https://www.runoob.com/python3/ref-set-symmetric_difference.html) | 返回两个集合中不重复的元素集合。                             |
| [symmetric_difference_update()](https://www.runoob.com/python3/ref-set-symmetric_difference_update.html) | 移除当前集合中在另外一个指定集合相同的元素，并将另外一个指定集合中不同的元素插入到当前集合中。 |
| [union()](https://www.runoob.com/python3/ref-set-union.html) | 返回两个集合的并集                                           |
| [update()](https://www.runoob.com/python3/ref-set-update.html) | 给集合添加元素                                               |
| [len()](https://www.runoob.com/python3/python3-string-len.html) | 计算集合元素个数                                             |

集合特点

•可以容纳多个数据

•可以容纳不同类型的数据（混装）

•数据是无序存储的（不支持下标索引）

•不允许重复数据存在

•可以修改（增加或删除元素等）

•支持for循环

## 数据容器：dict(字典、映射)

##### 定义

字典的定义，同样使用{}，不过存储的元素是一个个的：键值对，

•使用{}存储原始，每一个元素是一个键值对

•每一个键值对包含Key和Value（用冒号分隔）

•键值对之间使用逗号分隔

•Key和Value可以是任意类型的数据（key不可为字典）

•Key不可重复，重复会对原有数据覆盖

```python
# 定义字典
my_dict1 = {"王力鸿": 99, "周杰轮": 88, "林俊节": 77}
# 定义空字典
my_dict2 = {}
my_dict3 = dict()
print(f"字典1的内容是：{my_dict1}, 类型：{type(my_dict1)}")
print(f"字典2的内容是：{my_dict2}, 类型：{type(my_dict2)}")
print(f"字典3的内容是：{my_dict3}, 类型：{type(my_dict3)}")
# 定义重复Key的字典
my_dict1 = {"王力鸿": 99, "王力鸿": 88, "林俊节": 77}
print(f"重复key的字典的内容是：{my_dict1}")
```

##### 数据获取

```python
# 从字典中基于Key获取Value
my_dict1 = {"王力鸿": 99, "周杰轮": 88, "林俊节": 77}
score = my_dict1["王力鸿"]
print(f"王力鸿的考试分数是：{score}")
score = my_dict1["周杰轮"]
print(f"周杰轮的考试分数是：{score}")
```

字典的嵌套

```python
# 定义嵌套字典
stu_score_dict = {
    "王力鸿": {
        "语文": 77,
        "数学": 66,
        "英语": 33
    }, "周杰轮": {
        "语文": 88,
        "数学": 86,
        "英语": 55
    }, "林俊节": {
        "语文": 99,
        "数学": 96,
        "英语": 66
    }
}
print(f"学生的考试信息是：{stu_score_dict}")

# 从嵌套字典中获取数据
# 看一下周杰轮的语文信息
score = stu_score_dict["周杰轮"]["语文"]
print(f"周杰轮的语文分数是：{score}")
score = stu_score_dict["林俊节"]["英语"]
print(f"林俊节的英语分数是：{score}")
```

##### 注意事项

•键值对的Key和Value可以是任意类型（Key不可为字典）

•字典内Key不允许重复，重复添加等同于覆盖原有数据

•字典不可用下标索引，而是通过Key检索Value

##### 字典的操作

```python
my_dict = {"周杰轮": 99, "林俊节": 88, "张学油": 77}
# 新增元素
my_dict["张信哲"] = 66
print(f"字典经过新增元素后，结果：{my_dict}")
# 更新元素
my_dict["周杰轮"] = 33
print(f"字典经过更新后，结果：{my_dict}")
# 删除元素
score = my_dict.pop("周杰轮")
print(f"字典中被移除了一个元素，结果：{my_dict}, 周杰轮的考试分数是：{score}")

# 清空元素, clear
my_dict.clear()
print(f"字典被清空了，内容是：{my_dict}")

# 获取全部的key
my_dict = {"周杰轮": 99, "林俊节": 88, "张学油": 77}
keys = my_dict.keys()
print(f"字典的全部keys是：{keys}")
# 遍历字典
# 方式1：通过获取到全部的key来完成遍历
for key in keys:
    print(f"字典的key是:{key}")
    print(f"字典的value是：{my_dict[key]}")

# 方式2：直接对字典进行for循环，每一次循环都是直接得到key
for key in my_dict:
    print(f"2字典的key是:{key}")
    print(f"2字典的value是：{my_dict[key]}")

# 统计字典内的元素数量, len()函数
num = len(my_dict)
print(f"字典中的元素数量有：{num}个")
```

### 字典内置函数&方法

Python字典包含了以下内置函数：

| 序号 | 函数及描述                                                   | 实例                                                         |
| :--- | :----------------------------------------------------------- | :----------------------------------------------------------- |
| 1    | len(dict) 计算字典元素个数，即键的总数。                     | `>>> tinydict = {'Name': 'Runoob', 'Age': 7, 'Class': 'First'} >>> len(tinydict) 3` |
| 2    | str(dict) 输出字典，可以打印的字符串表示。                   | `>>> tinydict = {'Name': 'Runoob', 'Age': 7, 'Class': 'First'} >>> str(tinydict) "{'Name': 'Runoob', 'Class': 'First', 'Age': 7}"` |
| 3    | type(variable) 返回输入的变量类型，如果变量是字典就返回字典类型。 | `>>> tinydict = {'Name': 'Runoob', 'Age': 7, 'Class': 'First'} >>> type(tinydict) <class 'dict'>` |

Python字典包含了以下内置方法：

| 序号 | 函数及描述                                                   |
| :--- | :----------------------------------------------------------- |
| 1    | [dict.clear()](https://www.runoob.com/python3/python3-att-dictionary-clear.html) 删除字典内所有元素 |
| 2    | [dict.copy()](https://www.runoob.com/python3/python3-att-dictionary-copy.html) 返回一个字典的浅复制 |
| 3    | [dict.fromkeys()](https://www.runoob.com/python3/python3-att-dictionary-fromkeys.html) 创建一个新字典，以序列seq中元素做字典的键，val为字典所有键对应的初始值 |
| 4    | [dict.get(key, default=None)](https://www.runoob.com/python3/python3-att-dictionary-get.html) 返回指定键的值，如果键不在字典中返回 default 设置的默认值 |
| 5    | [key in dict](https://www.runoob.com/python3/python3-att-dictionary-in.html) 如果键在字典dict里返回true，否则返回false |
| 6    | [dict.items()](https://www.runoob.com/python3/python3-att-dictionary-items.html) 以列表返回一个视图对象 |
| 7    | [dict.keys()](https://www.runoob.com/python3/python3-att-dictionary-keys.html) 返回一个视图对象 |
| 8    | [dict.setdefault(key, default=None)](https://www.runoob.com/python3/python3-att-dictionary-setdefault.html) 和get()类似, 但如果键不存在于字典中，将会添加键并将值设为default |
| 9    | [dict.update(dict2)](https://www.runoob.com/python3/python3-att-dictionary-update.html) 把字典dict2的键/值对更新到dict里 |
| 10   | [dict.values()](https://www.runoob.com/python3/python3-att-dictionary-values.html) 返回一个视图对象 |
| 11   | [pop(key[,default\])](https://www.runoob.com/python3/python3-att-dictionary-pop.html) 删除字典 key（键）所对应的值，返回被删除的值。 |
| 12   | [popitem()](https://www.runoob.com/python3/python3-att-dictionary-popitem.html) 返回并删除字典中的最后一对键和值。 |

##### 特点

•可以容纳多个数据

•可以容纳不同类型的数据

•每一份数据是KeyValue键值对

•可以通过Key获取到Value，Key不可重复（重复会覆盖）

•不支持下标索引

•可以修改（增加或删除更新元素等）

•支持for循环，不支持while循环

## bytes 类型

在 Python3 中，bytes 类型表示的是不可变的二进制序列（byte sequence）。

与字符串类型不同的是，bytes 类型中的元素是整数值（0 到 255 之间的整数），而不是 Unicode 字符。

bytes 类型通常用于处理二进制数据，比如图像文件、音频文件、视频文件等等。在网络编程中，也经常使用 bytes 类型来传输二进制数据。

创建 bytes 对象的方式有多种，最常见的方式是使用 b 前缀：

此外，也可以使用 bytes() 函数将其他类型的对象转换为 bytes 类型。bytes() 函数的第一个参数是要转换的对象，第二个参数是编码方式，如果省略第二个参数，则默认使用 UTF-8 编码：

```
x = bytes("hello", encoding="utf-8")
```

与字符串类型类似，bytes 类型也支持许多操作和方法，如切片、拼接、查找、替换等等。同时，由于 bytes 类型是不可变的，因此在进行修改操作时需要创建一个新的 bytes 对象。

## 数据容器对比总结

```markdown
是否支持下标索引
支持：列表、元组、字符串 - 序列类型
不支持：集合、字典 - 非序列类型
是否支持重复元素：
支持：列表、元组、字符串 - 序列类型
不支持：集合、字典 - 非序列类型
是否可以修改
支持：列表、集合、字典
不支持：元组、字符串

```

|          | **列表**                         |     **字符串**     | **集合**               | **元组**                           | **字典**                                           |
| -------- | -------------------------------- | :----------------: | ---------------------- | ---------------------------------- | -------------------------------------------------- |
| 元素数量 | 支持多个                         |      支持多个      | 支持多个               | 支持多个                           | 支持多个                                           |
| 元素类型 | 任意                             |       仅字符       | 任意                   | 任意                               | Key：Value  Key：除字典外任意类型  Value：任意类型 |
| 下标索引 | 支持                             |        支持        | 不支持                 | 支持                               | 不支持                                             |
| 重复元素 | 支持                             |        支持        | 不支持                 | 支持                               | 不支持                                             |
| 可修改性 | 支持                             |       不支持       | 支持                   | 不支持                             | 支持                                               |
| 数据有序 | 是                               |         是         | 否                     | 是                                 | 否                                                 |
| 使用场景 | 可修改、可重复的一批数据记录场景 | 一串字符的记录场景 | 不可重复的数据记录场景 | 不可修改、可重复的一批数据记录场景 | 以Key检索Value的数据记录场景                       |

##### 应用场景

•列表：一批数据，可修改、可重复的存储场景

•元组：一批数据，不可修改、可重复的存储场景

•字符串：一串字符串的存储场景

•集合：一批数据，去重存储场景

•字典：一批数据，可用Key检索Value的存储场景

```python
my_list = [1, 2, 3, 4, 5]
my_tuple = (1, 2, 3, 4, 5)
my_str = "abcdefg"
my_set = {1, 2, 3, 4, 5}
my_dict = {"key1": 1, "key2": 2, "key3": 3, "key4": 4, "key5": 5}
```



#### **数据容器的通用操作** **-** **遍历**

•5类数据容器都支持for循环遍历

•列表、元组、字符串支持while循环，集合、字典不支持（无法下标索引）

#### **数据容器的通用统计功能**

len    max   min

#### **容器的通用转换功能**

list(容器)  将给定容器转换为列表

str(容器)   将给定容器转换为字符串

tuple(容器)   将给定容器转换为元组

set(容器)   将给定容器转换为集合

#### **容器**通用排序功能

sorted(容器, [reverse=True])   将给定容器进行排序

注意，排序后都会得到列表（list）对象

#### **容器通用功能总览**

| **功能**                     | **描述**                                         |
| ---------------------------- | ------------------------------------------------ |
| 通用for循环                  | 遍历容器（字典是遍历key）                        |
| max                          | 容器内最大元素                                   |
| min()                        | 容器内最小元素                                   |
| len()                        | 容器元素个数                                     |
| list()                       | 转换为列表                                       |
| tuple()                      | 转换为元组                                       |
| str()                        | 转换为字符串                                     |
| set()                        | 转换为集合                                       |
| sorted(序列, [reverse=True]) | 排序，reverse=True表示降序  得到一个排好序的列表 |

# python文件操作

## 文件的编码

1. 什么是编码？

编码就是一种规则集合，记录了内容和二进制间进行相互转换的逻辑。

编码有许多中，我们最常用的是UTF-8编码

2. 为什么需要使用编码？

计算机只认识0和1，所以需要将内容翻译成0和1才能保存在计算机中。

同时也需要编码， 将计算机保存的0和1，反向翻译回可以识别的内容

## 文件的读取

| 操作                                   | 功能                                              |
| -------------------------------------- | ------------------------------------------------- |
| 文件对象  = open(file, mode, encoding) | 打开文件获得文件对象                              |
| 文件对象.read(num)                     | 读取指定长度字节  不指定num读取文件全部           |
| 文件对象.readline()                    | 读取一行                                          |
| 文件对象.readlines()                   | 读取全部行，得到列表,其中每一行的数据为一个元素。 |
| for line in 文件对象                   | for循环文件行，一次循环得到一行数据               |
| 文件对象.close()                       | 关闭文件对象                                      |
| with open() as f                       | 通过with  open语法打开文件，可以自动关闭          |

```python
# 打开文件
import time

f = open("D:/测试.txt", "r", encoding="UTF-8")
print(type(f))
# 读取文件 - read()
# print(f"读取10个字节的结果：{f.read(10)}")
# print(f"read方法读取全部内容的结果是：{f.read()}")
print("-----------------------------------------------")
# 读取文件 - readLines()
# lines = f.readlines()   # 读取文件的全部行，封装到列表中
# print(f"lines对象的类型：{type(lines)}")
# print(f"lines对象的内容是：{lines}")

# 读取文件 - readline()
# line1 = f.readline()
# line2 = f.readline()
# line3 = f.readline()
# print(f"第一行数据是：{line1}")
# print(f"第二行数据是：{line2}")
# print(f"第三行数据是：{line3}")

# for循环读取文件行
# for line in f:
#     print(f"每一行数据是:{line}")
# # 文件的关闭
# f.close()
# time.sleep(500000)
# with open 语法操作文件
with open("D:/测试.txt", "r", encoding="UTF-8") as f:
    for line in f:
        print(f"每一行数据是：{line}")

time.sleep(500000)
```

name：是要打开的目标文件名的字符串(可以包含文件所在的具体路径)。

mode：设置打开文件的模式(访问模式)：只读、写入、追加等。

encoding:编码格式（推荐使用UTF-8）

| **模式** | **描述**                                                     |
| -------- | ------------------------------------------------------------ |
| r        | 以只读方式打开文件。文件的指针将会放在文件的开头。这是默认模式。 |
| w        | 打开一个文件只用于写入。如果该文件已存在则打开文件，并从开头开始编辑，原有内容会被删除。  如果该文件不存在，创建新文件。 |
| a        | 打开一个文件用于追加。如果该文件已存在，新的内容将会被写入到已有内容之后。  如果该文件不存在，创建新文件进行写入。 |

## 文件的写入

1. 打开文件

f = open('python.txt', 'w')

 2.文件写入

f.write('hello world')

3. 内容刷新

f.flush()

```python
# 打开文件，不存在的文件, r, w, a
import time

# f = open("D:/test.txt", "w", encoding="UTF-8")
# # write写入
# f.write("Hello World!!!")       # 内容写入到内存中
# # flush刷新
# # f.flush()                       # 将内存中积攒的内容，写入到硬盘的文件中
# # close关闭
# f.close()                       # close方法，内置了flush的功能的
# 打开一个存在的文件
f = open("D:/test.txt", "w", encoding="UTF-8")
# write写入、flush刷新
f.write("黑马程序员")
# close关闭
f.close()
```

•文件如果不存在，使用”w”模式，会创建新文件

•文件如果存在，使用”w”模式，会将原有内容清空

## 文件的追加

1. 打开文件，通过a模式打开即可

f = open('python.txt', 'a')

 2.文件写入

f.write('hello world')

3. 内容刷新

f.flush()

```python
# 打开文件，不存在的文件
# f = open("D:/test.txt", "a", encoding="UTF-8")
# # write写入
# f.write("黑马程序员")
# # flush刷新
# f.flush()
# # close关闭
# f.close()
# 打开一个存在的文件
f = open("D:/test.txt", "a", encoding="UTF-8")
# write写入、flush刷新
f.write("\n月薪过万")
# close关闭
f.close()
```

a模式，文件不存在会创建文件

a模式，文件存在会在最后，追加写入文件

# Python异常、模块与包

当检测到一个错误时，Python解释器就无法继续执行了，反而出现了一些错误的提示，这就是所谓的“异常”, 也就是我们常说的BUG

情况

​    ① 整个程序因为一个BUG停止运行

​    ② 对BUG进行提醒, 整个程序继续运行

```python
# 基本捕获语法
# try:
#     f = open("D:/abc.txt", "r", encoding="UTF-8")
# except:                                
#     print("出现异常了，因为文件不存在，我将open的模式，改为w模式去打开")
#     f = open("D:/abc.txt", "w", encoding="UTF-8")

# 捕获指定的异常
# try:
#     print(name)
#     # 1 / 0
# except NameError as e:
#     print("出现了变量未定义的异常")
#     print(e)
# 捕获多个异常
# try:
#     # 1 / 0
#     print(name)
# except (NameError, ZeroDivisionError) as e:
#     print("出现了变量未定义 或者 除以0的异常错误")
# 未正确设置捕获异常类型，将无法捕获异常

# 捕获所有异常
try:
    f = open("D:/123.txt", "r", encoding="UTF-8")
except Exception as e:
    print("出现异常了")
    f = open("D:/123.txt", "w", encoding="UTF-8")
else:
    print("好高兴，没有异常。")
finally:
    print("我是finally，有没有异常我都要执行")
    f.close()
```

## Python模块

![image-20240211165258873](C:\Users\Lenovo\AppData\Roaming\Typora\typora-user-images\image-20240211165258873.png)

**import**模块名

基本

import 模块名

import 模块名1，模块名2

模块名.功能名()

from 模块名 import 功能名

功能名()

from 模块名 import *

功能名()

**as**定义别名

\# 模块定义别名

import 模块名 as 别名

\# 功能定义别名

from 模块名 import 功能 as 别名

```
如果一个模块文件中有`__all__`变量，当使用`from xxx import *`导入时，只能导入这个列表中的元素

```

```python
# 创建一个包
# 导入自定义的包中的模块，并使用
# import my_package.my_module1
# import my_package.my_module2
#
# my_package.my_module1.info_print1()
# my_package.my_module2.info_print2()

# from my_package import my_module1
# from my_package import my_module2
# my_module1.info_print1()
# my_module2.info_print2()

# from my_package.my_module1 import info_print1
# from my_package.my_module2 import info_print2
# info_print1()
# info_print2()

# 通过__all__变量，控制import *
from my_package import *
my_module1.info_print1()
```

2. __init__.py文件的作用？

创建包会默认自动创建的文件，通过这个文件来表示一个文件夹是Python的包，而非普通的文件夹。

3. __all__变量的作用？

同模块中学习到的是一个作用，控制 import * 能够导入的内容

## **pip**的网络优化

pip install -i https://pypi.tuna.tsinghua.edu.cn/simple 

# 数据可视化

### json:

是一种轻量级的数据交互格式, 采用完全独立于编程语言的文本格式来存储和表示数据（就是字符串）

```python
# json数据的格式可以是： 
{"name":"admin","age":18} 

# 也可以是：  
[{"name":"admin","age":18},{"name":"root","age":16},{"name":"张三","age":20}] 

```

### **Python**数据和Json数据的相互转化

```python
# 导入json模块 
import json 

# 准备符合格式json格式要求的python数据 
data = [{"name": "老王", "age": 16}, {"name": "张三", "age": 20}]
 
# 通过 json.dumps(data) 方法把python数据转化为了json数据 
data = json.dumps(data) 

# 通过 json.loads(data) 方法把json数据转化为了python数据 
data = json.loads(data)

```

## pyecharts

全局配置选项

**全局配置选项**可以通过**set_global_opts**方法来进行配置, 相应的选项和选项的功能如下:

| **配置项**  | **作用**         | **代码实例**                                                |
| ----------- | ---------------- | ----------------------------------------------------------- |
| title_opts  | 设置图标题和位置 | title_opts=opts.TitleOpts(title="标题",  pos_left="center") |
| yaxis_opts  | y轴配置项        | yaxis_opts=opts.AxisOpts(name="累计确诊人数")               |
| xaxis_opts  | x轴配置项        | xaxis_opts=opts.AxisOpts(name="时间")                       |
| legend_opts | 图例配置项       | legend_opts=opts.LegendOpts(pos_left='70%')                 |

![image-20240308225400729](C:\Users\Lenovo\AppData\Roaming\Typora\typora-user-images\image-20240308225400729.png)

系列配置选项

https://gallery.pyecharts.org/#/README

### 基础折线图

![image-20240308225304367](C:\Users\Lenovo\AppData\Roaming\Typora\typora-user-images\image-20240308225304367.png)

| **配置项** | **作用**               | **代码实例**                                             |
| ---------- | ---------------------- | -------------------------------------------------------- |
| init_opts  | 对折线图初始化设置宽高 | init_opts=opts.InitOpts(width="1600px",  height="800px") |
| .add_xaxis | 添加x轴数据            | .add_xaxis(列表)                                         |
| .add_yaxis | 添加y轴数据            |                                                          |

#### 创建折线图

![image-20240308225510406](C:\Users\Lenovo\AppData\Roaming\Typora\typora-user-images\image-20240308225510406.png)

 **.add_yaxis**相关配置选项

| **配置项**     | **作用**               | **代码实例**                               |
| -------------- | ---------------------- | ------------------------------------------ |
| series_name    | 设置图例名称           | series_name="美国确诊人数"                 |
| y_axis         | 输入y轴数据            | y_axis=["列表"]                            |
| symbol_size    | 设置点的大小           | symbol_size=10                             |
| label_opts     | 标签设置项：不显示标签 | label_opts=opts.LabelOpts(is_show=False)   |
| linestyle_opts | 线条宽度和样式         | linestyle_opts=opts.LineStyleOpts(width=2) |

### 地图

break

### 柱状图

1. 通过Bar()构建一个柱状图对象

2. 和折线图一样，通过add_xaxis()和add_yaxis()添加x和y轴数据

3. 通过柱状图对象的：reversal_axis()，反转x和y轴

4. 通过label_opts=LabelOpts(position="right")设置数值标签在右侧显示

