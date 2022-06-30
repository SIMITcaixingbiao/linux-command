set
===

显示或设置shell特性及shell变量,与env不同的是，它显示所有变量

## 补充说明

**set命令** 作用主要是显示系统中已经存在的shell变量，以及设置shell变量的新变量值。使用set更改shell特性时，符号"+"和"-"的作用分别是打开和关闭指定的模式。set命令不能够定义新的shell变量。如果要定义新的变量，可以使用declare命令以`变量名=值`的格式进行定义即可。

###  语法

```shell
set(选项)(参数)
```

###  选项

```shell
-a：标示已修改的变量，以供输出至环境变量。
-b：使被中止的后台程序立刻回报执行状态。
-C：转向所产生的文件无法覆盖已存在的文件。
-d：Shell预设会用杂凑表记忆使用过的指令，以加速指令的执行。使用-d参数可取消。
-e：若指令传回值不等于0，则立即退出shell。
-f：取消使用通配符。
-h：自动记录函数的所在位置。
-H Shell：可利用"!"加<指令编号>的方式来执行history中记录的指令。
-k：指令所给的参数都会被视为此指令的环境变量。
-l：记录for循环的变量名称。
-m：使用监视模式。
-n：只读取指令，而不实际执行。
-p：启动优先顺序模式。
-P：启动-P参数后，执行指令时，会以实际的文件或目录来取代符号连接。
-t：执行完随后的指令，即退出shell。
-u：当执行时使用到未定义过的变量，则显示错误信息。
-v：显示shell所读取的输入值。
-x：执行指令后，会先显示该指令及所下的参数。
```

###  参数

取消某个set曾启动的参数。

###  实例

使用declare命令定义一个新的环境变量"mylove"，并且将其值设置为"Visual C++"，输入如下命令：

```shell
declare mylove='Visual C++'   #定义新环境变量
```

再使用set命令将新定义的变量输出为环境变量，输入如下命令：

```shell
set -a mylove                 #设置为环境变量
```

执行该命令后，将会新添加对应的环境变量。用户可以使用env命令和grep命令分别显示和搜索环境变量"mylove"，输入命令如下：

```shell
env | grep mylove             #显示环境变量值
```

此时，该命令执行后，将输出查询到的环境变量值。

