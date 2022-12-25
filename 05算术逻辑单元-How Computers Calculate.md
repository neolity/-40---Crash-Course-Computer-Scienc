How Computers Calculate
========================
## 计算机要怎样计算/视频导读

简单介绍ALU,英特尔74181

算术单元

半加器(处理1个bit, 2个输入)

全加器(处理1个bit, 3个输入)

8 bit加法(1个半加器。7个全加器)

溢出的概念，吃豆人的例子

乘法除法

逻辑单元

检测数字是否为0的电路(一堆OR门最后加个NOT门)

ALU抽象成个V符号

Flag标志(是否相等，是否小于，是否溢出等等)
## 小节

* 表示和存储数字是计算机的重要功能.(Representing and storing numbers is an important function of a computer)

* **"算术逻辑单元"的概念**：计算有意义的处理数字,比如把两个数字相加.等你理解了ALU的设计和功能之后,你就理解了现代计算机的基石,ALU就是计算机里负责运算的组件,基本其他所有部件都用到了它.

* **Concept of "Arithmetic and Logic Unit"(ALU)**：computation, or manipulating numbers in a structured and purposeful way,like adding two numbers together.When you understand an ALU'S design and function,you'll understand a fundamental part of modern computers.ALU is the component in the computer that is responsible for computing, and basically all other components use it.

* **"算术逻辑单元"详解**：ALU有2个单元，1个算术单元和1个逻辑单元.今天的重点是一切的根本,"把两个数字相加",我们可以用单个晶体管一个个拼,把这个电路做出来,但很快就会复杂的难以理解.所以用更高层的抽象即逻辑门来做.我们会用到AND，OR,NOT和XOR逻辑门.

* **Explanation of "Arithmetic and Logic Unit"(ALU)**：An ALU is really two units in one.there is an arithmetic unit and a logic unit.Today, we're going to focus on the piece of rsistance, the crme de la crme of operations that underlies almost everything else a computer does一adding two numbers together.We could build this circuit entirely out of individual transistors,but that would get confusing really fast.So we use the higher-level abstraction, that is, logic gates.In this Case: AND,OR,NOT andXORgates.

![05_01Logic Gate](media/05_01Logic Gate.png)

* **加法电路**：假设为2个bit加在一起(bit是0或1),有2个输入A和B，1个输出.就是两个数字的和.出现的4个组合中:0+0/0+1/1+0完全与XOR逻辑一致,而二进制中1+1=10,所以我们需要一根额外的线代表“进位”.只有输入是1和1时，“进位”才是"true".这个电路叫 **“半加器”**.还有之后的每列，我们得加3个位在一起，并不是2个,我们可以用半加器做**全加器**,最后用一个OR门检查进位是不是true.**全加器请自行用二进制的1+1+1作验证.** 有了半加器和全加器，我们就可以制作多位数相加的全加器,如"8位行波进位加法器".

* **Adding Circuit**：Assume that takes two binary digits, and adds them together.So we have two inputs, A and B, and one output, which is the sum of those two digits.Among the four combinations: 0+0/0+1/1+0 is completely consistent with XOR logic, but 1+1=10 in binary.So we need an extra output wire for that carry bit.The carry bitis only "true" when the inputs are1 AND 1.And that's it. This circuit is called a **half adder**.and every column after that we are going to have to add three bits together, no two.We can build a full adder using half adders.Lastly,we need a OR gate to check if either one of the carry bits was true.**Please use binary 1+1+1 to verify the full adder.** With a half adder and a full adder, we can make a full adder that adds multiple bits like 8-BIT RIPPLE CARRY ADDER.

![05_02half adder](media/05_02half adder.png)

![05_03half adder Sketch Map](media/05_03half adder Sketch Map.png)

![05_04add three bits together](media/05_04add three bits together.png)

![05_05full adder TAB](media/05_05full adder TAB.png)

![05_06full adder](media/05_06full adder.png)

![05_07full adder Sketch Map](media/05_07full adder Sketch Map.png)

![05_08BUILDING AN 8-BIT ADDER](media/05_08BUILDING AN 8-BIT ADDER.png)

* **溢出**：如果第9位有进位,代表着2个数字的和太大了,超过了8位,这叫溢出(overflow).通常，当加法运算的结果太大而无法用所使用的位数表示时，就会发生溢出,这会导致错误和不可预期的结果,比如著名的游戏"吃豆人"最多玩到255关，当超过后会乱码.如果想避免溢出,我们可以加更多全加器。可以操作16或32位数字.让溢出更难发生，但代价是更多逻辑门.另外一个缺点是，每次进位都要一点时间,所以现代计算机用的加法电路有点不同.叫 **"超前进位加法器"** .

* **overflow**：if there is a carry into the 9th bit, it means the sum of the two numbers is too large to fit into 8-bits,This is called an overflow.In general, an overflow occurs when the result of an addition is too large to be represented by the number of bits you are using.This can usually cause errors and unexpected behavior.For example, the famous game "Pac Man" can play up to 255 levels at most, and will be garbled when it exceeds.So if we want to avoid overflows,we can extend our circuit with more full adders, allowing us to add 16 or 32 bit numbers.This makes overflows less likely to happen, but at the expense of more gates.An additional downside is that it takes a little bit of time for each of the carries to ripple forward.For this reason, modern computers use a slightly different adding circuit.called a **"carry-look-ahead" adder**.

* **其它算术电路**：就像加法器一样,这些操作也是由逻辑门构成的.

* **Other arithmetic circuits**：And like our adder, these other operations are built from individual logicgates.

![05_09overflow](media/05_09overflow.png)

![05_10Other Math Operations](media/05_10Other Math Operations.png)

* **逻辑单元**：逻辑单元执行逻辑操作.例如一个检查ALU输出是否为0的电路.

* **Logic Unit**：The logical unit performs logical operations.For example, a circuit to check whether ALU output is 0.

![05_11Check whether ALU output is 0](media/05_11Check whether ALU output is 0.png)

![05_12Check whether ALU output is 0](media/05_12Check whether ALU output is 0.png)

![05_13ALU Sketch Map](media/05_13ALU Sketch Map.png)

![05_14Execution of ALU](media/05_14Execution of ALU.png)

![05_15Execution of ALU](media/05_15Execution of ALU.png)

![05_16Execution of ALU](media/05_16Execution of ALU.png)

![05_17Execution of ALU](media/05_17Execution of ALU.png)