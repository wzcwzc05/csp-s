# CSP-S初赛知识点整理

如题，2021届。

### 一、计算机硬件软件基础知识

- 第一台计算机：1946.2 ENIAC

- 第一位程序员：Ada Lovelace    

- 计算机届最高奖：图灵奖

- 冯诺依曼理论：计算机硬件设备：存储器、运算器、控制器、输入设备、输出设备。

- 1KB=1024B    1MB=1024KB   1GB=1024MB   1TB=1024GB  1PB=1024TB

- RAM是读写存储器，当断电时数据全部丢失;ROM是只读存储器，断电时数据不丢失。

- 外存储器——>内存储器——>Cache——>CPU

- 总线结构:   数据总线:传输数据信息  地址总线:传送地址信息  控制总线:传送控制信号，协调各部件之间的操作。

- CPU种类:

  Intel: Core ，Itanium、Pentium、8086

  AMD：Ryzen、Athlon64、Opteron

- 桌面操作系统：

  Unix系统:Linux发行版（如Ubuntu、Arch、Centos、Redhat等）、Mac OS X、FreeBSD、Solaris等

  类Unix：Windows

- 计算机语言:机器语言---->汇编语言----->高级语言

  汇编语言: 汇编源程序 ---翻译程序---> 目标程序 ---连接程序---> 可执行程序

  编译型语言(高级语言):C/C++、Pascal等    源程序 ---编译程序---> 目标程序 ---连接程序---> 可执行程序

  解释型语言(高级语言):ASP、PHP、Java、JavaScript、Python等     源程序 ---解释程序---> 可执行程序

  面向对象语言：几乎当代所有的高级语言都是面向对象的（C语言除外，C++面向对象）（世界上第二个面向对象语言是Smalltalk）

  高级语言的程序可移植性好、汇编语言的精简程度高。

- 进制转换：略

- 信息编码:
  最小单位:Bit（比特）表示一个"0"或"1"

  一个字节：由8个Bit组成。是存储器系统的最小存取单位。

  ASCII编码:7位二进制码（1个字节）

  一个中文字符：2个字节



### 二、基本数据结构

#### 1.栈

定义：栈是只能在某一端插入和删除的特殊线性表。栈也称为后进先出表（LIFO表）

表示方法：一个栈可以用定长为n的数组s来表示，用一个指针top指向栈顶。top=0时栈空，top=n时栈满，top<0时为下溢，top>n是为上溢。

进栈时top++，x[top]=n

出栈时top--

进栈时检查上溢，出栈时检查下溢。

<img src="https://bkimg.cdn.bcebos.com/pic/8b82b9014a90f603eab7c55f3912b31bb051eda7?x-bce-process=image/watermark,image_d2F0ZXIvYmFpa2U4MA==,g_7,xp_5,yp_5/format,f_auto" alt="img" style="zoom:50%;" />

#### 2.队列

定义:队列是限定在一端进行插入，另一端进行删除的特殊线性表。队列也称为先进先出表（FIFO）

表示方法：一个队列可以用一个数组q来表示，用一个指针front指向队头，rear指向队尾。

<img src="https://bkimg.cdn.bcebos.com/pic/7dd98d1001e939015d4345bb78ec54e737d196f6?x-bce-process=image/watermark,image_d2F0ZXIvYmFpa2U4MA==,g_7,xp_5,yp_5/format,f_auto" alt="img" style="zoom:50%;" />

由于入队和出队操作中，头尾指针只增加不减小，致使被删元素的空间永远无法重新利用。当队列中实际的元素个数远远小于向量空间的规模时，也可能由于尾指针已超越向量空间的上界而不能做入队操作。该现象称为"假上溢"现象。

对于这种现象可以使用循环队列。即当尾指针越过上界时，可以判断底部是否还有剩余空间，从而讲尾指针指向队尾。形象地来看，就像一个循环一样。

PS:对于循环队列中元素个数:n=(r-f+n)%n(其中r表示尾指针，f为头指针，n为数组大小)
