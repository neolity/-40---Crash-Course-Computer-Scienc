The First Programming Languages
========================
## 编程语言发展史/视频导读

编程:二进制 → 助记符(汇编器) → A-0 (编译器) → FORTRAIN

二进制写程序, 先纸上写伪代码, 手工转二进制, 很快就烦了

用"助记符”写代码(LOAD A_14) 为了把助记符转二进制,汇编器诞生(Assembler)

葛丽丝.霍普(Grace Hopper)哈佛1号计算机首批程序员，海军军官

设计了编程语言A-0

Grace 1952年做了第一个编译器(Compiler),实现A-O

变量(Variables)

FORTRAIN

COBOL

新语言

1960年代: ALGOL, LSP BASIC 

1970年代: Pascal, C, Smalltalk 

1980年代: C++, Objective-G, Perl

1990年代: Python, Ruby Java

## 小节

* **"机器语言"或"机器码"**：第8集中的00101110即代表Load_A 14, 这里使用了两种不同的语言(二进制和助记符), 就像英语和汉语一样, 两种不同的表达方式但同时表示着同一件事物, 只是编写的方式不一样, 计算机语言也一样, 正如所见, 计算机能处理二进制，二进制是处理器的"母语", 事实上，它们"只能"理解二进制, 所以又叫"机器码".

* **Machine Language or Machine Code.**：As we've seen, computer hardware can only handle raw, binary instructions.In fact, it's the only lanquage they're able to speak, so it also called Machine Code.

* **伪代码**：在计算机早期阶段,必须用机器码写程序, 具体来讲，会先在纸上用英语写一个"高层次版". 举例,"从内存取下一个销售额, 然后加到天、周、年的总和, 然后算税.这种对程序的高层次描述，叫**伪代码**.在纸上写好后, 用"操作码表"把为代码转成二进制机器码. 

* **Pseudo-Code**：In the early days of computing, people had to write entire programs in machine code. More specifically, they'd first write a high-level version of a program on paper, in English.For xample, "retrieve the next sale from memory, then add this to the running total for the day week and year, then calculate any taxto be added. An informal, high-level description of a program like this is called Pseudo-Code.Then, when the program was all figured out on paper, they'd painstakingly expand and translate it into binary macine code by hand, using things like opcode tables.

![11_01 Pseudo-Code](media/11_01 Pseudo-Code.png)

* **助记符**：很快人们就厌烦了伪代码转二进制,程序员开发出一种新语言, 更可读, 更高层次, 每个操作码分配一个简单名字叫"助记符", "助记符"后面紧跟数据，形成完整指令, 与其用1和0写代码, 程序员可以写"LOAD A_14", 

* **Mnemonics**：People quickly got fed up with this process.programmers had developed slightly higher-level languages that were more human-readable.Opcodes were given simple names, called mnemonics, which were followed by operands, to form instructions. So instead of having to write instructions as a bunch of 1's and 0's, programmers could write something like "LOAD_A 14".

* **汇编器**：CPU不知道LOAD_A 14是什么, 它不能理解文字, 只能理解二进制.所以程序员想了一个技巧, 写二进制程序来帮忙, 它可以读懂文字指令, 自动转成二进制指令. 汇编器读取用"汇编语言"写的程序，然后转成"机器码".随着时间推移, 汇编器有越来越多功能, 让编程更容易.其中一个功能是自动分析JUMP地址, 汇编器不用固定跳转地址, 而是让你插入可跳转的标签.

* **Assembler**：Of course, a CPU has no idea what "LOAD_A 14"is.It doesn't understand text-based language, only binary.They created reusable helper programs, in binary, that read in text-based instructions, and assemble them into the correspondling binary instructions automatically. It reads in a program written in an Assembly Language and converts it to native machine code. Over time, Assemblers gained new features that made programming even easier. One nifty feature is automatically figuring out JUMP addresses.assembler does away with raw jump addresses, and lets you insert little labels thatcan be jumped to.

![11_02 Automatically figuring out JUMP addresses](media/11_02 Automatically figuring out JUMP addresses.png)

![11_03 Automatically figuring out JUMP addresses](media/11_03 Automatically figuring out JUMP addresses.png)

![11_04 Automatically figuring out JUMP addresses](media/11_04 Automatically figuring out JUMP addresses.png)

![11_05 Automatically figuring out JUMP addresses](media/11_05 Automatically figuring out JUMP addresses.png)

* **编译器**：汇编只是修饰了一下机器码, 一般来说, 一条汇编指令对应一条机器指令. 所以汇编码和底层硬件的连接很紧密, 汇编器仍然强迫程序员思考, 用什么寄存器和内存地址. 如果你突然要个额外的数, 可能要改很多代码.汇编与机器指令是一一对应的,但一行高级编程语言, 可能会转成几十条二进制指令, 为了做到这种复杂转换, Hopper在1952年创造了第一个编译器. 编译器专门把高级语言转成低级语言, 比如汇编或机器码(CPU可以直接执行机器码).不用管寄存器或内存位置, 编译器会搞定这些细节，不用管底层细节.程序员只需要创建代表内存地址的抽象, 叫"变量".

* **Compiler**：Assembly Languages are still a thin veneer over machine code.to a corresponding machine instruction a one-to-one mapping. so it's inherently tied to the underlying hardware. And the assembler still forces programmers to think about which registers and memory locations they will use.If you suddenly needed an extra value, you might have to change a lot of code to fit it in. Assembly languages have direct, one-to-one mapping to machine instructions. But, a single line of a high-level programming language might result in dozens of instructions being executed by the CPU. To perform this complex translation, Hopper built the first compiler in 1952. that transforms "source" code written in a programming language into a low-level language, like assembly or the binary "machine code" that the CPU can directly process.Notice how there are no registers or memory locations to deal with, the compiler takes care of that stuff, abstracting away a lot of low-level and unnecessary complexity.The programmer just creates abstractions for needed memory locations, known as variables.

![11_06 Compiler](media/11_06 Compiler.png)

![11_07 Compiler](media/11_07 Compiler.png)

* **通用编译器**：最初FORTRAN代码只能跑在IBM计算机上, 1950年代大多数编程语言和编译器, 只能运行在一种计算机上.如果升级电脑, 可能要重写所有代码!因此工业界, 学术界, 政府的计算机专家在1959年组建了一个联盟, 数据系统语言委员会, Grace Hopper担任顾问, 开发一种通用编程语言, 可以在不同机器上通用, 最后诞生了一门高级, 易于使用, "普通面向商业语言", 简称COBOL. 为了兼容不同底层硬件, 每个计算架构需要一个COBOL编译器, 最重要的是, 这些编译器都可以接收相同COBOL代码, 不管是什么电脑.这叫"一次编写，到处运行".不必接触CPU特有的汇编码和机器码, 

* **Universal Compiler**：Initially, FORTRAN code could only be compiled and run on IBM computers. And most programing languages and compilers of the 1950s, could only run on a single type of computer.So,if you upgraded your computer, you'd often have to re-write all the code too! In response, computer experts from industry, academia and government formed a consortium in 1959.The Committee on Data Systems Languages, advised by our friend Grace Hopper, to guide the development of a common programming language that could be used across different machines. The result was the high-level, easy to use, Common Business-Oriented Language, or COBOL for short. To deal with different underlying hardware, each computing architecture needed its own COBOL compiler. But critically, these compilers could all accept the same COBOL source code, no matter what computer it was run on.This notionis called write once, run anywhere. a benefit of moving away from assembly and machine code, which is still CPU specific.

* 1960年代: ALGOL, LSP BASIC

* 1970年代: Pascal, C, Smalltalk

* 1980年代: C++, Objective-G, Perl

* 1990年代: Python, Ruby Java

* 新千年: Swift, C#, Go