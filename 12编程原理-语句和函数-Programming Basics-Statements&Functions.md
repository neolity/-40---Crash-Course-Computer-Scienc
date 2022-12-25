Programming Basics-Statements&Functions
========================
## 编程原理-语句和函数/视频导读

变量, 赋值语句

Grace Hopper拍虫子游戏

if判断

while循环

for循环

函数

下集介绍算法

## 小节

* **语法**：规定句子结构的一系列规则叫语法, 英语有语法, 所有编程语言也都有语法.a=5是一个编程语言语句, 意思是创建一个叫a的变量, 把数字5放里面. 这叫"赋值语句". 把一个值赋给一个变量. 为了表达更复杂的含义, 需要更多语句. 比如, a=5, b=10, c=a+b. 除了abc, 也可以叫苹果、梨、水果.计算机不在乎你取什么名, 只要不重名就行. 当然取名最好还是有点意义, 方便别人读懂.程序是从第一条语句开始, 一句一句运行到结尾.

* **syntax**：The set of rules that govern the structure and composition of statements in a language is called syntax. The English language has syntax, and so do all programming languages. a = 5 is a programming language statement. In this case, the statement says a variable named A has the number 5 stored in it. This is called an assignment statement because we're assigning a value to a variable. To express more complex things, we need a series of statements, like "A is 5, B is 10, C equals A plus B". Instead of A, B and C it could be apples, pears, and frufts.The computer doesntcare, as long as variables are uniquely  named. But it's probably best practice to name them things that make sense in case someone else is trying to understand your code.and runs down one at a time until it hits the end. 

![12_01 Value](media/12_01 Value.png)

* **初始化**：设置最开始的值. 任何程序都会有它最基本的值, 比如游戏的初始关卡, 初始分数等. 

* **Initialize**：Set the initialvalue. Any program will have its most basic value. For example, initial level of the game, initial score, etc.

* **控制流语句**：为了做成交互式游戏, 程序的执行顺序要更灵活.不只是从上到下执行. 控制流语包有好几种, 最常见的是if语句. 可以想成是"如果X为真，那么执行Y". if 语句就像岔路口. 走哪条路取决于表达式的真假， 因此这些表达式又叫 **"条件语句"**. 如果希望根据条件执行多次, 需要 **"条件循环"**, 比如while语句, 也叫"while循环". 当while条件为真, 代码会重复执行. For 不判断条件, 判断次数, 会循环特定次数. 

* **Control Flow Statement**：To create an interactive game, we need to control the flow of the program. beyond just running from top to bottom. There are several types, but If Statements are the most common. You can think of them as "If X is true, then do Y". An IF statement is like a fork in the road. Which path you take is conditional on whether the expression is true or false, so these expressions are called **Conditional Statements**. To repeat some statements many times, we need to create a **conditional loop**. One way is a while statement also called a while loop. As you might have guessed, this loops a piece of code "while' a condition is true. For loop, in stead of being a condition-controlled loop that can repeat forever until the condition is false.

![12_02 Conditional Statements](media/12_02 Conditional Statements.png)

* **函数**：对于复用性高的代码, 可以将它打包成一个函数, 以便于在下次使用时直接调用. 函数的最后还要用到Return来返回一个结果给调用了这个函数的代码. 视频中还简要地讲述了嵌套函数. 

* **控制流语句**：For highly reusable code, you can package it into a function that can be called directly the next time you use it. Return is also used at the end of the function to return a result to the code calling the function.

![12_03 Function](media/12_03 Function.png)

![12_04 Function](media/12_04 Function.png)

* **模块化编程**：把编程模块化为函数不仅可以让单个程序员独立制作App, 也让团队协作可以写更大型的程序.不同程序员写不同函数, 只需要确保自己的代码工作正常, 把所有人的拼起来, 整个程序也应该能正常运作!

* **模块化编程**：Modularizing programs into functions not only allows asingle programmer to write an entire app, but also allows teams of people to work efficiently on even bigger programs. Different programmers can work on different functions, and if everyone makes sure their code works correctly, then when everything is put together, the whole program should work too!

* **库**：现代编程语言有很多预先写好的函数集合，叫"库".由专业人员编写， 不仅效率高， 而且经过了仔细检查， 几乎做所有事情都有库, 网络、图像、声音.

* **Libraries**：Modern programming languages come with huge bundles of pre-written functions, called Libraries. These are written by expert coders, made efficient and rigorously tested, and then given to everyone.There are libraries for almost everything, including networking, graphics, and sound.

