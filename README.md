# Algorithm

极客时间上的 [数据结构与算法之美](https://time.geekbang.org/column/intro/100017301) 学习总结

方便自己回顾

## 开篇

经典书籍《算法导论》

## 入门篇

### 为什么要学习数据结构和算法？

数据结构与算法作为计算机的基础知识、核心知识，都是必须要掌握的。

### 如何抓住重点，系统高效地学习数据结构与算法？

#### 广义：

- 数据结构就是指一组数据的存储结构。
- 算法就是操作数据的一组方法。

**数据结构和算法是相辅相成的，数据结构是为算法服务的，算法要作用在特定的数据结构之上。**

#### 复杂度分析。

数据结构和算法解决的是如何更省、更快地存储和处理数据的问题，因此，我们就需要一个考量效率和资源消耗的方法，这就是复杂度分析方法。

### 常用的数据结构和算法

- 10 个数据结构：数组、链表、栈、队列、散列表、二叉树、堆、跳表、图、Trie 树；
- 10 个算法：递归、排序、二分查找、搜索、哈希算法、贪心算法、分治算法、回溯算法、动态规划、字符串匹配算法。

### 复杂度分析（上）：如何分析、统计算法的执行效率和资源消耗？

#### 为什么需要复杂度分析？

通过统计、监控，就能得到算法执行的时间和占用的内存大小。叫事后统计法。但是，这种统计方法有非常大的局限性。

1. 测试结果非常依赖测试环境
2. 测试结果受数据规模的影响很大

#### 大 O 复杂度表示法

1. 时间复杂度表示代码执行时间随数据规模增长的变化趋势，所以，也叫作渐进时间复杂度（asymptotic time complexity），简称时间复杂度。
2. 空间复杂度全称就是渐进空间复杂度（asymptotic space complexity），表示算法的存储空间与数据规模之间的增长关系。

#### 几种常见时间复杂度

多项式量:

- 常量阶 O(1)
- 对数阶 O(logn)
- 线性阶 O(n)
- 线性对数阶 O(nlogn)
- 平方阶 O(n^2) 、O(n^3) 、O(n^k)

非多项式量级:

- 指数阶 O(2^n)
- 阶乘阶 O(n!)

#### 几种常见空间复杂度

我们常见的空间复杂度就是 O(1)、O(n)、O(n2 )，像 O(logn)、O(nlogn) 这样的对数阶复杂度平时都用不到。

### 复杂度分析（下）：浅析最好、最坏、平均、均摊时间复杂度

- 最好情况时间复杂度（best case time complexity）
- 最坏情况时间复杂度（worst case time complexity）
- 平均情况时间复杂度（average case time complexity）
- 均摊时间复杂度（amortized time complexity）

## 基础篇

### 数组：为什么很多编程语言中数组都从0开始编号？

从数组存储的内存模型上来看，**下标** 最确切的定义应该是 `偏移（offset）`。

数组作为非常基础的数据结构，通过下标随机访问数组元素又是其非常基础的编程操作，效率的优化就要尽可能做到极致。所以为了减少一次减法操作，数组选择了从 0 开始编号，而不是从 1 开始。

- 如何实现随机访问？
- 低效的“插入”和“删除”
- 警惕数组的访问越界问题
- 容器能否完全替代数组？

### 链表（上）：如何实现LRU缓存淘汰算法?

#### 五花八门的链表结构

1. 单链表
2. 循环链表
3. 双向链表
4. 双向循环链表

#### 链表 VS 数组性能大比拼

从 插入删除、随机访问 对比

数组和链表是两种截然不同的内存组织方式。正是因为内存存储的区别，它们插入、删除、随机访问操作的时间复杂度正好相反。

### 链表（下）：如何轻松写出正确的链表代码？

- 技巧一：理解指针或引用的含义
- 技巧二：警惕指针丢失和内存泄漏
- 技巧三：利用哨兵简化实现难度
- 技巧四：重点留意边界条件处理
- 技巧五：举例画图，辅助思考
- 技巧六：多写多练，没有捷径

LeetCode 练习题
1. [单链表反转](https://leetcode.com/problems/reverse-linked-list/)
2. [链表中环的检测](https://leetcode.com/problems/linked-list-cycle/)
3. [两个有序的链表合并](https://leetcode.com/problems/merge-two-sorted-lists/)
4. [删除链表倒数第 n 个结点](https://leetcode.com/problems/remove-nth-node-from-end-of-list/)
5. [求链表的中间结点](https://leetcode.com/problems/middle-of-the-linked-list/)

### 栈：如何实现浏览器的前进和后退功能？

我们使用两个栈，X 和 Y，我们把首次浏览的页面依次压入栈 X，当点击后退按钮时，再依次从栈 X 中出栈，并将出栈的数据依次放入栈 Y。当我们点击前进按钮时，我们依次从栈 Y 中取出数据，放入栈 X 中。当栈 X 中没有数据时，那就说明没有页面可以继续后退浏览了。当栈 Y 中没有数据，那就说明没有页面可以点击前进按钮浏览了。

#### 如何理解“栈”？

后进者先出，先进者后出，这就是典型的“栈”结构。从栈的操作特性上来看，栈是一种“操作受限”的线性表，只允许在一端插入和删除数据。

#### 如何实现一个“栈”？

实际上，栈既可以用数组来实现，也可以用链表来实现。用数组实现的栈，我们叫作顺序栈，用链表实现的栈，我们叫作链式栈。

#### 栈在函数调用中的应用

函数调用栈。每进入一个函数，就会将临时变量作为一个栈帧入栈，当被调用函数执行完成，返回之后，将这个函数对应的栈帧出栈。

#### 栈在表达式求值中的应用

实际上，编译器就是通过两个栈来实现的。其中一个保存操作数的栈，另一个是保存运算符的栈。我们从左向右遍历表达式，当遇到数字，我们就直接压入操作数栈；当遇到运算符，就与运算符栈的栈顶元素进行比较。

如果比运算符栈顶元素的优先级高，就将当前运算符压入栈；如果比运算符栈顶元素的优先级低或者相同，从运算符栈中取栈顶运算符，从操作数栈的栈顶取 2 个操作数，然后进行计算，再把计算完的结果压入操作数栈，继续比较。

#### 栈在括号匹配中的应用

LeetCode: [20. Valid Parentheses](https://leetcode.com/problems/valid-parentheses/)

我们用栈来保存未匹配的左括号，从左到右依次扫描字符串。当扫描到左括号时，则将其压入栈中；当扫描到右括号时，从栈顶取出一个左括号。如果能够匹配，比如“(”跟“)”匹配，“[”跟“]”匹配，“{”跟“}”匹配，则继续扫描剩下的字符串。如果扫描的过程中，遇到不能配对的右括号，或者栈中没有数据，则说明为非法格式。

### 队列：队列在线程池等有限资源池中的应用

线程池没有空闲线程时，新的任务请求线程资源时，线程池该如何处理？各种处理策略又是如何实现的呢？

我们一般有两种处理策略。第一种是非阻塞的处理方式，直接拒绝任务请求；

另一种是阻塞的处理方式，将请求排队，等到有空闲线程时，取出排队的请求继续处理。那如何存储排队的请求呢？

基于链表的实现方式，可以实现一个支持无限排队的无界队列（unbounded queue）

而基于数组实现的有界队列（bounded queue），队列的大小有限

实际上，对于大部分资源有限的场景，当没有空闲资源时，基本上都可以通过“队列”这种数据结构来实现请求排队。

#### 如何理解“队列”？

队列这个概念非常好理解。你可以把它想象成排队买票，先来的先买，后来的人只能站末尾，不允许插队。先进者先出，这就是典型的“队列”。

入队 enqueue()，放一个数据到队列尾部；出队 dequeue()，从队列头部取一个元素。

#### 顺序队列和链式队列

用数组实现的队列叫作顺序队列，用链表实现的队列叫作链式队列。

#### 循环队列

循环队列，顾名思义，它长得像一个环。原本数组是有头有尾的，是一条直线。现在我们把首尾相连，扳成了一个环。

循环队列会浪费一个数组的存储空间。

#### 阻塞队列和并发队列

阻塞队列其实就是在队列基础上增加了阻塞操作。简单来说，就是在队列为空的时候，从队头取数据会被阻塞。因为此时还没有数据可取，直到队列中有了数据才能返回；如果队列已经满了，那么插入数据的操作就会被阻塞，直到队列中有空闲位置后再插入数据，然后再返回。

线程安全的队列我们叫作并发队列。

### 递归：如何用三行代码找到“最终推荐人”？

#### 如何理解“递归”？

去的过程叫“递”，回来的过程叫“归”。

#### 递归需要满足的三个条件

1. 一个问题的解可以分解为几个子问题的解
2. 这个问题与分解之后的子问题，除了数据规模不同，求解思路完全一样
3. 存在递归终止条件

#### 如何编写递归代码？

写递归代码的关键就是找到如何将大问题分解为小问题的规律，并且基于此写出递推公式，然后再推敲终止条件，最后将递推公式和终止条件翻译成代码。

编写递归代码的关键是，只要遇到递归，我们就把它抽象成一个递推公式，不用想一层层的调用关系，不要试图用人脑去分解递归的每个步骤。

#### 递归代码要警惕堆栈溢出

我们可以通过在代码中限制递归调用的最大深度的方式来解决这个问题。递归调用超过一定深度（比如 1000）之后，我们就不继续往下再递归了，直接返回报错。

但这种做法并不能完全解决问题，因为最大允许的递归深度跟当前线程剩余的栈空间大小有关，事先无法计算。如果实时计算，代码过于复杂，就会影响代码的可读性。所以，如果最大深度比较小，比如 10、50，就可以用这种方法，否则这种方法并不是很实用。

#### 递归代码要警惕重复计算

为了避免重复计算，我们可以通过一个数据结构（比如散列表）来保存已经求解过的 f(k)。当递归调用到 f(k) 时，先看下是否已经求解过了。如果是，则直接从散列表中取值返回，不需要重复计算。

#### 怎么将递归代码改写为非递归代码？

我们刚说了，递归有利有弊，利是递归代码的表达力很强，写起来非常简洁；而弊就是空间复杂度高、有堆栈溢出的风险、存在重复计算、过多的函数调用会耗时较多等问题。

