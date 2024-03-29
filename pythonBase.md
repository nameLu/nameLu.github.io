#Python基础的细小知识点

python好久之前就学会了。但是基础学的比较匆忙，这回看七月7老师的python基础课顺便补习一下细小python知识点，一些我自己大概之前已经掌握的点就不记录了，就记录一点我觉得自己可能会注意不到的点。

```
如何在Mac下打开python的IDLE

在终端里输入`IDLE`就可以进入python2.x的IDLE；要想进入python3.x的IDLE的话，就输入`IDLE3`（前提你安装了python3.x）

```

##基本类型知识点

###float

1. float是python中的浮点类型，在例如C这样的语言中浮点分为单精度类型（float）和双精度（double）两种，python中的float不分单双精度，默认就是双精度。
2. 两个整数相除就会变成浮点数。例如2/2 --> 1.0；要想两个整数相处得整数要用`//`符号，2//2 --> 1，但是注意一点`//`是把小数点直接舍弃，比如1//2 --> 0。

###进制转化

1. 常用进制有十进制、八进制、二进制和十六进制。
    - 十进制在python是默认表示不用加任何符号
    - 八进制要在前面加`0o`，例如0o12 = 10
    - 二进制要在前面加`0b`，例如0b10 = 2
    - 十六进制要在前面加`0x`， 例如0xAF = 175

2. 进制间的互相转化函数
    - `bin()` 任意进制转化成二进制
    - `int()` 任意进制转化成十进制
    - `hex()` 任意进制转化成十六进制
    - `oct()` 任意进制转化成八进制

###Boolean

1. boolean类型只有True和False，并且python中的这两个保留字是开头字母大写的
2. 任意类型的非空字符和非0数字都可以转化成True，也在if这样的逻辑中判定为True，例如\['dd'\], {'a', 'b'}, 'hello', 23等等
3. 任意空字符和0都会被判定为False，例如Null, \[\], {}, '', 0

###String

1. 三引号`‘’‘`字符表示多行字符串，可以输入回车算字符串的一部分
    - 在IDLE中多行字符串中的回车会被输出成\n，只有使用print函数时输出多行字符串才会显示换行。
2. 在字符串前面加r就会变成原始字符串，就是特殊字符无效，不用额外加反义字符了（不加默认为普通字符串）
    - 例如 `print("C:\nadtd\ndd")`会被显示成
        ```
            C:
            adtd
            dd
        ```
    加了r（大写的R也可以）后
        ```
        print(r"C:\nadtd\ndd")
        C:\nadtd\ndd"
        ```

###特殊字符

**\n表示回车，\r表示换行，它俩的区别是：**
1. \r本义表示光标重新回到本行开头，\n本义表示光标往下一行（不一定是下一行开头）。
2. 在不同的操作系统中\r和\n的意义不一样， 在win中，两个字符表示本义；在unix类系统下，\n表示换到下一行的开头；在Mac中，\r表示回到本行开头并前往下一行。enter键一般是这两个的结合。
3. \r一般是换行但是光标还在本行，\n是换行并且光标也在下一行.