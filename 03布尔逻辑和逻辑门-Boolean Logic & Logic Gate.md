Boolean Logic & Logic Gate
========================
## 布尔逻辑和逻辑门/视频导读

什么是二进制，为什么用二进制布尔逻辑

3个基本操作: NOT, AND, OR

解释3个基本操作

XOR异或

## 小节

* **二进制**：只用开/关两种状态也可以代表信息.

* **Binary**：with just two states of electricity we can represent important information.


* **二进制的应用**：

1、电路闭合,电流流过,代表"真";电路断开,无电流流过,代表"假”.

2、二进制也可以写成1和0而不是true和false.

* **Binary Applications**：

1、In computers,an "on”state, when electity is flowing, represents true.The off state, no electricity flowing, represents false.

2、We can also write binary as 1's and 0's instead of true's and false's.

* **高进制的痛点**：状态越多，越难区分信号,如果手机快没电子或者附近有电噪音因为有人在用微波炉,信号可能会混在一起..而每秒百万次变化的晶体管会让这个问题变得更糟!

* **Multi base pain point**：The more intermediate states there are,the harder it is to keep them all seperate.If your smartphone battery starts running low or there's electrical noise,because someone's running a microwave nearby,the signals can get mixed up.And this problem only gets worse with transistors changing states millions of times per second!

![03_01Quanary System](media/03_01Quanary System.png)

* **二进制系统的便利**：所以我们把两种信号尽可能分开,只用“开"和"关"两种状态，可以尽可能减少这类问题;计算机用二进制的另一个原因是有一整个数学分支存在，专门处理"真"和“假”.且它已经解决了所有法则和运算.叫**布尔代数**.尤其是，晶体管可以通过各种连线组合实现布尔数学分支.

* **Convenience of binary system**：So, placing two signals as far apart as possible,using just 'on and off', gives us the most distinct signal to minimize these issues.Another reason computers use binary is that an entire branch of mathematics already existed that dealt exclusively with true and false values.And it had figured out all of the necessary rules and operations for manipulating them.It's called **Boolean Algebra**!In particular, transistors can branch Boolean mathematics through various wire combinations.

* **布尔代数**：乔治布尔(George Boole)是布尔二字的由来,布尔用逻辑方程系统而正式的证明真理(truth).

* **Boolean Algebra**：George Boole, from which Boolean Algebra later got its name,Boole's approach allowed truth to be systematically and formally proven, through logic equations.

* **布尔代数的三个基本操作:**：**NOT**, **AND**和**OR**

* **three fundamental operations in Boolean Algebra**：a **NOT**, an **AND**, and an **OR** operation.

![03_02NOT TAB](media/03_02NOT TAB.png)

* **晶体管中非逻辑的实现原理:** 把控制线当做输入(input),顶部的电极当做输出(output),底部的电极接地

* **The realization principle of "not" logic in transistors:** You can take the control line as the input, the top electrode as the output, and the bottom electrode as the grounding.

![03_03NOT In Transistor](media/03_03NOT In Transistor.png)

![03_04NOT In Transistor](media/03_04NOT In Transistor.png)

![03_05NOT In Transistor](media/03_05NOT In Transistor.png)

* **晶体管中与逻辑的实现原理:** 为了实现"AND门”,我们需要2个晶体管连在一起

* **The realization principle of "and" logic in transistors:** To build an AND gate, we need two transistors connected together.

![03_06AND TAB](media/03_06AND TAB.png)

![03_07AND In Transistor](media/03_07AND In Transistor.png)

![03_08AND In Transistor](media/03_08AND In Transistor.png)

* **晶体管中或逻辑的实现原理:** 实现"OR门"除了晶体管还要额外的线,不是串联起来。而是并联.

* **The realization principle of "or" logic in transistors:** Building an OR gate from transistors needs a few extra wires,instead of having two transistors in series- one after the other,we have them in parallel.

![03_09OR TAB](media/03_09OR TAB.png)

![03_10OR In Transistor](media/03_10OR In Transistor.png)

![03_11OR In Transistor](media/03_11OR In Transistor.png)

* **NOT Sketch Map:**：

![03_12NOT Sketch Map](media/03_12NOT Sketch Map.png)

* **AND Sketch Map:**：

![03_13AND Sketch Map](media/03_13AND Sketch Map.png)

* **OR Sketch Map:**：

![03_14OR Sketch Map](media/03_14OR Sketch Map.png)

* **晶体管中异或逻辑的实现原理:**

* **The realization principle of "xor" logic in transistors:** Building an OR gate 

![03_15XOR TAB](media/03_15XOR TAB.png)

![03_16XOR In Transistor](media/03_16XOR In Transistor.png)

![03_17XOR In Transistor](media/03_17XOR In Transistor.png)

![03_18XOR In Transistor](media/03_18XOR In Transistor.png)

* **XOR Sketch Map:**：

![03_19XOR Sketch Map](media/03_19XOR Sketch Map.png)