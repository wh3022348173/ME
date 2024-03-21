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