Registers and RAM
========================
## 寄存器&内存/视频导读

本集重点是Memory (存储/内存两种含义)

存1位(Gated Latch,锁存器)

存8位(Register,寄存器)

16x16的矩阵存256位

数据选择器/多路复用器Muktiplexer)解码8位地址，定位到单个锁存器

16x16的矩阵中4位代表行。4位代表列

组合256位内存+多路复用器

可寻址的256字节内存

-条1980年代的内存，1M大小

8个模块，每个模块有32个小万块，

每个小方块有4个小块，每个小块是128位x 64位
## 小节

* 本节目标是先做只能存储1位的电路,之后再扩大，做出我们的内存模块,下次和ALU结合起来，做出CPU!

* The goal of this section is to first build a circuit that can only store 1 bit, then expand it to build our memory module, and next time combine it with ALU to build a CPU!



* **内存需求的产生**：使用ALU计算的数据有必要存储起来而非算完即弃,所以计算机还需要具备存储值的功能,以便于将来可能使用到该值进行连续操作.

* **Generation of Memory requirements**：It is necessary to store the data calculated by ALU rather than discard it after calculation. Therefore, the computer also needs to have the function of storing the value, so that the value may be used for continuous operation in the future.

* **"随机存取存储器(RAM)"**：只能在有电的情况下存储东西，比如游戏状态.

* **Random Access Memory(RAM)**：It stores things like game state,as long as the power stays on.

* **持久存储**：电源关闭时数据也不会丢失.

* **Persistent Memory**：It can survive without power.

* **Or Gate loop input storage 1**：然而有个小问题:这是永久的!(Except we've got a teensy tiny problem-this change is permanent!)

![06_01Or Gate loop input storage 1](media/06_01Or Gate loop input storage 1.png)

![06_02Or Gate loop input storage 1](media/06_02Or Gate loop input storage 1.png)

![06_03Or Gate loop input storage 1](media/06_03Or Gate loop input storage 1.png)

* **AND Gate loop input storage 0**：然而有个小问题:这是永久的!(Except we've got a teensy tiny problem-this change is permanent!)

![06_04AND Gate loop input storage 0](media/06_04AND Gate loop input storage 0.png)

![06_05AND Gate loop input storage 0](media/06_05AND Gate loop input storage 0.png)

![06_06AND Gate loop input storage 0](media/06_06AND Gate loop input storage 0.png)

* **AND-OR锁存器**：存1位,这叫"锁存”,因为它"锁定"了一个值,放入数据的动作叫"写入",拿出数据的动作叫”读取".

* **AND-OR Latch**：Save 1 bit.This is called a "latch" because it "latches onto" a particular value and stays that way.The action of putting data into memory is called writing, whereas getting the data out is called reading.

![06_07AND-OR Latch](media/06_07AND-OR Latch.png)

![06_08AND-OR Latch](media/06_08AND-OR Latch.png)

![06_09AND-OR Latch](media/06_09AND-OR Latch.png)

* **门锁**：

* **Gated Latch**：

![06_10Gated Latch](media/06_10Gated Latch.png)

![06_11Gated Latch Sketch Map](media/06_11Gated Latch Sketch Map.png)

![06_12Gated Latch Sketch Map](media/06_12Gated Latch Sketch Map.png)

![06_13Gated Latch Sketch Map](media/06_13Gated Latch Sketch Map.png)

![06_14Gated Latch Sketch Map](media/06_14Gated Latch Sketch Map.png)

![06_15Gated Latch Sketch Map](media/06_15Gated Latch Sketch Map.png)

* **寄存器**：存8位.一组这样的锁存器叫寄存器.寄存器能存一个数字.这个数字有多少位叫"位宽",早期电脑用8位寄存器,然后是16位，32位.如今许多计算机都有64位宽的寄存器.如果只有很少的位(bits)，把锁存器并排放置，也勉强够用了.64位寄存器要64根数据线，64根连到输出端,幸运的是,我们只要1根线启用所有锁存器,但加起来也有129条线了.如果存256位要513条线!解决方法是**矩阵**.所以对于256位的存储,只要35条线,1条数据线,1条允许写入线,1条允许读取线,还有16行16列的线用于选择锁存器(16+16=32.32+3=35).

* **register**：Save 8 bit.A group of lathes operating like this is called a register.which holds a single number and the number of bits in a register is called its width.Early computers had 8-bit registers, then16, 32,and today, many computers have registers that are 64-bits wide.Putting latches side-by-side works ok for a small-ish number of bits.A 64-bit register would need 64 wires running tothe data pins, and 64 wires running to the outputs.Luckily we only need 1 wire to enable all the latches, but that's still 129 wires.For 256 bits, we end up with 513 wires!The solutionis a **matrix**!This means in total, for 256 bits of memory,we only need 35 wires - 1 data wire, 1 write enable wire, 1 read enable wire,and 16 rows and columns for the selection.

![06_16 8-bit registers](media/06_16 8-bit registers.png)

![06_17 8-bit registers](media/06_17 8-bit registers.png)

![06_18 16 x 16 Latch matrix](media/06_18 16 x 16 Latch matrix.png)

![06_19 16 x 16 Latch matrix](media/06_19 16 x 16 Latch matrix.png)

![06_20 16 x 16 Latch matrix](media/06_20 16 x 16 Latch matrix.png)

![06_21 16 x 16 Latch matrix](media/06_21 16 x 16 Latch matrix.png)

![06_22 16 x 16 Latch matrix](media/06_22 16 x 16 Latch matrix.png)

![06_23 16 x 16 Latch matrix](media/06_23 16 x 16 Latch matrix.png)

![06_24 16 x 16 Latch matrix](media/06_24 16 x 16 Latch matrix.png)

![06_25 16 x 16 Latch matrix](media/06_25 16 x 16 Latch matrix.png)

![06_26 16 x 16 Latch matrix](media/06_26 16 x 16 Latch matrix.png)

* **多路复用器**：为了将地址转成行和列

* **Multiplexer**：To convert from an address into something that selects the right row or column,

![06_27 Multiplexer](media/06_27 Multiplexer.png)

![06_28 Multiplexer](media/06_28 Multiplexer.png)

![06_29 256-bit Memory](media/06_29 256-bit Memory.png)

![06_30 256-bit Memory Like Register](media/06_30 256-bit Memory Like Register.png)

![06_31 Random Access Menory](media/06_31 Random Access Menory.png)

* **随机访问内存(随机存取存储器)**：内存的一个重要特性是可以随时访问任何位置,所以叫RAM.当人们问你的RAM有多大,意思就是问你计算机的内存，RAM就像人们的**短期记忆,记录当前在做什么事.**

* **Random Access Memory(RAM)**： It can access any memory location, at any time, and in a random order.That the reason why it is called RAM.When people ask how big your RAM is, it means that they ask your computer's memory. RAM is like people's **short-term memory, recording what they are doing.**

![06_32 Random Access Menory](media/06_32 Random Access Menory.png)

![06_33 Random Access Menory](media/06_33 Random Access Menory.png)

![06_34 Random Access Menory](media/06_34 Random Access Menory.png)

![06_35 Random Access Menory](media/06_35 Random Access Menory.png)

![06_36 Random Access Menory](media/06_36 Random Access Menory.png)

![06_37 Random Access Menory](media/06_37 Random Access Menory.png)

![06_38 Random Access Menory](media/06_38 Random Access Menory.png)

![06_39 Random Access Menory](media/06_39 Random Access Menory.png)

![06_40 Random Access Menory](media/06_40 Random Access Menory.png)

![06_41 Random Access Menory](media/06_41 Random Access Menory.png)

![06_42 Random Access Menory](media/06_42 Random Access Menory.png)

* **静态随机存取存储器**：由锁存器制成

* **Static Random Access Memory(SRAM)**：Made of latch

* **其它类型的随机存取存储器**：如DRAM、内存和NVRAM.它们在功能上与SRAM相似.但用不同的电路存单个位.比如用不同的逻辑门,电容器，电荷捕获或忆阻器

* **other types of RAM**：such as DRAM, Flash memory, and NVRAM.These are very similar in function to SRAM,but use different circuits to store the individual  bits.for example, using different logic gates, capacitors, charge traps, or memristors.

