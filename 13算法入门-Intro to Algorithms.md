Intro to Algorithms
========================
## 算法入门/视频导读

选择排序 Selection sort

大O表示法 Big O notation

归并排序 Merge sort

Dijkstra 算法

## 小节

* **算法**：重要的是，之前写的指数函数, 只是无数解决方案的一种, 还有其它方案, 用不同顺序写不同语句也能得到一样结果, 不同的是"算法", 意思是:解决问题的具体步骤. 即使结果一致，有些算法会更好. 一般来说，所需步骤越少越好.

* **Algorithm**：Importantly, the function we wrote tocalculate exponents is only one possible solution, there are otherways to write this function, that achieve exactly the same numerical result. The difference between them is the algorithm, that is the specific steps used to complete the computation. Some algorithms are better than others even if they produce equal results. Generally, the fewer steps it takes to compute, the better it is.

* **排序**：排序到处都是. 找最便宜的机票. 按最新时间排邮件, 按姓氏排联系人. 排序的方法有很多种.

* **Sorting**：Computers sort allthe time. Looking forthe cheapest airfare, arranging your email by most recently sent, or scrolling your contacts by last name. 

![13_01 Sorting Method](media/13_01 Sorting Method.png)

![13_02 Sorting Method](media/13_02 Sorting Method.png)

![13_03 Sorting Method](media/13_03 Sorting Method.png)

![13_04 Sorting Method](media/13_04 Sorting Method.png)

![13_05 Sorting Method](media/13_05 Sorting Method.png)

![13_06 Try to Sort](media/13_06 Try to Sort.png)

![13_07 Selection sort](media/13_07 Selection sort.png)

![13_08 Selection sort](media/13_08 Selection sort.png)

* **算法的复杂度**：这意味着, 大致来说, 如果要选择排序排N个东西, 要循环N次, 每次循环中再循环N次，共N * N,或N^2.算法的输入大小和运行步骤之间的关系, 叫算法的复杂度.表示运行速度的量级.又称**大O表示法**.算法复杂度O(N^2)效率不高. 总之，"归并排序"的算法复杂度是O(n * log2 n), n是需要比较 + 合并的次数, 和数组大小成正比, log2 N 是合并步骤的次数.

* **The complexity of the algorithm**： This means, very roughly, that if we want to sort N items by selection sort, we have to loop N times, inside of which, we loop N times, for a grand total of roughly N times N loops,or N squared. This relationship of input size to the number of steps the algorithm takes to run characterizes the complexity of the Selection Sort algorithm. It gives you an approximation of how fast, or slow, an algorithm is going to be.Also called **"big O notation"**.N squared is not particularly efficient. In a word, the algorithm complexity of "merge sort" is O (n * log2n). n is the number of times to compare + merge, which is proportional to the size of the array. Log2N is the number of merge steps.

![13_09 big O notation](media/13_09 big O notation.png)

[13_01 merge_sort](attachments/13_01 merge_sort.mp4)

![13_10 merge_sort](media/13_10 merge_sort.png)

* **图搜索**："图"是用线连起来的一堆"节点", 可以想成地图, 每个节点是一个城市, 线是公路, 一个城市到另一个城市, 花的时间不同, 可以用成本(cost)或权重(weight)来代称.最简单的方法是尝试每一条路, 计算总成本, 这是蛮力方法,这种方法的时间复杂度为O(n!),n是节点数,效率比O(N^2)还低.和排序一样, 图搜索的算法也很多, 有不同的优缺点.

* **Graph Search**：A graph is a network of nodes connected by lines. You can think of it like a map, with cities and roads connecting them.Routes between these cities take different amounts of time. We can label each line with what is called a cost or weight. The easiest way is to try every  road and calculate the total cost. This is a brute force method. This would have an N factorial complexity.N is the number of nodes, which is lower than O (N ^ 2).Like sorting, there are many graph search algorithms with different advantages and disadvantages.

![13_11 Graph Search](media/13_11 Graph Search.png)

[13_02 Dijkstra_Algorithm](attachments/13_02 Dijkstra_Algorithm.mp4)

* **Dijkstra 算法**：Djkstra算法的原始版本. 构思于1956年, 算法复杂度是O(n^2). 原始版本的效率还不够好, 意味着输入不能太大, 比如美国的完整地图, 不过后边Dijkstra 算法得到改进, 算法复杂度是O(n * lg n + l).n是节点数, l是多少条线, 虽然看起来更复杂, 但效率更快.

* **Dijkstra Algorithm**：Djkstra's original algorithm,conceived in 1956, had a complexity of the number of nodes in the graph squared. The efficiency of the original version is not good enough, which means that the input cannot be too large, such as the complete map of the United States. However, the Dijkstra algorithm has been improved, and the algorithm complexity is O (n * lg n + l) N is the number of nodes and l is the number of lines. Although it looks more complex, it is more efficient.

![qownnotes-media-gqCcdU](media/qownnotes-media-gqCcdU.png)
