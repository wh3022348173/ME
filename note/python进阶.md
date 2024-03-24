# 面向对象

#### 导入

设计表格，称之为：设计类（class）

打印表格，称之为：创建对象

填写表格，称之为：对象属性赋值

## 成员方法

•class是关键字，表示要定义类了

•类的属性，即定义在类中的变量（成员变量）

•类的行为，即定义在类中的函数（成员方法）

```python
# 定义一个带有成员方法的类
class Student:
    name = None     # 学生的姓名

    def say_hi(self):
        print(f"大家好呀，我是{self.name}，欢迎大家多多关照")


    def say_hi2(self, msg):
        print(f"大家好，我是：{self.name}，{msg}")
```

self关键字是成员方法定义的时候，必须填写的。

•它用来表示类对象自身的意思

•当我们使用类对象调用方法的是，self会自动被python传入

•在方法内部，想要访问类的成员变量，必须使用self

self关键字，尽管在参数列表中，但是传参的时候可以忽略它。

## 类与对象

1. 现实世界的事物由什么组成？

•属性

•行为

类也可以包含属性和行为，所以使用类描述现实世界事物是非常合适的

2. 类和对象的关系是什么？

类是程序中的“设计图纸”

对象是基于图纸生产的具体实体

3. 什么是面向对象编程？

面向对象编程就是，使用对象进行编程。

即，设计类，基于类创建对象，并使用对象来完成具体的工作

## 构造方法

Python类可以使用：__init__()方法，称之为构造方法。

可以实现：

•在创建类对象（构造类）的时候，会自动执行。

•在创建类对象（构造类）的时候，将传入参数自动传递给__init__方法使用。

```python
# 演示使用构造方法对成员变量进行赋值
# 构造方法的名称：__init__

class Student:

    def __init__(self, name, age ,tel):
        self.name = name
        self.age = age
        self.tel = tel
        print("Student类创建了一个类对象")

stu = Student("周杰轮", 31, "18500006666")
```

构造方法的作用：

•构建类对象的时候会自动运行

•构建类对象的传参会传递给构造方法，借此特性可以给成员变量赋值

注意事项：

•构造方法不要忘记self关键字

在方法内使用成员变量需要使用self

## 其他内置方法

| 方法     | 功能                                           |
| -------- | ---------------------------------------------- |
| __init__ | 构造方法，可用于创建类对象的时候设置初始化行为 |
| __str__  | 用于实现类对象转字符串的行为                   |
| __lt__   | 用于2个类对象进行小于或大于比较                |
| __le__   | 用于2个类对象进行小于等于或大于等于比较        |
| __eq__   | 用于2个类对象进行相等比较                      |

- **__init__ :** 构造函数，在生成对象时调用
- **__del__ :** 析构函数，释放对象时使用
- **__repr__ :** 打印，转换
- **__setitem__ :** 按照索引赋值
- **__getitem__:** 按照索引获取值
- **__len__:** 获得长度
- **__cmp__:** 比较运算
- **__call__:** 函数调用
- **__add__:** 加运算
- **__sub__:** 减运算
- **__mul__:** 乘运算
- **__truediv__:** 除运算
- **__mod__:** 求余运算
- **__pow__:** 乘方

```python
class Student:
    def __init__(self, name, age):
        self.name = name        # 学生姓名
        self.age = age          # 学生年龄

    # __str__魔术方法
    def __str__(self):
        return f"Student类对象，name:{self.name}, age:{self.age}"

    # __lt__魔术方法
    def __lt__(self, other):
        return self.age < other.age

    # __le__魔术方法
    def __le__(self, other):
        return self.age <= other.age

    # __eq__魔术方法
    def __eq__(self, other):
        return self.age == other.age


stu1 = Student("周杰轮", 31)
stu2 = Student("林俊节", 36)
print(stu1 == stu2)
```

## 封装

封装表示的是，将现实世界事物的：

•属性

•行为

封装到类中，描述为：

•成员变量

•成员方法

从而完成程序对现实世界事物的描述

### 私有成员

定义私有成员的方式非常简单，只需要：

•私有成员变量：变量名以__开头（2个下划线）

•私有成员方法：方法名以__开头（2个下划线）

私有方法无法直接被类对象使用                 

私有变量无法赋值，也无法获取值

私有成员无法被类对象使用，但是可以被其它的成员使用

## 继承

### 单继承和多继承

单继承：一个类继承另一个类

多继承：一个类继承多个类，按照顺序从左向右依次继承

多继承中，如果父类有同名方法或属性，先继承的优先级高于后继承

###  pass关键字的作用

pass是占位语句，用来保证函数（方法）或类定义的完整性，表示无内容，空的意思

```python
# 演示单继承
class Phone:
    IMEI = None     # 序列号
    producer = "ITCAST" # 厂商
    def call_by_4g(self):
        print("4g通话")

class Phone2022(Phone):
    face_id = "10001"       # 面部识别ID
    def call_by_5g(self):
        print("2022年新功能：5g通话")

phone = Phone2022()
print(phone.producer)
phone.call_by_4g()
phone.call_by_5g()
# 演示多继承
class NFCReader:
    nfc_type = "第五代"
    producer = "HM"
    def read_card(self):
        print("NFC读卡")
    def write_card(self):
        print("NFC写卡")

class RemoteControl:
    rc_type = "红外遥控"

    def control(self):
        print("红外遥控开启了")

class MyPhone(Phone, NFCReader, RemoteControl):
    pass

phone = MyPhone()
phone.call_by_4g()
phone.read_card()
phone.write_card()
phone.control()
print(phone.producer)
# 演示多继承下，父类成员名一致的场景

```

### 复写

子类继承父类的成员属性和成员方法后，如果对其“不满意”，那么可以进行复写。

即：在子类中重新定义同名的属性或方法即可。

方式1：

•调用父类成员

   使用成员变量：父类名.成员变量

   使用成员方法：父类名.成员方法(self)

方式2：

•使用super()调用父类成员

   使用成员变量：super().成员变量

   使用成员方法：super().成员方法()

```python
class Phone:
    IMEI = None             # 序列号
    producer = "ITCAST"     # 厂商

    def call_by_5g(self):
        print("使用5g网络进行通话")

# 定义子类，复写父类成员
class MyPhone(Phone):
    producer = "ITHEIMA"        # 复写父类的成员属性

    def call_by_5g(self):
        print("开启CPU单核模式，确保通话的时候省电")
        # 方式1
        # print(f"父类的厂商是：{Phone.producer}")
        # Phone.call_by_5g(self)
        # 方式2
        print(f"父类的厂商是：{super().producer}")
        super().call_by_5g()
        print("关闭CPU单核模式，确保性能")

phone = MyPhone()
phone.call_by_5g()
print(phone.producer)

# 在子类中，调用父类成员
```

## 类型注解

### 变量

1. 什么是类型注解，有什么作用？

在代码中涉及数据交互之时，对数据类型进行显式的说明，可以帮助：

•PyCharm 等开发工具对代码做类型推断协助做代码提示

•开发者自身做类型的备注

2. 类型注解支持：

•变量的类型注解

•函数（方法）的形参和返回值的类型注解

3. 变量的类型注解语法

•语法1： 变量: 类型

•语法2： 在注释中，# type: 类型

4. 注意事项

•类型注解只是提示性的，并非决定性的。数据类型和注解类型无法对应也不会导致错误

```python
# 基础数据类型注解
var_1: int = 10
var_2: str = "itheima"
var_3: bool = True
# 基础容器类型注解
 my_list: list = [1, 2, 3]
 my_tuple: tuple = (1, 2, 3)
 my_dict: dict = {"itheima": 666} 
# 容器类型详细注解
my_list: list[int] = [1, 2, 3]
my_tuple: tuple[int, str, bool] = (1, "itheima", True)
my_dict: dict[str, int] = {"itheima": 666}
# 在注释中进行类型注解
var_1 = random.randint(1, 10)   # type: int
var_2 = json.loads('{"name": "zhangsan"}')  # type: dict[str, str] 
```

### 函数

```python
# 对形参进行类型注解
def add(x: int, y: int):
    return x + y

# 对返回值进行类型注解
def func(data: list) -> list:
    return data

print(func(1))

```

### Union类型

```python
# 使用Union类型，必须先导包
from typing import Union

my_list: list[Union[int, str]] = [1, 2, "itheima", "itcast"]

def func(data: Union[int, str]) -> Union[int, str]:
    pass
```

## 多态

多种状态，即完成某个行为时，使用不同的对象会得到不同的状态。

多态常作用在继承关系上.

比如

•函数(方法)形参声明接收父类对象

•实际传入父类的子类对象进行工作

即:

•以父类做定义声明

•以子类做实际工作

•用以获得同一行为, 不同状态

```python
class Animal:
    def speak(self):
        pass
    
class Dog(Animal):
    def speak(self):
        print("汪汪汪")

class Cat(Animal):
    def speak(self):
        print("喵喵喵")

def make_noise(animal: Animal):
    """制造点噪音，需要传入Animal对象"""
    animal.speak()

# 演示多态，使用2个子类对象来调用函数
dog = Dog()
cat = Cat()

make_noise(dog)
make_noise(cat)
```

1. 什么是多态？

多态指的是，同一个行为，使用不同的对象获得不同的状态。

如，定义函数（方法），通过类型注解声明需要父类对象，实际传入子类对象进行工作，从而获得不同的工作状态

2. 什么是抽象类（接口）

包含抽象方法的类，称之为抽象类。抽象方法是指：没有具体实现的方法（pass）称之为抽象方法

3. 抽象类的作用

多用于做顶层设计（设计标准），以便子类做具体实现。

也是对子类的一种软性约束，要求子类必须复写（实现）父类的一些方法

并配合多态使用，获得不同的工作状态。

# 数据结构

## 列表

| 方法              | 描述                                                         |
| :---------------- | :----------------------------------------------------------- |
| list.append(x)    | 把一个元素添加到列表的结尾，相当于 a[len(a):] = [x]。        |
| list.extend(L)    | 通过添加指定列表的所有元素来扩充列表，相当于 a[len(a):] = L。 |
| list.insert(i, x) | 在指定位置插入一个元素。第一个参数是准备插入到其前面的那个元素的索引，例如 a.insert(0, x) 会插入到整个列表之前，而 a.insert(len(a), x) 相当于 a.append(x) 。 |
| list.remove(x)    | 删除列表中值为 x 的第一个元素。如果没有这样的元素，就会返回一个错误。 |
| list.pop([i])     | 从列表的指定位置移除元素，并将其返回。如果没有指定索引，a.pop()返回最后一个元素。元素随即从列表中被移除。（方法中 i 两边的方括号表示这个参数是可选的，而不是要求你输入一对方括号，你会经常在 Python 库参考手册中遇到这样的标记。） |
| list.clear()      | 移除列表中的所有项，等于del a[:]。                           |
| list.index(x)     | 返回列表中第一个值为 x 的元素的索引。如果没有匹配的元素就会返回一个错误。 |
| list.count(x)     | 返回 x 在列表中出现的次数。                                  |
| list.sort()       | 对列表中的元素进行排序。                                     |
| list.reverse()    | 倒排列表中的元素。                                           |
| list.copy()       | 返回列表的浅复制，等于a[:]。                                 |

## 将列表当做堆栈使用

也可以把列表当做队列用，只是在队列里第一加入的元素，第一个取出来；但是拿列表用作这样的目的效率不高。在列表的最后添加或者弹出元素速度快，然而在列表里插入或者从头部弹出速度却不快（因为所有其他的元素都得一个一个地移动）

## 列表推导式

列表推导式提供了从序列创建列表的简单途径。通常应用程序将一些操作应用于某个序列的每个元素，用其获得的结果作为生成新列表的元素，或者根据确定的判定条件创建子序列。

每个列表推导式都在 for 之后跟一个表达式，然后有零到多个 for 或 if 子句。返回结果是一个根据表达从其后的 for 和 if 上下文环境中生成出来的列表。如果希望表达式推导出一个元组，就必须使用括号。

这里我们将列表中每个数值乘三，获得一个新的列表：

>>> vec = [2, 4, 6]
>>> [3*x for x in vec]
>>> [6, 12, 18]

## del 语句

使用 del 语句可以从一个列表中根据索引来删除一个元素，而不是值来删除元素。这与使用 pop() 返回一个值不同。可以用 del 语句从列表中删除一个切割，或清空整个列表（我们以前介绍的方法是给该切割赋一个空列表）

# 高级

## 正则表达式

正则表达式是一个特殊的字符序列，它能帮助你方便的检查一个字符串是否与某种模式匹配。

在 Python 中，使用 **re** 模块来处理正则表达式。

re 模块提供了一组函数，允许你在字符串中进行模式匹配、搜索和替换操作。

**re** 模块使 Python 语言拥有完整的正则表达式功能。

### re.match函数

re.match 尝试从字符串的**起始位置**匹配一个模式，如果不是起始位置匹配成功的话，match() 就返回 None。

**函数语法**：

```
re.match(pattern, string, flags=0)
```

函数参数说明：

| 参数    | 描述                                                         |
| :------ | :----------------------------------------------------------- |
| pattern | 匹配的正则表达式                                             |
| string  | 要匹配的字符串。                                             |
| flags   | 标志位，用于控制正则表达式的匹配方式，如：是否区分大小写，多行匹配等等。参见：[正则表达式修饰符 - 可选标志](https://www.runoob.com/python3/python3-reg-expressions.html#flags) |

匹配成功 **re.match** 方法返回一个匹配的对象，否则返回 **None**。

我们可以使用 **group(num)** 或 **groups()** 匹配对象函数来获取匹配表达式。

| 匹配对象方法 | 描述                                                         |
| :----------- | :----------------------------------------------------------- |
| group(num=0) | 匹配的整个表达式的字符串，group() 可以一次输入多个组号，在这种情况下它将返回一个包含那些组所对应值的元组。 |
| groups()     | 返回一个包含所有小组字符串的元组，从 1 到 所含的小组号。     |

### re.search方法

re.search 扫描整个字符串并返回第一个成功的匹配。

函数语法：

```
re.search(pattern, string, flags=0)
```

函数参数说明：

| 参数    | 描述                                                         |
| :------ | :----------------------------------------------------------- |
| pattern | 匹配的正则表达式                                             |
| string  | 要匹配的字符串。                                             |
| flags   | 标志位，用于控制正则表达式的匹配方式，如：是否区分大小写，多行匹配等等。参见：[正则表达式修饰符 - 可选标志](https://www.runoob.com/python3/python3-reg-expressions.html#flags) |

匹配成功re.search方法返回一个匹配的对象，否则返回None。

我们可以使用group(num) 或 groups() 匹配对象函数来获取匹配表达式。

| 匹配对象方法 | 描述                                                         |
| :----------- | :----------------------------------------------------------- |
| group(num=0) | 匹配的整个表达式的字符串，group() 可以一次输入多个组号，在这种情况下它将返回一个包含那些组所对应值的元组。 |
| groups()     | 返回一个包含所有小组字符串的元组，从 1 到 所含的小组号。     |

#### re.match 与 re.search的区别

**re.match** 只匹配字符串的开始，如果字符串开始不符合正则表达式，则匹配失败，函数返回 None，而 **re.search** 匹配整个字符串，直到找到一个匹配。

### 检索和替换

Python 的re模块提供了re.sub用于替换字符串中的匹配项。

语法：

```
re.sub(pattern, repl, string, count=0, flags=0)
```

参数：

- pattern : 正则中的模式字符串。
- repl : 替换的字符串，也可为一个函数。
- string : 要被查找替换的原始字符串。
- count : 模式匹配后替换的最大次数，默认 0 表示替换所有的匹配。
- flags : 编译时用的匹配模式，数字形式。

前三个为必选参数，后两个为可选参数。

### compile 函数

compile 函数用于编译正则表达式，生成一个正则表达式（ Pattern ）对象，供 match() 和 search() 这两个函数使用。

语法格式为：

```
re.compile(pattern[, flags])
```

参数：

- pattern : 一个字符串形式的正则表达式

- flags 可选，表示匹配模式，比如忽略大小写，多行模式等，具体参数为：

- - re.IGNORECASE 或 re.I

  -  

  - \- 使匹配对大小写不敏感

  - re.L 表示特殊字符集 \w, \W, \b, \B, \s, \S 依赖于当前环境
  - re.MULTILINE 或 re.M - 多行模式，改变 ^ 和 $ 的行为，使它们匹配字符串的每一行的开头和结尾。
  - re.DOTALL 或 re.S - 使 **.** 匹配包括换行符在内的任意字符。
  - re.ASCII - 使 \w, \W, \b, \B, \d, \D, \s, \S 仅匹配 ASCII 字符。
  - re.VERBOSE 或 re.X - 忽略空格和注释，可以更清晰地组织复杂的正则表达式。

  这些标志可以单独使用，也可以通过按位或（|）组合使用。例如，re.IGNORECASE | re.MULTILINE 表示同时启用忽略大小写和多行模式。

### findall

在字符串中找到正则表达式所匹配的所有子串，并返回一个列表，如果有多个匹配模式，则返回元组列表，如果没有找到匹配的，则返回空列表。

**注意：** match 和 search 是匹配一次 findall 匹配所有。

语法格式为：

```
re.findall(pattern, string, flags=0)
或
pattern.findall(string[, pos[, endpos]])
```

参数：

- **pattern** 匹配模式。
- **string** 待匹配的字符串。
- **pos** 可选参数，指定字符串的起始位置，默认为 0。
- **endpos** 可选参数，指定字符串的结束位置，默认为字符串的长度。

### re.finditer

和 findall 类似，在字符串中找到正则表达式所匹配的所有子串，并把它们作为一个迭代器返回。

```
re.finditer(pattern, string, flags=0)
```

参数：

| 参数    | 描述                                                         |
| :------ | :----------------------------------------------------------- |
| pattern | 匹配的正则表达式                                             |
| string  | 要匹配的字符串。                                             |
| flags   | 标志位，用于控制正则表达式的匹配方式，如：是否区分大小写，多行匹配等等。参见：[正则表达式修饰符 - 可选标志](https://www.runoob.com/python3/python3-reg-expressions.html#flags) |

### re.split

split 方法按照能够匹配的子串将字符串分割后返回列表，它的使用形式如下：

```
re.split(pattern, string[, maxsplit=0, flags=0])
```

参数：

| 参数     | 描述                                                         |
| :------- | :----------------------------------------------------------- |
| pattern  | 匹配的正则表达式                                             |
| string   | 要匹配的字符串。                                             |
| maxsplit | 分割次数，maxsplit=1 分割一次，默认为 0，不限制次数。        |
| flags    | 标志位，用于控制正则表达式的匹配方式，如：是否区分大小写，多行匹配等等。参见：[正则表达式修饰符 - 可选标志](https://www.runoob.com/python3/python3-reg-expressions.html#flags) |

### 正则表达式对象

### re.RegexObject

re.compile() 返回 RegexObject 对象。

### re.MatchObject

group() 返回被 RE 匹配的字符串。

- **start()** 返回匹配开始的位置
- **end()** 返回匹配结束的位置
- **span()** 返回一个元组包含匹配 (开始,结束) 的位置

### 正则表达式修饰符 - 可选标志

| 修饰符                | 描述                                                         | 实例                                                         |
| :-------------------- | :----------------------------------------------------------- | :----------------------------------------------------------- |
| re.IGNORECASE 或 re.I | 使匹配对大小写不敏感                                         | `import re pattern = re.compile(r'apple', flags=re.IGNORECASE) result = pattern.match('Apple') print(result.group())  # 输出: 'Apple'` |
| re.MULTILINE 或 re.M  | 多行匹配，影响 **^** 和 **$**，使它们匹配字符串的每一行的开头和结尾。 | `import re pattern = re.compile(r'^\d+', flags=re.MULTILINE) text = '123\n456\n789' result = pattern.findall(text) print(result)  # 输出: ['123', '456', '789']` |
| re.DOTALL 或 re.S：   | 使 **.** 匹配包括换行符在内的任意字符。                      | `import re pattern = re.compile(r'a.b', flags=re.DOTALL) result = pattern.match('a\nb') print(result.group())  # 输出: 'a\nb'` |
| re.ASCII              | 使 \w, \W, \b, \B, \d, \D, \s, \S 仅匹配 ASCII 字符。        | `import re pattern = re.compile(r'\w+', flags=re.ASCII) result = pattern.match('Hello123') print(result.group())  # 输出: 'Hello123'` |
| re.VERBOSE 或 re.X    | 忽略空格和注释，可以更清晰地组织复杂的正则表达式。           | `import re pattern = re.compile(r'''    \d+  # 匹配数字    [a-z]+  # 匹配小写字母 ''', flags=re.VERBOSE) result = pattern.match('123abc') print(result.group())  # 输出: '123abc'` |

### 正则表达式模式

模式字符串使用特殊的语法来表示一个正则表达式。

字母和数字表示他们自身。一个正则表达式模式中的字母和数字匹配同样的字符串。

多数字母和数字前加一个反斜杠时会拥有不同的含义。

标点符号只有被转义时才匹配自身，否则它们表示特殊的含义。

反斜杠本身需要使用反斜杠转义。

由于正则表达式通常都包含反斜杠，所以你最好使用原始字符串来表示它们。模式元素(如 **r'\t'**，等价于 **\\t** )匹配相应的特殊字符。

下表列出了正则表达式模式语法中的特殊元素。如果你使用模式的同时提供了可选的标志参数，某些模式元素的含义会改变。

| 模式         | 描述                                                         |
| :----------- | :----------------------------------------------------------- |
| ^            | 匹配字符串的开头                                             |
| $            | 匹配字符串的末尾。                                           |
| .            | 匹配任意字符，除了换行符，当re.DOTALL标记被指定时，则可以匹配包括换行符的任意字符。 |
| [...]        | 用来表示一组字符,单独列出：[amk] 匹配 'a'，'m'或'k'          |
| [^...]       | 不在[]中的字符：[^abc] 匹配除了a,b,c之外的字符。             |
| re*          | 匹配0个或多个的表达式。                                      |
| re+          | 匹配1个或多个的表达式。                                      |
| re?          | 匹配0个或1个由前面的正则表达式定义的片段，非贪婪方式         |
| re{ n}       | 匹配n个前面表达式。例如，"o{2}"不能匹配"Bob"中的"o"，但是能匹配"food"中的两个o。 |
| re{ n,}      | 精确匹配n个前面表达式。例如，"o{2,}"不能匹配"Bob"中的"o"，但能匹配"foooood"中的所有o。"o{1,}"等价于"o+"。"o{0,}"则等价于"o*"。 |
| re{ n, m}    | 匹配 n 到 m 次由前面的正则表达式定义的片段，贪婪方式         |
| a\| b        | 匹配a或b                                                     |
| (re)         | 匹配括号内的表达式，也表示一个组                             |
| (?imx)       | 正则表达式包含三种可选标志：i, m, 或 x 。只影响括号中的区域。 |
| (?-imx)      | 正则表达式关闭 i, m, 或 x 可选标志。只影响括号中的区域。     |
| (?: re)      | 类似 (...), 但是不表示一个组                                 |
| (?imx: re)   | 在括号中使用i, m, 或 x 可选标志                              |
| (?-imx: re)  | 在括号中不使用i, m, 或 x 可选标志                            |
| (?#...)      | 注释.                                                        |
| (?= re)      | 前向肯定界定符。如果所含正则表达式，以 ... 表示，在当前位置成功匹配时成功，否则失败。但一旦所含表达式已经尝试，匹配引擎根本没有提高；模式的剩余部分还要尝试界定符的右边。 |
| (?! re)      | 前向否定界定符。与肯定界定符相反；当所含表达式不能在字符串当前位置匹配时成功。 |
| (?> re)      | 匹配的独立模式，省去回溯。                                   |
| \w           | 匹配数字字母下划线                                           |
| \W           | 匹配非数字字母下划线                                         |
| \s           | 匹配任意空白字符，等价于 [\t\n\r\f]。                        |
| \S           | 匹配任意非空字符                                             |
| \d           | 匹配任意数字，等价于 [0-9]。                                 |
| \D           | 匹配任意非数字                                               |
| \A           | 匹配字符串开始                                               |
| \Z           | 匹配字符串结束，如果是存在换行，只匹配到换行前的结束字符串。 |
| \z           | 匹配字符串结束                                               |
| \G           | 匹配最后匹配完成的位置。                                     |
| \b           | 匹配一个单词边界，也就是指单词和空格间的位置。例如， 'er\b' 可以匹配"never" 中的 'er'，但不能匹配 "verb" 中的 'er'。 |
| \B           | 匹配非单词边界。'er\B' 能匹配 "verb" 中的 'er'，但不能匹配 "never" 中的 'er'。 |
| \n, \t, 等。 | 匹配一个换行符。匹配一个制表符, 等                           |
| \1...\9      | 匹配第n个分组的内容。                                        |
| \10          | 匹配第n个分组的内容，如果它经匹配。否则指的是八进制字符码的表达式。 |

##  CGI编程???

CGI(Common Gateway Interface),通用网关接口,它是一段程序,运行在服务器上如：HTTP服务器，提供同客户端HTML页面的接口。

## 网络编程???

Python 提供了两个级别访问的网络服务。：

- 低级别的网络服务支持基本的 Socket，它提供了标准的 BSD Sockets API，可以访问底层操作系统Socket接口的全部方法。
- 高级别的网络服务模块 SocketServer， 它提供了服务器中心类，可以简化网络服务器的开发。

## SMTP发送邮件???

## 多线程???

## XML 解析???

## 日期和时间

Python 程序能用很多方式处理日期和时间，转换日期格式是一个常见的功能。

Python 提供了一个 time 和 calendar 模块可以用于格式化日期和时间。

时间间隔是以秒为单位的浮点小数。

每个时间戳都以自从 1970 年 1 月 1 日午夜（历元）经过了多长时间来表示。

Python 的 time 模块下有很多函数可以转换常见日期格式。

### 时间元组

| 序号 | 字段         | 值                                   |
| :--- | :----------- | :----------------------------------- |
| 0    | 4位数年      | 2008                                 |
| 1    | 月           | 1 到 12                              |
| 2    | 日           | 1到31                                |
| 3    | 小时         | 0到23                                |
| 4    | 分钟         | 0到59                                |
| 5    | 秒           | 0到61 (60或61 是闰秒)                |
| 6    | 一周的第几日 | 0到6 (0是周一)                       |
| 7    | 一年的第几日 | 1到366 (儒略历)                      |
| 8    | 夏令时       | -1, 0, 1, -1是决定是否为夏令时的标识 |

| 序号 | 属性     | 值                                                           |
| :--- | :------- | :----------------------------------------------------------- |
| 0    | tm_year  | 2008                                                         |
| 1    | tm_mon   | 1 到 12                                                      |
| 2    | tm_mday  | 1 到 31                                                      |
| 3    | tm_hour  | 0 到 23                                                      |
| 4    | tm_min   | 0 到 59                                                      |
| 5    | tm_sec   | 0 到 61 (60或61 是闰秒)                                      |
| 6    | tm_wday  | 0 到 6 (0是周一)                                             |
| 7    | tm_yday  | 一年中的第几天，1 到 366                                     |
| 8    | tm_isdst | 是否为夏令时，值有：1(夏令时)、0(不是夏令时)、-1(未知)，默认 -1 |

## MongoDB???

## urllib???

## operator 模块???

## math 模块???

##  requests 模块???

## random 模块

| 方法                                                         | 描述                                                         |
| :----------------------------------------------------------- | :----------------------------------------------------------- |
| [seed()](https://www.runoob.com/python3/python3-func-number-seed.html) | 初始化随机数生成器                                           |
| getstate()                                                   | 返回捕获生成器当前内部状态的对象。                           |
| setstate()                                                   | state 应该是从之前调用 getstate() 获得的，并且 setstate() 将生成器的内部状态恢复到 getstate() 被调用时的状态。 |
| getrandbits(k)                                               | 返回具有 k 个随机比特位的非负 Python 整数。 此方法随 MersenneTwister 生成器一起提供，其他一些生成器也可能将其作为 API 的可选部分提供。 在可能的情况下，getrandbits() 会启用 randrange() 来处理任意大的区间。 |
| [randrange()](https://www.runoob.com/python3/ref-random-randrange.html) | 从 range(start, stop, step) 返回一个随机选择的元素。         |
| [randint(a, b)](https://www.runoob.com/python3/ref-random-randint.html) | 返回随机整数 N 满足 a <= N <= b。                            |
| [choice(seq)](https://www.runoob.com/python3/python3-func-number-choice.html) | 从非空序列 seq 返回一个随机元素。 如果 seq 为空，则引发 IndexError。 |
| choices(population, weights=None, *, cum_weights=None, k=1)  | 从 population 中选择替换，返回大小为 k 的元素列表。 如果 population 为空，则引发 IndexError。 |
| [shuffle(x[, random\])](https://www.runoob.com/python3/python3-func-number-shuffle.html) | 将序列 x 随机打乱位置。                                      |
| sample(population, k, *, counts=None)                        | 返回从总体序列或集合中选择的唯一元素的 k 长度列表。 用于无重复的随机抽样。 |
| [random()](https://www.runoob.com/python3/python3-func-number-random.html) | 返回 [0.0, 1.0) 范围内的下一个随机浮点数。                   |
| [uniform()](https://www.runoob.com/python3/python3-func-number-uniform.html) | 返回一个随机浮点数 N ，当 a <= b 时 a <= N <= b ，当 b < a 时 b <= N <= a 。 |
| triangular(low, high, mode)                                  | 返回一个随机浮点数 N ，使得 low <= N <= high 并在这些边界之间使用指定的 mode 。 low 和 high 边界默认为零和一。 mode 参数默认为边界之间的中点，给出对称分布。 |
| betavariate(alpha, beta)                                     | Beta 分布。 参数的条件是 alpha > 0 和 beta > 0。 返回值的范围介于 0 和 1 之间。 |
| expovariate(lambd)                                           | 指数分布。 lambd 是 1.0 除以所需的平均值，它应该是非零的。   |
| gammavariate()                                               | Gamma 分布（ 不是伽马函数） 参数的条件是 alpha > 0 和 beta > 0。 |
| gauss(mu, sigma)                                             | 正态分布，也称高斯分布。 mu 为平均值，而 sigma 为标准差。 此函数要稍快于下面所定义的 normalvariate() 函数。 |
| lognormvariate(mu, sigma)                                    | 对数正态分布。 如果你采用这个分布的自然对数，你将得到一个正态分布，平均值为 mu 和标准差为 sigma 。 mu 可以是任何值，sigma 必须大于零。 |
| normalvariate(mu, sigma)                                     | 正态分布。 mu 是平均值，sigma 是标准差。                     |
| vonmisesvariate(mu, kappa)                                   | 冯·米塞斯分布。 mu 是平均角度，以弧度表示，介于0和 2*pi 之间，kappa 是浓度参数，必须大于或等于零。 如果 kappa 等于零，则该分布在 0 到 2*pi 的范围内减小到均匀的随机角度。 |
| paretovariate(alpha)                                         | 帕累托分布。 alpha 是形状参数。                              |
| weibullvariate(alpha, beta)                                  | 威布尔分布。 alpha 是比例参数，beta 是形状参数。             |

## statistics 模块

### math 模块方法

| 方法                                                         | 描述                                                     |
| :----------------------------------------------------------- | :------------------------------------------------------- |
| [statistics.harmonic_mean()](https://www.runoob.com/python3/ref-stat-harmonic_mean.html) | 计算给定数据集的调和平均值。                             |
| [statistics.mean()](https://www.runoob.com/python3/ref-stat-mean.html) | 计算数据集的平均值                                       |
| [statistics.median()](https://www.runoob.com/python3/ref-stat-median.html) | 计算数据集的中位数                                       |
| [statistics.median_grouped()](https://www.runoob.com/python3/ref-stat-median_grouped.html) | 计算给定分组数据集的分组中位数                           |
| [statistics.median_high()](https://www.runoob.com/python3/ref-stat-median_high.html) | 计算给定数据集的高位中位数                               |
| [statistics.median_low()](https://www.runoob.com/python3/ref-stat-median_low.html) | 计算给定数据集的低位中位数。                             |
| [statistics.mode()](https://www.runoob.com/python3/ref-stat-mode.html) | 算数据集的众数（出现频率最高的值）                       |
| [statistics.pstdev()](https://www.runoob.com/python3/ref-stat-pstdev.html) | 计算给定数据集的样本标准偏差                             |
| [statistics.stdev()](https://www.runoob.com/python3/ref-stat-stdev.html) | 计算数据集的标准差                                       |
| [statistics.pvariance()](https://www.runoob.com/python3/ref-stat-pvariance.html) | 计算给定数据集的样本方差                                 |
| [statistics.variance()](https://www.runoob.com/python3/ref-stat-variance.html) | 计算数据集的方差                                         |
| [statistics.quantiles()](https://www.runoob.com/python3/ref-stat-quantiles.html) | 计算数据集的分位数，可指定分位数的数量（默认为四分位数） |

## hashlib 模块???

## 量化???

## pyecharts 模块

yecharts 是一个基于 ECharts 的 Python 数据可视化库，它允许用户使用 Python 语言生成各种类型的交互式图表和数据可视化。

ECharts 是由百度开发的一款强大的开源数据可视化库，而 Pyecharts 则是 ECharts 的 Python 封装，使得在 Python 中使用 ECharts 变得更加方便。

pyecharts 提供了一组简单而灵活的 API，使用户能够轻松地创建各种图表，包括但不限于折线图、柱状图、散点图、饼图、地图等。

通过 pyecharts，用户可以使用 Python 语言处理和准备数据，然后使用简洁的代码生成交互式的图表，这些图表可以嵌入到 Web 应用程序中或保存为静态文件。

**pyecharts 特点与功能：**

- **简单易用：** Pyecharts 提供了直观而友好的 API，使得用户能够快速上手，轻松生成各种图表。
- **丰富的图表类型：** 支持多种常见的图表类型，包括线图、柱状图、散点图、饼图、地图等，满足不同场景的需求。
- **支持主流数据格式：** 能够处理常见的数据格式，如列表、字典、Pandas DataFrame 等。
- **交互性：** 生成的图表可以具有交互性，用户可以通过鼠标悬停、缩放等方式与图表进行互动。
- **丰富的配置选项：** 提供了丰富的配置选项，允许用户自定义图表的样式、布局等属性。
- **支持主题：** 提供多种主题，用户可以根据需要选择合适的主题，使图表更符合应用的整体风格。

### pyecharts 图表类型

| 图表类型     | pyecharts 类 | 包引入                                   |
| :----------- | :----------- | :--------------------------------------- |
| 折线图       | `Line`       | `from pyecharts.charts import Line`      |
| 柱状图       | `Bar`        | `from pyecharts.charts import Bar`       |
| 散点图       | `Scatter`    | `from pyecharts.charts import Scatter`   |
| 饼图         | `Pie`        | `from pyecharts.charts import Pie`       |
| 雷达图       | `Radar`      | `from pyecharts.charts import Radar`     |
| 热力图       | `HeatMap`    | `from pyecharts.charts import HeatMap`   |
| K 线图       | `Kline`      | `from pyecharts.charts import Kline`     |
| 箱线图       | `Boxplot`    | `from pyecharts.charts import Boxplot`   |
| 地图         | `Map`        | `from pyecharts.charts import Map`       |
| 词云图       | `WordCloud`  | `from pyecharts.charts import WordCloud` |
| 仪表盘       | `Gauge`      | `from pyecharts.charts import Gauge`     |
| 漏斗图       | `Funnel`     | `from pyecharts.charts import Funnel`    |
| 树图         | `Tree`       | `from pyecharts.charts import Tree`      |
| 平行坐标系图 | `Parallel`   | `from pyecharts.charts import Parallel`  |
| 桑基图       | `Sankey`     | `from pyecharts.charts import Sankey`    |
| 地理坐标系图 | `Geo`        | `from pyecharts.charts import Geo`       |
| 时间线图     | `Timeline`   | `from pyecharts.charts import Timeline`  |
| 3D 散点图    | `Scatter3D`  | `from pyecharts.charts import Scatter3D` |
| 3D 柱状图    | `Bar3D`      | `from pyecharts.charts import Bar3D`     |
| 3D 曲面图    | `Surface3D`  | `from pyecharts.charts import Surface3D` |