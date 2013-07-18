# <a name="3-Functions"></a> 函数

## <a name="3.1-Function-calls"></a> 函数调用

在程序上下文环境里, 函数是指一系列呈现如何进行计算的语句. 当你定义一个函数的时候, 你需要指明函数的名和这些语句. 然后你才可以通过"呼叫"函数名来调用函数. 我们已经看过一个函数调用的例子了:

    >>> type(32)
    <type 'int'>

这个函数的函数名是 "type". 括号里的表达式被称为__函数的形参(argument of the function)__. 这个函数调用的结果是告诉你形参是什么类型. 

我们通常说函数 "采用(take)" 一个形参, 并且 "返回(return)" 结果. 这个被返回的结果称为"返回值".

## <a name="3.2-Type-conversion-functions"></a> 类型转换函数

Python 提供了能将数据从一个类型转换到另一个类型的内置函数. `int()` 函数能够获取任何值,如果获得的值能够转换,那么它将转换成一个整型数据.

    >>> int('32')
    32
    >>> int("Hello")
    ValueError: invalid literal for int(): Hello
    
`int()` 函数能够将浮点型数据转换成整型数据, 但它并不是采用四舍五入的方法,而是舍弃尾数.

    >>> int(3.99999)
    3
    >>> int(-2.3)
    -2
    
`float()` 能够将整型数据或字符串转换成浮点数字:

    >>> float(32)
    32.0
    >>> float("3.14159")
    3.14159
    
最后, `str()` 能够将他的参数转换成字符串:

    >>> str(32)
    '32'
    >>> str(3.14159)
    '3.14159'

## <a name="1.3-Math-functions"></a> 数学运算函数

Python 有一个数学模块提供了几乎所有数学函数. __模块__是指一个包含了相关函数集合的文件.

在我们使用模块之前,我们需要导入(import)它:

    >>> import math

这个语句创建了一个名为 math 的模块对象. 如果你打印模块对象, 你会得到一些关于它的信息:

    >>> print math
    <module 'math' (built-in)>

模块对象包含了定义在模块里的函数和变量. 为了访问一个函数, 你需要指定模块名和函数名, 并且用一个点分割开(也就是著名的句号). 这种格式被称为点符号.

    >>> ratio = signal_power / noise_power
    >>> decibels = 10 * math.log10(ratio)

    >>> radians = 0.7
    >>> height = math.sin(radians)

第一个例子利用 log10 来计算信噪比(假定 signal_power 和 noise_power 已经定义). 数学模块同时也提供 log 函数来计算基于 e 的对数.

第二个例子计算 radians 的正弦值. 变量名已经暗示了比如 `sin` 等其他三角函数(如 `cos`, `tan`) 是以弧度为单位计算的. 从角度转换成弧度需要除以 360 并乘上 2π .

    >>> degrees = 45
    >>> radians = degrees / 360.0 * 2 * math.pi
    >>> math.sin(radians)
    0.707106781187

表达式 `math.pi` 会从数学模块中取得 π 的值的近似值, 精确 15 个数字.
如果你了解三角函数, 你可以对比 2 的平方根除以 2 的值:

    >>> math.sqrt(2) / 2.0
    0.707106781187
