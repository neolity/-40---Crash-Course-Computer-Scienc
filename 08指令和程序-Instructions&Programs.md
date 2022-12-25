Instructions&Programs
========================
## 指令和程序/视频导读

本集重点: 一步步带你运行遍程序

回顾上集的例子程序，一步步讲解。介绍”指令集"的概念

LOAD A, LOAD B, SUB, JUMP, ADD, HALT等指令

带条件跳转JUMIP NEGATIVE 是负数才跳转,还有其他类型的JUMP

真正现代CPU用更多指令集, 位数更长

1971年的英特尔4004处理器有46个指令

如今英特尔酷睿7有上千条指令

## 小节

* 本节目标是运行遍程序,CPU之所以强大，是因为它是可编程的,如果写入不同指令，就会执行不同任务,所以**CPU是一块硬件，可以被软件控制!**

* The thing that makes a CPU powerful is the fact that it is programmable, if you write a different sequence of instructions, then the CPU will perform a different task.**So the CPU is a piece of hardware which is controlled by easy-to-modifty software!**

![08_01 Simplified Instructions](media/08_01 Simplified Instructions.png)

![08_02 Simplified Instructions](media/08_02 Simplified Instructions.png)

![08_03 Instructions Execute](media/08_03 Instructions Execute.png)

![08_04 More Instructions](media/08_04 More Instructions.png)

![08_05 Halt Instructions](media/08_05 Halt Instructions.png)

![08_06 Data&Instructions](media/08_06 Data&Instructions.png)

![08_07 Halt ](media/08_07 Halt .png)

![08_08 Never Stop](media/08_08 Never Stop.png)

![08_09 Infinit Loop](media/08_09 Infinit Loop.png)

![08_10 Jump Out The Loop](media/08_10 Jump Out The Loop.png)

* **指令的长度**：现代计算机不可能像本例子一样只有8个位来做指令，因为8个位最多只能兼容16个操作码以及选中16个内存地址，这太少了;所以现代计算机有两种策略来解决这个问题:最直接的方法是用更多位来代表指令,比如32位或64位;第二个策略是 **"可变指令长度"** , 举个例子, 比如某个CPU用8位长度的操作码,如果看到HALT指令,HALT不需要额外数据,那么会马上执行;如果看到JUMP, 它得知道位置值, 这个值在JUMP的后面,这叫"立即值.这样设计, 指令可以是任意长度, 但会让读取阶段复杂一点点.要说明的是, 我们拿来举例的CPU和指令集都是假设的,是为了展示核心原理.

* **Instruction length**: It is impossible for modern computers to use only 8 bits for instructions, as in this example, because 8 bits can only be compatible with 16 operation codes at most and 16 memory addresses can be selected, which is too few; So modern computers have two strategies to solve this problem:The most straightforward approach is just to have bigger instructions, with more bits, like 32 or 64 bits.The second approach is to use **variable length instructions**,For example, imagine a CPU that uses 8 bit opcodes,When the CPU sees an instruction that needs no extra values, like the HALT instruction, it can just execute it immediately. However, if it sees something like a JUMP instruction, it knows it must also fetch, the address to jump to, which is saved immediately behindthe JUMP instruction in memory,This is called, logically enough, an Immediate Value.In such processor designs, instructions can be any number of bytes long,which makes the fetch cycle of the CPU a tad more complicated.Now, our example CPU and instruction set is hypothetical,designed to ilustrate key working principles.

![08_11 CPU Instance](media/08_11 CPU Instance.png)

