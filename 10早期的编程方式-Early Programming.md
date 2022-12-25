Early Programming
========================
## 早期的编程方式/视频导读

本集重点:早期计算机如何编程

打孔纸卡 → 插线板 → 面板拨开关

开头说本集重点:程序如何进入计算机

拿纺织业举例，给机器编程的需求远在计算机出现前就有了

打孔纸卡 Punched card

插线板 Plugboard

冯诺依曼架构 Von Neumann Archtecture

面板编程 Panel progrannming

第一款取得商业成功的家用计算机: Atair 8800

编程依然很困难,人们需要更友好更简单的方式编程L

下周主题:编程语言

## 小节

* **程序如何进入计算机**：但事实是, 程序需要加载进内存.编程的需求可追溯到计算机出现之前的纺织业, 为便于纺织出漂亮图案, 约瑟夫:玛丽.雅卡尔发明了可编程纺织机, 每一行的图案由**可穿孔纸卡**决定, 为了让每行图案不同，纸卡连成长条, 形成连续指令.事实证明穿孔纸卡便宜、可靠、也易懂.穿孔纸卡存的是数据，不是程序.为了正确执行不同计算, 程序员需要某种控制面板,面板有很多小插孔，程序员可以插电线, 让机器的不同部分互相传数据和信号,因此, 也叫 **"插线板"**, 不幸的是, 这意味着运行不同程序要重新接线, 所以到1920年代，控制面板变成了可拔插, 让编程更方便, 可以给机器插入不同程序.比如, 一个插线板算销售税, 另一个算工资单. 但给插线板编程很复杂, 人们急需更快、更灵活的新方式来编程, 好消息是后边内存变得可行, 价格下降, 容量上升, 与其把程序存在插线板, 把整个程序存在内存变得可行, 这样程序易于修改、方便CPU快速读取, 这类机器叫"存储程序计算机".如果内存足够, 不仅可以存要运行的程序, 还可以存程序需要的数据, 包括程序运行时产生的新数据. 

* **how a program gets into a computer**：But in reality, programs haveto be loaded into a computer's memory.The need for programming goes back to the textile industry before the advent of computers. To make it easier to produce beautiful patterns for textiles, Joseph Marie Jacquard developed a programmable textile loom.The pattern for each row of the cloth was defined by a **punched card**. To vary the pattern across rows these punch cards were arranged in long chains, forming a sequence of commands for the loom.Punched cards, turned out to be a cheap, reliable, faily human-readable way t ostore data.punched cards stored data, but not a program. So that different calculations could be performed, a programmer accessed a control panel, this panel was full of little sockets into which a programmer would plug cables.To pass values and signals between dfferent parts of the machine. For this reason they were also called **plug boards**.Unfortunately this meant having to rewire the machine each time a different programneeded to be run, And so by the 1920s these plug boards were made swappable. This not only made programming a lot more comfortable, but also allowed for different programs be plugged into a machine.For example one board might be wired to calculate sales tax, while another helps with payroll.But plug boards were fiendishly complicated to program. So the new faster more flexible way to program machines was badly needed.The good news is that the back memory is working.As costs fell, memory size grew, instead of storing a program as a physical plug board of wires, it became possible to store a program entirely in a computer's memory, where it could be easily changed by programmers and quickly accessed by the CPU, these machines were called Stored-program Computers.With enough computer memory you could store not only the program you wanted to run, but also any data your program would need.including new values it created along the way.

![10_01 control panel](media/10_01 control panel.png)

![10_02 Plug Board_hard to program](media/10_02 Plug Board_hard to program.png)

* **"冯诺依曼结构"**：程序和数据都存在这个地方. 冯诺依曼计算机的标志是, 一个处理器(有算术逻辑单元) + 数据寄存器 + 指令寄存器 + 指令地址寄存器 + 内存(负责存数据和指令).你现在看视频的计算机，仍在用一样的架构.

* **The Von Neumann Architecture**：Unifying the program and data into a single shared memory is called the Von Neumann Architecture. The hallmarks of a Von Neumann computer are a processing unit containing an arithmetic logic unit, data registers and instruction register and instruction address register and finally a memory to store both data and instructions. And even the computer you are watching this video right now, uses the same architecture.

![10_03 The Von Neumann Architecture](media/10_03 The Von Neumann Architecture.png)

* **用穿孔卡载入程序**：虽然有内存很棒, 但程序和数据依然需要某种方式输入计算机. 早期使用的是穿孔卡.

* **Load program with Punch Card**：Now electronic computer memory is great and all. but you still have to load the program and data into the computer before it can run. Earlier uses were perforated cards. 

![10_04 Punch Card](media/10_04 Punch Card.png)

* **纸带**：基本是回事，只不过更连续，不是一张张卡.

* **Punched Paper Tape**：Which is basically the same idea, but continuous instead of being on individual cards.

![10_05 Punched Paper Tape](media/10_05 Punched Paper Tape.png)

* **其它存写硬件**：当然我们还没提硬盘, 只读光盘DVD, U盘等等

* **Other memory and write hardware**： And of course we haven't talked about Hard Drives, CD-ROMs, DVDS, USB-Thumb drives and other similar goodies.

![10_06 Other memory and write hardware](media/10_06 Other memory and write hardware.png)

* **面板编程**：在1980年代前的另一种常见编程方式, 与其插一堆线到插线板, 可以用一大堆开关和按钮, 做到同样的效果, 面板上有指示灯，代表各种函数的状态和内存中的值. 

* **Panel programming**：Another common programming method before the 1980s was, Rather than having to physically plug in cables to activate certain functions, this could also be done with huge panels full of switches and buttons, And there were indicator lights to display the status of various functions and values in memory. 

![10_07 Panel programming](media/10_07 Panel programming.png)

* 不管是插线板、开关或穿孔纸卡, 早期编程都是专家活, 不管是全职还是技术控, 都要非常了解底层硬件, 比如操作码, 寄存器等, 才能写程序.

* Whether it was plug board, switches or punched paper, Programming these early computers was the realm of experts, either professionals who did this for living or technology enthusiasts, so things like processor op-codes and register wits, to write programs. 
