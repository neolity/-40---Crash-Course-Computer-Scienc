The Central Processing Unit
========================
## 中央处理器(CPU)/视频导读

本集重点

1.拼个CPU出来

2. CPU怎么执行命令

RAM+寄存器+ALU 可做个CPU

解释“取指令 --> 解释 --> 执行"这个循环

时钟是什么，时钟速度和赫兹

超频提升性能,降频省电

## 小节

* 本节目标是做出CPU,我们把重点放在功能，而不是一根根线具体怎么连,当我们用一条线连接两个组件时,这条线只是所有必须线路的一个抽象,这种高层次视角叫"微体系架构".

* **本小节务必配套视频观看**

* We'll focus on functional blocks, rather than showing every single wire.When we do connect two components with a line,this is an abstraction for all of the necessary wires.This highlevel view is called the microarchitecture.

* **中央处理器(CPU)**：CPU负责执行程序,程序由一个个操作组成,这些操作叫 **"指令" (Instruction)**,因为它们指示"计算机要做什么",如果是**数学指令**,比如加/减,CPU会让ALU进行数学运算,也可能是**内存指令**，CPU会和内存通信,然后读/写值.

* **Central Processing Unit**：A CPU'S job is to execute programs,are made up of a series of individual operations called **instructions**, because they "instruct" the computer what to do.If these are **mathematical instructions**, like add or subtract,the CPU will configure its ALU to do the mathematical operation.Or it might be a **memory instruction**,which case the CPU will talk with memory to read and write values.

* **中央处理器(CPU)制作**：

1、RAM,为了保持简单，假设它只有16个位置，每个位置存8位.

2、四个8位寄存器，叫A, B，C,D.寄存器用来临时存数据和操作数据.

3、我们可以给CPU支持的所有指令，分配一个ID.在这个假设的例子,我们用前四位存"操作代码" (operation code),后四位代表数据来自哪里,可以是寄存器或内存地址.

4、我们还需要两个寄存器来完成CPU：一个寄存器追踪程序运行到哪里了,我们叫它 **"指令地址寄存器"**,顾名思义,存当前指令的内存地址；另一个寄存器存当前指令，叫 **"指令寄存器"**,

* **Central processing unit (CPU) production**：

1、RAM,To keep things simple, we'll assume it only has 16 memory locations ,each containing 8 bits.

2、Let's also give our processor four 8-bit memory registers, labeled A, B,C and D.which will be used to temporarily store and manipulate values.

3、We can assignan ID to each instruction supported by our CPU.In our hypothetical example, we use the first four bits to store the "operation code".The final four bits specify where the data for that operation should come from,this could be registers or an address in memory.

4、We also need two more registers to complete our CPU：First, we need a register to  keep track of where we are in a program, For this, we use an **instruction address register**,which as the name suggests, stores the memory address of the current instruction；And then we need the other register to store the current instruction,

![07_01 Instruction Table](media/07_01 Instruction Table.png)

![07_02 CPU Makeing](media/07_02 CPU Makeing.png)

![07_03 CPU Makeing](media/07_03 CPU Makeing.png)

* **中央处理器(CPU)运行阶段**：

**1、“取指令阶段”**:负责拿到指令;首先，将"指令地址寄存器"连到RAM.寄存器的值为0,因此RAM返回地址0的值，本例中,0010 1110会复制到"指令寄存器”里.现在指令拿到了,要弄清是什么指令,才能执行(execute).

**2、“解码阶段”**:本例中,前4位0010是LOADA指令,意思是，把RAM的值放入寄存器A.后4位1110是RAM的地址，转成十进制是14.接下来，指令由"控制单元"进行解码,就像之前的所有东西,"控制单元"也是逻辑门组成的,比如，为了识别"LOAD A"指令,需要一个电路,检查操作码是不是0010.

**3、“执行阶段”**:本例中,用"检查是否为LOAD A指令的电路",可以打开RAM的"允许读取线",把地址14传过去.RAM拿到值，0000 0011，即十进制的3.因为是LOAD A指令,我们把这个值只放到寄存器A,其他寄存器不受影响,所以需要一根线，把RAM连到4个寄存器,我们能用"检查是否为LOAD A指令的电路"启用寄存器A的"允许写入线",这样我们成功把RAM中地址14的值按照Load_A指令存入了寄存器A.我们把"指令地址寄存器"+1."执行阶段”就此结束.

* **Central processing unit (CPU) running phase**：

**1、The fetch phase**:This is where we retrieve our first instruction.First, we wire our Instruction Address Register to our RAM module.The register's value is O, so the RAM returns whatever value is stored in address 0.In this case,00101110.Then this value is copied into our instruction register.Now that we've fetched an instruction from memory,we need to figure out what that instruction is,so we can execute it.

**2、The decode phase**:In this case the opcode, which is the first four bits, is 0010.This opcode corresponds to the LOAD "A" instruction,which loads a value from RAM into Reqister A.The RAM address is the last four bits of our instruction which are 1110 or 14 in decimal.Next, instructions are decoded and interpreted by a Control Unit.Like everything else we've built, it too is made out of logic gates.For example, to recognize a LOAD A instruction,we need a circuit that checks if the opcode matches 0010.

**3、The execute phase**:In this case ,using the outputof our LOAD_A checking circuit,we can turn on the RAM's read enable line and send in address 14.The RAM retrieves the value at that address, which is 00000011,or 3 in decimal.Now, because this is a LOAD A instruction,we want that value to only be saved into Register A and not any of the other registers.So if we connect the RAM's data wires to our four  data registers,we can use our LOAD_A check circuit to enable the write enable only for Register A.In this way, we successfully set the value of address 14 in RAM according to Load_A instruction is stored in register A.To do this, we increment the Instruction Address Register by 1 which completes the execute phase.

![07_04 CPU_The fetch phase](media/07_04 CPU_The fetch phase.png)

![07_05 CPU_The decode phase_Check OPcode](media/07_05 CPU_The decode phase_Check OPcode.png)

![07_06 CPU_The decode phase](media/07_06 CPU_The decode phase.png)

![07_07 CPU_The execute phase](media/07_07 CPU_The execute phase.png)

![07_08 CPU_The execute phase_Done](media/07_08 CPU_The execute phase_Done.png)

![07_09 CPU_The execute phase_Done](media/07_09 CPU_The execute phase_Done.png)

* **指令**:LOAD_A只是CPU可以执行的各种指令之一.不同指令由不同逻辑电路解码.这些逻辑电路会配置CPU内的组件来执行对应操作.

* **instructions**:LOAD_A is just one of several possible instructions that our CPU can execute.Different instructions are decoded by different logic circuits,which configure the CPU'S components to performthat action.

![07_10 CPU_Control_Unit](media/07_10 CPU_Control_Unit.png)

![07_11 CPU_ALU](media/07_11 CPU_ALU.png)

![07_12 CPU_ALU](media/07_12 CPU_ALU.png)

![07_13 CPU_ALU](media/07_13 CPU_ALU.png)

![07_14 CPU_ALU](media/07_14 CPU_ALU.png)

* **时钟**:CPU的运行流程已经齐备，但我们仍需让CPU把握一个节奏去运行程序，切换CPU"取指令--解码--执行"三个不同状态，这时就需要一个计时器**时钟**来负责管理CPU的节奏.

* **Clock**:The running process of the CPU is complete, but we still need to let the CPU grasp a rhythm to run the program, and switch the three different states of the CPU: "fetch instruction -- decode -- execute". At this time, a timer **clock** is needed to manage the CPU rhythm.

![07_15 CPU_Clock](media/07_15 CPU_Clock.png)

![07_16 CPU_Clock](media/07_16 CPU_Clock.png)

![07_17 CPU_Clock](media/07_17 CPU_Clock.png)

![07_18 CPU_Clock](media/07_18 CPU_Clock.png)

* **时钟速度**:CPU每一步"取指令" --> "解码" --> "执行"(这里为3步)的速度.单位是赫兹,赫兹是用来表示频率的单位.1赫兹代表一秒1个周期.Carrie Anne花了大概6分钟为我们讲解了4条指令(读取--读取--相加--存储),意味着小姐姐的时钟速度大概是0.03赫兹(次/秒).(3 * 4 / (60 * 6))=0.0333(Hz)

* **Clock Speed**:The speed at which a CPU can carry out **each step** of the fetch-decode-execute cycle.This speed is measured in Hertz , a unit of frequency. One Hertz means one cycle per second.Carrie Anne spent about 6 minutes explaining four instructions (read -- read -- add -- store), which means that the clock speed of little sister is about 0.03 Hz (3 * 4 / (60 * 6))=0.0333(Hz)

* **超频/降频**:指修改中央处理单元的时钟速度,超频太多会让CPU过热或产生乱码，因为信号跟不上时钟;降频同样超有用,把CPU的速度降下来，可以省很多电,省电对用电池的设备很重要，比如笔记本和手机.可以加快或减慢时钟速度, 又叫做 **"动态调整频率"**.

* **Overfrequency/frequency reduction**:It refers to modifying the clock speed of the central processing unit,too much overclocking can either overheat the CPU or produce gobbledygook as the signals fall behind the clock;Underclocking also supper useful,by slowing the CPU down, you can save a lot of power,which is important for computers that run on batteries, like laptops and smartphones.It can speed up or slow down the clock, also called **"Dynamic Frequency Scaling"**.

![07_19 Completed_CPU](media/07_19 Completed_CPU.png)

