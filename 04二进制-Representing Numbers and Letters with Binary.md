Representing Numbers and Letters with Binary
========================
## 用二进制表示数字和字母/视频导读

用十进制举例进制的原理，演示进制加法。存储单位MB GBTB等

正数。负数，整数，浮点数的表示

美国信息交换标准代码A ASCII,用来表示字符

UNICODE 1992年诞生，是字符编码标准，解决ASCII不够表达所有语言的问题

## 小节

* **位权**：对于多位数，处在某一位上的“1”所表示数值的大小，称为该位的位权。

* **Positional right**：For multi bit numbers, the size of the value represented by "1" in a bit is called the bit weight of the bit.

* **示例**：

* **(1010)10 读作十进制的1010**

l.十进制数的特点是逢十进一。例如：

(1010)10 =1× 10^3+0× 10^2+1× 10^1+0× 10^0

2.二进制数的特点是逢二进一。例如：

(1010)2 =l× 2^3+0 × 2^2+l× 2^1+0 × 2^0=(10)10

3.八进制数的特点是逢八进一。例如：

(1010)8 =l× 8^3+0 × 8^2+l× 8^1+0 × 8^0=(520)10

4.十六进制数的特点是逢十六进一。例如：

(BAD)16 =11× 16^2+10×16^1+13×16^0=(2989)10

* **位**：二进制中，每一个1或0,叫一"位"

* **Bit**：Each of these binary digits,1 or 0, is called a "bit".

* **字节**：计算机曾经大多为8个位进行数据处理，所以8个位有另一个别称叫做字节.8位最大的二进制数值为11111111,即255.二进制里，1千字节 = 2的10次方 = 1024字节,如今计算机多为32位或64位,即每32/64位作为一块来处理数据.

* **Byte**：most computers process data for 8 bits, so another 8 bits is called byte.The maximum binary value of 8 bits is 11111111, i.e. 255.In binary,a kilobyte has two to the power of 10bytes, or 1024.Nowadays, most computers are 32-bit or 64 bit, that is, every 32/64 bit is used as a block to process data.

![04_01Display of different bit pixels](media/04_01Display of different bit pixels.png)

* **位址**：指64位数据中单独留一位表示数据的属性.如用第一位的0和1表示数据的正负.除了负数和正数,计算机也要处理非整数.比如12.7和3.14,或"星历43989.1".**在32位浮点数中,第1位表示数字的正负,接下来8位存指数,剩下23位存有效位数**.同时我们也要表示文字,与其用特殊方式来表示字母,计算机可以用数字表示字母.

* **Address**：It refers to the attribute of 64 bit data that only one bit is left to represent the data. For example, 0 and 1 of the first bit represent the positive and negative of the data.In addition to negative and positive numbers,computers must deal with numbers that are not whole numbers,like 12.7and 3.14, or maybe even stardate:43989.1.**In a 32-bit floating point number,the first bit is used for the sign of the number -- positiveor negative.The next 8 bits are used to store the exponent,and the remaining 23 bits are used to store the significand**.At the same time, we should also express words.However, rather than have a special form of storage for letters,computers simply use numbers to represent letters.

![04_03 32-bit storage format](media/04_03 32-bit storage format.png)

* **浮点数**：小数点可以在数字间浮动.有好几种方法表示浮点数.最常见的是IEEE 754标准,

* **"floating point" numbers**：The decimal point can float around in the middle of number.Several methods have been developed to represent floating point numbers.The most common of which is the IEEE 754 standard.

![IEEE 754](media/IEEE 754.png)

* **美国信息交换标准代码**：美国信息交换标准代码(ASCII)发明于1963年，是7位代码,足够存128个不同值.ASCI是个很早的标准,被广泛使用,让不同公司制作的计算机,能互相交换数据这种通用交换信息的能力叫"互用性”.但有个限制:它是为英语设计的.

* **ASCII**：ASCII, the American Standard Code for Information Interchange.Invented in 1963, ASCII was a 7-bit code, enough to store 128 different values.ASCI is an early standard and is widely used. It allows computers made by different companies to exchange data with each other. This general ability to exchange information is called "interoperability".However, it did have a major limitation: it was really only designed for English.

![04_04ASCII](media/04_04ASCII.png)

![04_05Extended ASCII](media/04_05Extended ASCII.png)

* **Unicode**：统一所有编码的标准,设计于1992年，解决了不同国家不同标准的问题.Unicode用一个统编码方案,最常见的Unicode是16位的，有超过一百万个位置,对所有语言的每个字符都够了.100多种字母表加起来占了12万个位置.

* **Unicode**：one formatto rule them all.Devised in 1992 to finally do awaywith all of the different international schemes.it replaced them with one universal encoding scheme.The most common version of Unicode uses 16 bits with space for over a million codes.enough for every single character from every language ever used.more than 120,000 of them in over 100 types of script.

* **其它存储格式**：就像ASCII用二进制来表示字母一样,其他格式比如MP3或GIF,用二进制编码声音/颜色，表示照片电影，音乐,重要的是，**这些标准归根到底是一长串位.**

* **Other storage formats**：And in the same way that ASCII defines a scheme for encoding letters as binary numbers,other file formats - like MP3s or GIFS - use binary numbers to encode sounds orcolors of a pixel in our photos, movies, and music.Most importantly, **under the hood it all comes down to long sequences of bits.**

