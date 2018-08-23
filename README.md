# HelloJava

记录《Head First Java》一书的读书笔记

----

### 2018-08-21  类

- 面向对象的Java编程思想，类是对象的模板，对象中包含变量和方法

- 创建对象时，他会被存放在称为堆的内存区域中，不管对象如何创建都会放在此区域中。此区域并非普通的堆。

- ``` Math.random()  // ```获取0到1之间的随机数

  ---

### 2018-08-22 变量

- 变量必须拥有类型，且变量必须要有名称

- 变量就像是杯子，是一种容器，可以承装某些事物

- primitive主数据类型的变量就像不同大小的杯子

  | 变量   | 杯子   | 大小    |
  | ------ | ------ | ------- |
  | byte   | 小杯   | 8 bits  |
  | short  | 中杯   | 16 bits |
  | int    | 大杯   | 32 bits |
  | long   | 重量杯 | 64 bits |
  | float  |        | 32 bits |
  | double |        | 64 bits |

- primitive主数据类型

  |          类型           |      位数      |          值域          |
  | :---------------------: | :------------: | :--------------------: |
  |         boolean         | Java虚拟机决定 |      true或false       |
  |          char           |    16 bits     |        0~65535         |
  | 数值Integer（带正负号） |                |                        |
  |          byte           |     8 bits     |        -128~127        |
  |          short          |    16 bits     |      -32768~32767      |
  |           int           |    32 bits     | -2147483648~2147483647 |
  |          long           |    64 bits     |      -很大~+很大       |
  |         浮点数          |                |                        |
  |          float          |    32 bits     |      范围模糊可变      |
  |         double          |    64 bits     |      范围模糊可变      |

- ``` float f = 32.5f;    // 注意"f"，声明float变量时，除非加上f，否则所有带小数点的值都会被Java当做double处理 ```

- ``` double d = 33456.98 ```

- 对象引用变量保存的是存取对象的方法，它并不是对象的容器，而是类似指向对象的指针。或者可以说是地址

- 对于任意Java虚拟机来说，所有的对象引用大小都一样。但不同的Java虚拟机间可能会以不同的方式来表示引用，因此某个Java虚拟机的引用大小可能会大于或小于另一个Java虚拟机的引用大小

- 使用公有与私有这两个存取修饰符来隐藏数据

- 封装的基本原则：将实例变量标记为私有的，并提供公有的getter和setter构造方法，来控制存取动作，目前这种做法可以维持安全性。将实例变量标记为private，将getter和setter标记为public

- 封装会对实例变量加上绝对领域，因此没有人能够恶搞变量。封装可以强迫其他的程序一定得经过setter。如此setter就能够检查参数并判断是否可以执行。setter也许可以退回不合理的值、或是抛出Exception、或者自己进行取小数的动作。重点在于你可以在setter中执行任何动作，直接暴露的public变量就没有这个功能

- 实例变量永远都会有默认值。如果你没有明确的赋值给实例变量，或者没有调用setter方法，实力变量还是会有值

  | integers(包括 char) | 0     |
  | ------------------- | ----- |
  | floating points     | 0.0   |
  | booleans            | false |
  | references          | null  |

- | 实例变量               | 局部变量           |
  | ---------------------- | ------------------ |
  | 声明在类内而不是方法中 | 声明在方法中       |
  |                        | 在使用前必须初始化 |

- 局部变量没有默认值。如果在局部变量初始化前就使用的话，编译器会显示错误

- 判断是否相等

  使用 == 来比较两个primitive主数据类型，或者判断两个引用是否引用同一个对象

  使用``` equals() ```来判断两个对象是否在意义上相等

- 极限编程(XP)思想：先编写测试用的代码。 伪代码 —> 测试码 —> 真实码

- 先写出一点点的测试码，然后只编写能够通过该测试的方法就好。之后再编写另一点测试码，再编写新的实现以让测试能够通过。经过如此循环，能够证明新加入的程序代码不会破坏原有已经测试过的部分。

- 以面向对象的方式来思考：专注于程序中出现的事物而不是过程
