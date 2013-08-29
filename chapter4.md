# <a name="4-Case-study-interface-design"></a> 第四章 案例学习：接口设计

_这一章的范例代码可以从 [http://thinkpython.com/code/polygon.py](http://thinkpython.com/code/polygon.py) 下载_

## <a name="4.1-TurtleWorld"></a> 4.1 乌龟的世界

伴随这本书，我已经写了 `Swampy` 的包。你可以从 [http://thinkpython.com/swampy](http://thinkpython.com/swampy) 下载；然后根据上面的指示在您的系统上安装 `Swampy` 。

一个包是一些模块的集合； `Swampy` 的其中一个模块叫 `TurtleWorld` , 它提供了一系列通过控制屏幕上的乌龟画直线的函数. 如果 `Swampy` 已经作为一个包在系统上安装好，你可以直接导入 `TurtleWorld` ：

    from swampy.TurtleWorld import *

如果你下载了 `Swampy` 模块，但还没安装成一个包，你也可以在含有 `Swampy` 的工作目录下导入 `TurtleWorld` ，你还可以将含有 `Swampy` 的目录添加到 Python 的查找路径(__search path__)

    from TurtleWorld import *

关于如何安装以及如何设置 Python 的查找路径的细节，取决于你的系统，详细请浏览： [http://thinkpython.com/swampy](http://thinkpython.com/swampy) 

创建一个名为 `mypolygon.py` 的文件，输入下面的代码：

    from swampy.TurtleWorld import *
    world = TurtleWorld()
    bob = Turtle()
    print bob
    wait_for_user()

第一行导入了 `TurtleWorld` 模块中的所有元素。
第二行创建了一个 `TurtleWorld` 对象，并赋值给 `world` 。
第三行创建了一个 `Turtle` 对象，并赋值给 `bob` 。
第四行输出 bob 对象，所输出的信息例如这样： `<TurtleWorld.Turtle instance at 0xb7bfbf4c>` 
这表示 bob 指向 `Turtle` 的一个实例。

在这里，_instance_ 表示一组成员中的一个；这只是其中一个可能的 Turtle 成员。

`wait_for_user` 告诉 _TurtleWorld_ 等待用户执行操作，尽管在这个情况下，用户只能关闭窗口。

`TurtleWorld` 提供了一些控制乌龟的函数: `fd` 和 `bk` 分别表示向前(forward)和退后(backward)，以及 `lt` 和 `rt` 表示向左或者向右转。另外每只乌龟掌握着一支笔，它可以“画”或“停”；如果笔是“画”的状态，乌龟就会留下它的痕迹。函数 `pu` 和 `pd` 代表画或者停。

如果想要画一个角，将下面的代码添加到程序中（创建 bob 之后，调用 wait_for_user 之前）：

    fd(bob, 100)
    lt(bob)
    fd(bob, 100)

第一行， 告诉 bob 向前走 100 步。
第二行告诉他向左转。
当你运行这个程序，你应该会看到 bob 向东走，接着再向北走，留下两条痕迹。

接下来试着画一个正方形。不要继续往下看，直到你的程序真的能够正确运行。
