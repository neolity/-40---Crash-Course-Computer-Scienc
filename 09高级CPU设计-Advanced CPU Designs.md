Advanced CPU Designs
========================
## 高级CPU设计/视频导读

早期是加快晶体管切换速度，来提升CPU速度

给CPU专门的除法电路+其他电路来做复杂操作。比如游戏视频解码

给CPU加缓存, 提高数据存取速度，更快喂给CPU用计算餐馆销售额举例

脏位, Dirty bit

流水线设计, 用1个洗衣机和1个干燥机举例

乱序执行 out-of-ord erexecuton

推测执行 speculative execunion

分支预测 branch prediction 

多个ALU

多核(Core)

多个独立CPU

超级计算机，中国的"神威大湖之光"
## 小节

* **数据传输问题**：超高的时钟速度带来另一个问题, 如何快速传递数据给CPU.RAM是CPU之外的独立组件,意味着数据要用线来传递，叫"总线",总线可能只有几厘米, 别忘了电信号的传输接近光速, 但CPU每秒可以处理上亿条指令, 很小的延迟也会造成问题. RAM自己也还需要时间找地址取数据， 配置，输出数据.所以一条"从内存读数据“的指令可能要多个时钟周期而在此期间CPU空等数据.

* **Data Transmission Problems**：Now, high clock speeds and fancy instruction sets lead to another problem, getting data in and out of the CPU quickly enough.RAM is typically a memory module that lies out side the CPU.This means that data has to be transmitted to and from RAM along sets of data wires called a bus.This bus might only be a few centimeters long, and remember those electrical signals are traveling near the speed of light, but when you are operating at gigahertz speeds, that's billionths ofasecond- even this small delay starts to become problematic.It also takes time for RAM itself to lookup the address, retrieve the data and configure itself for output.So a "load from RAM" instruction might take dozens of clock cycles to complete, and during this time the processor is just sitting there idly waiting for the data.

![09_01 CPU&RAM](media/09_01 CPU&RAM.png)

* **数据传输问题的解决办法一**：解决延迟的方法之一是给CPU加-点RAM,叫 **"缓存"**.因为处理器里空间不大, 所以缓存一般只有KB或MB, 而RAM都是GB起.缓存提高了速度.CPU从RAM拿数据时, RAM不用传一个, 可以传一批, 虽然花的时间久一点，但数据可以存在缓存, 这很实用，因为数据常常是一个个按顺序处理, 缓存因为离CPU近, 一个时钟周期就能给数据, CPU不用空等, 比反复去RAM拿数据快得多!缓存也可以当临时空间, 存一些中间值，适合长/复杂的运算.

* **The first solutions to data transmission problems**：One solution is to put a little piece of RAM right on the CPU -- called a **cache**.There isn't a lot  of space on a processor's chip, so most caches are just kilobytes or maybe megabytes in size, where RAM is usually gigabytes. Having a cache speeds things up in a clever way.When the CPU requests a memory location from RAM the RAM can transmit, but it allows this data block to be saved into the cache.This tends to be really useful because computer data is often arranged and processed sequentially, it can typically provide the data in a single clock cycle, no waiting required, This speeds things up tremendously over having to go back and forth to RAM every single time.The cache can also be used like a scratch space, storing intermediate values when performing a longer, or more complicated calculation.

![09_02 CPU&CACHE](media/09_02 CPU&CACHE.png)

![09_03 CPU&Transmission](media/09_03 CPU&Transmission.png)

* **缓存命中/缓存未命中**：想要的数据已经在缓存叫缓存命中; 如果想要的数据不在缓存叫缓存未命中.

* **Cache Hit/Cache Miss**：When data requested in RAM is already stored in the cache like this it's called a cache hit; and if the data requested isn't in the cache,so you have to go to RAM,its a called a cache miss.

* **脏位**：假设从RAM拿100到200地址的数值放进缓存里并逐条做运算, 最终想把结果存进RAM地址150, 此时就像之前一样并不是直接存进RAM地址150而是将数据先存进缓存, 这样不仅存储时更快, 同时如果要接着算也可以更快取出来. 但这样也会带来一个有趣的问题, 缓存和RAM上的数据不一致了(因为RAM传输进缓存中的那批数据会有部分数据被新计算出来的数据覆盖掉), 这种不一致必须记录好, 之后要作数据同步.因此缓存里的每一块内存空间都会有一个特殊的标记叫做 **"脏位"**.同步一般发生在当缓存满了但CPU又要用到缓存时, 在清理缓存腾出空间之前, 会先检查一遍缓存的脏位, 如果位置是"脏"的, 在加载新内容之前, 会先把数据数据写会RAM. 

* **dirty bit**：Suppose we take 100 to 200 address values from RAM and put them into the cache and perform operations one by one. Finally, we want to store the results in RAM address 150. At this time, as before, we do not directly store the data in RAM address 150, but store the data in the cache first. This is not only faster for storage, but also faster for subsequent calculations. However, this also brings an interesting problem. The data in the cache and RAM are inconsistent (because some of the data transferred into the cache by RAM will be overwritten by the newly calculated data). This inconsistency must be recorded, and then the data must be synchronized. Therefore, each memory space in the cache will have a special flag called **"dirty bit"**.Synchronization usually occurs when the cache is full but the CPU needs to use the cache again. Before clearing the cache to make room, it checks the dirty bit of the cache. If the location is "dirty", it writes the data to RAM before loading new content.

![09_04 CPU&Cache Write Back](media/09_04 CPU&Cache Write Back.png)


* **数据传输问题的解决办法二**：另一种提升性能的方法叫 **"指令流水线"**, 处理器也可以流水线设计.但是和缓存一样, 它也会带来一些问题, 第一个大难题是指令之间的依赖关系, 举个例子, 你可能正在读取某个数据, 但是正在执行的指令会修改这个数据.所以流水线处理器要先弄清数据的依赖性, 在必要时停止流水线, 避免出问题. 高端CPU比如笔记本或手机, 会更进一步去动态排序有依赖关系的指令并最小化流水线的停工时间,这叫 **"乱序执行"**.第二个难题是 **"条件跳转"**. 比如上一集的JUMP NEGATIVE(跳转如果是负数), 这些指令会根据某一个值改变程序的执行方向(流向), 简单的流水线处理器, 看到JUMP(跳转)指令会停一会儿, 等待条件值确认下来, 只有等JUMP(跳转)的结果出来, 处理器才继续流水线, 因为空等会造成延迟, 所以高端处理器会使用一些技巧, 想象一个JUMP(跳转)指令是一个岔路口, 高端CPU会先猜测那一条路的概率更大, 然后提前把指令放进流水线,这叫**预测执行**, 当JUMP(跳转)的结果出来, CPU若猜对了, 流水线上早已塞满了正确的指令, 可以马上执行; 但若CPU猜错了, 就要清空流水线, 就像走错路掉头一样.为了尽可能减少清空流水线的次数, CPU厂商开发了复杂的方法来猜测哪条分支更有可能, 叫做 **"分支预测"**,现代CPU的正确概率已经超过90%.

* **The second solutions to data transmission problems**：Another trick to boost cpu performance is called **instruction pipelining**. Processor designs can apply the same idea.But like caching, it also brings some problems. The first big problem is the dependency between instructions. For example, you may be reading some data, but the executing instruction will modify the data Therefore, the pipeline processor should first understand the dependence of data, and stop the pipeline when necessary to avoid problems. High end CPUs, such as laptops or mobile phones, will further dynamically sort dependent instructions and minimize pipeline downtime, which is called **"out-of-order  execution"**.The second problem is **"conditional jump"**. For example, in the previous episode of JUMP NEGATIVE(Jump If it is a negative number), these instructions will change the execution direction (flow direction) of the program according to a certain value. Simple pipeline processors will stop for a while when they see JUMP instructions and wait for the condition value to be confirmed. The processor will continue to pipeline only when JUMP results are available. Because waiting will cause delay, high-end processors will use some techniques, Imagine that a JUMP instruction is a fork in the road. The high-end CPU will first guess which road has a higher probability, and then put the instruction into the pipeline in advance, which is called **Speculative Execution**. When the JUMP result comes out, if the CPU guesses correctly, the pipeline is already full of correct instructions, and can be executed immediately; But if the CPU guesses wrong, it will perform a **pipeline flush**, just like turning around in a wrong way. In order to minimize the number of times the pipeline is emptied, CPU manufacturers have developed complex methods to guess which branch is more likely, called **"branch prediction"**. The correct probability of modern CPUs has exceeded 90%.

![09_05 instruction pipelining](media/09_05 instruction pipelining.png)

![09_06 Process in order](media/09_06 Process in order.png)

![09_07 Process in order](media/09_07 Process in order.png)

![09_08 The possibility of instruction pipelining](media/09_08 The possibility of instruction pipelining.png)

![09_09 The possibility of instruction pipelining](media/09_09 The possibility of instruction pipelining.png)

![09_10 Instruction Pipelining](media/09_10 Instruction Pipelining.png)

* **超标量处理器**：理想情况下, 流水线一个时钟周期完成1个指令,然后"超标量处理器"出现了, 一个时钟周期完成多个指令.即便有流水线设计, 在指令执行阶段中, 处理器里仍有些区域还是可能会空闲, 比如在执行一个"从内存取值"指令期间, ALU会闲置, 所以一次性处理多条指令(取指令+解码)会更好.如果多条指令需要用到的组件在CPU中不同的部分, 那这样就可以多条同时执行.举例，很多CPU有四个、八个甚至更多完全相同的ALU, 可以同时执行多个数学运算.

* **Superscalar Processors**：In an ideal case, pipelining lets you complete one instruction every single clock cycle, but then superscalar processors came along which can execute more than one instruction per clock cycle.Even with pipelining, there are still areas of the processor that may be idle during instruction execution, such as ALU that is idle during the execution of a "fetch from memory" instruction, so it is better to process multiple instructions at once (fetch + decode). If multiple instructions require components in different parts of the CPU, then multiple instructions can be executed at the same time.For example, many processors will have four、 eight or more identical ALUs, so they can execute many mathematial instructions all in parallel!

![09_11 Superscalar Processors](media/09_11 Superscalar Processors.png)

* **截至目前为止, 我们讨论的都是优化1个指令流的运行效率; 另一个提升性能的方法是同时运行多个指令流, 即用多核处理器.**

![09_12 Servel Instruction Process](media/09_12 Servel Instruction Process.png)

![09_13 multi-core processors](media/09_13 multi-core processors.png)

![09_14 Quad Core Processors](media/09_14 Quad Core Processors.png)

![09_15 Quad Core Processors](media/09_15 Quad Core Processors.png)

![09_16 Quad Core Processors](media/09_16 Quad Core Processors.png)

![09_17 Quad Core Processors](media/09_17 Quad Core Processors.png)

![09_18 Quad Core Processors](media/09_18 Quad Core Processors.png)

* 当多个核也不够时, 可以用多个CPU, 高端计算机, 比如现在给你传视频的YouTube服务器, 需要更大的马力, 让上百人能同时流畅观看. 

* 超级计算机: 要做怪兽级运算像模拟宇宙形成, 便需要用到及其强大的计算能力.截止安妮的视频发布,世上最快的计算机为中国无锡的神威.太湖之光(40960个CPU, 每个CPU256个核心)