# 第八章-排序

> 习题来自张铭第八章-内排序

:warning: _注：缺少的题号表示习题重复_

## 8.1 教材习题

### 8.1.1 试构造 $5$ 个整数元素进行排序且最多只用 $7$ 次比较的算法思想

### 8.1.2 写一个处理整数排序吗的插入排序算法。算法要满足以下条件：输入数据存放于栈中（不是存放于数组中），并且程序中只许用一定的整数及栈。算法结束时排序结果放在栈中，栈顶元素最小。最差情况下，算法的执行时间为$O(n^2)$

### 8.1.3 试给出采用增量序列$\{2^k-1, 2^{k-1}-1,...,7,3,1\}$的 Shell 排序的时间代价为$Θ(n^{3/2})$的推理过程

### 8.1.4 采用增量序列$\{2^k-1, 2^{k-1}-1,...,7,3,1\}$对$[45, 34, 78, 12, 34, 32, 29, 64]$进行排序，试写排序各阶段时的数组状态，与原来的排序过程进行比较

### 8.1.5 直接选择排序的最小交换次数为$Θ(n)$，因为算法并不检查第 $i$ 个元素是否已经在第 $i$ 个位置，即有可能带来不必要的交换

**（1）改进算法使之没有不必要的交换**  
**（2）这种改进能加快速度吗，试说明理由**  
**（3）编程验证一下原始排序算法和改进算法的运行时间，哪个算法实际上更快**

### 8.1.6 考虑这样一种计数排序：对每个待排记录，扫描整个序列统计比它小的记录个数 $c$，则 $c$ 就是他在序列中的正确位置。值得注意的是，计数排序只适用于不存在重复记录的情况。编程实现这种算法，并分析其时间代价，与直接选择排序进行比较

### 8.1.7 在堆排序中采用的堆是基于二叉树的，因此时间代价为$Θ(nlogn)$。如果采用基于三叉树的堆来实现堆排序，时间代价是否会编程$Θ(nlog_3n)$？试编写一个基于三叉树的堆排序算法，并分析时间代价

### 8.1.8 冒泡排序相关

**冒泡排序中有如下循环：**  
`for(int j = n-1; j >= i; j--)`  
**考虑将其换成以下语句的影响：**  
`for(int j = n-1; j > 0; j--)`  
**新的算法是否还能正常执行，这种改变是否会影响到程序的近似复杂性，此改变对时间代价有和影响？**

### 8.1.9 冒泡排序的一个变种就是所谓的鸡尾酒混合排序：与本章中介绍的冒泡排序一样，它对数组总共也要进行 $n-1$ 趟排序。但是相邻两趟的冒泡是相反的，例如，第一趟排序将最大记录值跑到数组的底部，而在第二趟排序中将最小的记录冒泡到数组的顶部。试编程实现该算法

### 8.1.10 在冒泡排序过程中，什么情况下排序码会朝向与排序相反的反向移动，试举例说明。在快速排序过程中有这种现象吗

**提示：排序相反的方向是某个元素从它现在的位置向其最终的位置移动的方向。例如，该元素原来在位置 $3$，最终排序位置是 $5$，那么如果它移动到位置 $4$，则与排序方向同向移动；如果它移动到位置 $2$，则与排序方向反向移动。如果移动到位置 $7$，这次移动还算同向移动，但下次该排序方向就是从 $7$ 向位置 $5$ 的移动。**

### 8.1.11 通常，快速排序是将数组划分成两部分，当数组中有大量重复记录时，试将快速排序改成三分数组（将数组划分成大于，等于和小于轴值三部分），并将讨论算法对包含 $d$ 个不同值的长度为 $N$ 的数组的效率

### 8.1.12 本章中算法 8.6 中给出的快速排序是通过递归来实现的

**（1）试用栈来代替递归，减少函数调用次数，优化该算法。**  
**（2）在最差情况下栈有多深？**  
**（3）怎样组织递归调用的顺序可以让栈的深度减到最小，可以减为多少？**  
**（4）可以用队列，而不用栈来消除快速排序中的递归吗？**

### 8.1.13 一个非零数列中有些为正数，有些为负数。试编写一个算法，重新排列这些非零实数，使得负数排在前面，正数排在后面

**提示：参考快速排序的分割算法。**

### 8.1.14 设有一个仅由红、白、蓝 $3$ 种颜色的条块（每个色块除了颜色外，其他性质相同）组成的序列，各个色块的个数是随机的，但 $3$ 种颜色色块的总数为 $n$。试编写一个时间复杂度为$Θ(n)$的算法，使用辅助空间最少的算法，使得这些条块按照红、白、蓝的顺序排号，即排成荷兰国旗图案（整个图案由三大色块组成，第一块是红色，第二块是白色，第三块是蓝色）。试分析你的算法的时间和空间代价

### 8.1.15 定义“中位数”长度为 $n$ 的序列的第$⌈(n+1)/2⌉$个（取上整）或第$⌊(n+1)/2⌋$个（取下整）（若对该序列排序，就是排在$⌈(n+1)/2⌉$或低$⌊(n+1)/2⌋$位置的值。注意，当 $n$ 是偶数时中位数有两个）。试设计一个$Θ(n)$的算法求给定序列的中位数

### 8.1.16 设 $A、B$ 是长为 $n$ 的数表，已经按照非降顺序排好。如果将这 2n 个数全体排序，则处于第 n 个位置的数称为中位数。设计一个最坏情况下$O(logn)$时间的算法求 A 和 B 的中位数

**（1）描述算法的设计思想**  
**（2）证明算法的时间复杂性**

### 8.1.17 为了由 n 个元素构成的未排序序列$S={s_1,s_2,...,s_n}$种选择出第 k 个最大的元素，考虑以下算法

**（a）如果$n≤5$，对$S$排序且直接选出第$k$个最大元素**  
**（b）否则$n>5$：把序列$S$分割成长度为 5 的子序列。一般而言，将有⌊n/5⌋个长度为 5 的子序列，一个长度为(n%5)的子序列**  
**（c）对长度为 5 的子序列用任意一种方法进行排序**  
**（d）对子序列排序后从每个子序列中选取一个中位数，形成一个含⌊n/5⌋个中位数序列$M={m_1,m_2,...,m_{n/5}}$**  
**（e）递归重复这一选择过程，找出序列 M 种的中位数，设 m 是序列 M 的中位数**  
**（f）将序列 S 分割成 3 个子序列{L,E,C}，使得序列 L 的元素都比 m 小，E 中的元素都等于 m，G 种的元素都比 m 大**  
**（g）如果 k≤|L|，递归重复这个过程选择 L 种的第 k 个最大元素；如果|L|＜ k≤|L|+|E|，结果就是 m；否则选择 G 种的第(k-(|L|+|E|))个最大元素**

**（1）此算法的运行时间是多少？**  
**（2）如果用这个算法选择轴值，试证明快速排序的最差运行时间是 Θ(nlogn)**

### 8.1.18 本章中介绍的是两路归并算法，如果是 4 路或者 8 路归并，应该如何改写？试分析改写后的算法代价，并与原来的算法进行比较

### 8.1.19 有人说：“由于归并排序的时间代价是 Θ(nlogn)，插入排序的时间代价为 Θ(n2)，因此当对 256 个数字进行排序是，归并排序的速度将是插入排序的 64 倍!”试问这种说法是否正确？并说明理由

### 8.1.20 本章中算法 8.8 中给出的归并排序是通过递归来实现的

**（1）试用栈来代替递归，编写一个非递归的归并排序算法**  
**（2）不用栈、也不用队列，编写一个非递归的归并排序算法**

### 8.1.21 本章中介绍的归并函数中，需要用到一个长度为 n 的辅助数组来保存合并后的记录。试对该函数进行改进，在不增加算法的时间代价前提下尽量减小空间代价

### 8.1.22 编写一种对扑克牌进行排序的基数排序。花色为高位排序码，面值为低位排序码，大小顺序为：方块 < 梅花 < 红桃 < 黑桃，2 < 3 < 4 < 5 < 6 < 7 < 8 < 9 < 10 < J < K < A

### 8.1.23 本章介绍了很多种排序算法，分别列出哪些算法具有以下特性

**（1）不需要访问那些已经排好序的记录**  
**（2）在整个排序过程中，算法每次都要访问序列中的所有记录**

### 8.1.24 下面的各种操作中，哪一个最适于先进行排序处理？对于这些操作，分别简短的描述一个实现算法，并给出算法的渐进复杂性

**（1）找最小值**  
**（2）找最大值**  
**（3）计算算术平均值**  
**（4）找中位数**  
**（5）找出现次数最多的值**

### 8.1.25 在下列情况下，你会选择哪种排序算法？并说明理由

**（1）需要对 1000 个数字进行排序，程序只需运行一次**  
**（2）只需要对 50 个数字进行排序，程序只需要运行一次**  
**（3）在编写一个很庞大的程序中需要编写一个对 5 个记录进行排序的函数，而且改函数将被反复调用很多次**  
**（4）需要对 1000 个大型记录进行排序，记录本身存在外存中，在内存中只保存了多有记录的排序码。排序码之间的比较非常快，但移动代价很大，因为一旦移动一个排序码，相应的外存中的记录也要移动，将设计上百个磁盘块的移动**  
**（5）在图书馆里计算机类的书籍区一共有 12 列书架，书架上的书本来都是按照编目号排列好的，但其中有些书被读者放错了地方，但通常不会偏离超过一个书架。试设计一个算法将这些书重新放回正确的位置**  
**（6）需要将 500 张随机排列的图书卡按照字母顺序排好序**  
**（7）已知一个包含了 5000 个单词的列表已按字母顺序排序好，需要再进行一次检查，确保所有单词已经排好序**

### 8.1.26 某整数型数组 A 的十个元素值依次为{6,2,9,7,3,8,4,5,0,1}用下列各种排序方法，将 A 中的元素由小到大排序

**（1）取第一个元素值 6 作为分割数，试写出快速排序第一次分隔后 A 中的结果**  
**（2）用堆排序，试写出将第一个选出的数据放在 A 的最后位置上，将 A 调整成堆后的 A 中结果**  
**（3）用基数为 3 的基数排序法，试写出第一次分配和收集后 A 中的结果**

### 8.1.27 已知一组元素的排序码为(46,74,16,53,14,26,40,53',86,65,27,34)

**（1）利用直接插入排序的方法写出每次向前面有序表插入一个元素后的排列结果**  
**（2）利用直接选择排序方法写出每次选择和交换后的排列结果**  
**（3）利用最大堆排序方法写出在构成初始堆和利用堆排序的过程中，每次过筛(sift-Down)运算后的排列结果，并画出初始堆所对应的完全二叉树**  
**（4）采用快速排序，每次都取子序列的最左元素为轴值，写出每一层划分后的排列结果，并画出由此快速排序得到如图 8.6 所示的二叉搜索树**  
**（5）利用归并排序的方法写出每一趟二路归并排序后的结果**

<div align="center"><img src="./images/7-1-27.png" alt="7-1-27" height=240, width= /></div>

### 8.1.28 如果只想在一个有 n 个元素的任意序列中得到其中的最小的第 k(k<<n)个元素之前的部分排序序列，而且这个 n 是比较小的值。采用什么排序方法能得到比用堆排序比较次数更少？例如，有这样一个序列{503,017,512,908,170,897,275,653,612,154,509,612',677,765,094}，要得到其第 4 个元素之前的部分有序序列{017,094,154,170}，用所选择的排序算法（非堆排序）实现时，要执行多次比较？若用堆排序算法，要执行多少次比较？

### 8.1.29 设$S_1,S2,...,S_k$是$k$个集合，每个集合均由$n$个实数组成。试设计一个算法将所有的和$x_1+x_2+...+x_k$(其中，$x_i∈S_i,i=1,2,...,k$)从小到大排序，并分析算法时间代价

### 8.1.30 设$k$为给定常数，$A_1=<x_1,x_2,...,x_k>,A_2=<y_1,y2,...,y_k>$是$k$维整数序列，如果存在$x_1,x_2,...,x_k$的排列$x'_1,x'_2,...,x'_k$满足$x'_1<y_1,x'_2<y_2,...,x'_k<y_k$，则称$A_1$嵌入$A_2$，记作$A_1<A_2$。现有$n$个$k$维序列$A_1,A_2,...,A_k$构成集合$B$

**（1）说明$B$上的嵌入关系有哪些性质。**  
**（2）设计一个算法求使得$j$最大的$A_{i1},A_{i2},...,A_{ij}$，并且$A_{i1}<A_{i2}<...<A_{ij}$**  
**（3）说明算法的正确性并分析算法在最坏情况下的复杂性**

### 8.1.31 像静态链基数排序那样，数组元素增加一个 next 域逻辑链表，对这个静态链表实现插入排序（只修改 next 静态指针，不移动元素），则称为“表插入排序”

**（1）实现这个表插入排序算法，算法执行后，这个长度为 n 的数组由其内部的静态链链指针 next（数组内部加入一个下标域）而串成一个已排序序列（不减的顺序）**  
**（2）设计一个只使用一个辅助结点的算法，在 Θ(n)时间内，把这个由静态 next 串成的有序数组，整理成为从数组 0~n~1 位置存放的不减的序列**

<table align="center">
  <thread>
    <th align="center">index</th>
    <th align="center"></th>
    <th align="center">1</th>
    <th align="center">2</th>
    <th align="center">3</th>
    <th align="center">4</th>
    <th align="center">5</th>
    <th align="center">6</th>
    <th align="center">7</th>
    <th align="center">8</th>
  </thread>
  <tbody>
    <th align="center">key</th>
    <th align="center"></th>
    <th align="center">49</th>
    <th align="center">38</th>
    <th align="center">65</th>
    <th align="center">97</th>
    <th align="center">76</th>
    <th align="center">13</th>
    <th align="center">27</th>
    <th align="center">52</th>
  </tbody>
  <tbody>
    <th align="center">next</th>
    <th align="center">6</th>
    <th align="center">8</th>
    <th align="center">1</th>
    <th align="center">5</th>
    <th align="center">0</th>
    <th align="center">7</th>
    <th align="center">4</th>
    <th align="center">3</th>
    <th align="center">2</th>
  </tbody>
</table>

### 8.1.32 考虑把由 3 个不同记录组成的序列{A,B,C}，试分别画出表示下列排序算法的二叉判定树：直接插入排序、直接选择排序、冒泡排序

### 8.1.33 设计一个算法，将数组$A(0...n-1)$中的元素循环右移$k$位，假设原数组序列位$a_0,a_1,...,a_{n-2},a_{n-1}$；移动后的序列为$a_{n-k},a_{n-k+1},...,a_0,a_1,...,a_{n-k-1}$。要求只用一个元素大小的附加存储，元素移动或交换次数为$O(n)$

## 8.2 上机题

### 8.2.1 编程实现下述算法，并于教材上的算法进行效率比较，然后用理论分析支持你的试验结论

**（1）教材中是用插入算法线性搜索来寻找正确位置的。在插入第 i 个记录时，前面的记录已经有序，因此可以考虑用二分查找第 i 个记录的正确位置。这种算法称为二分法插入排序(binary insert sorting)**  
**（2）交换式插入排序(swap insert sorting)改写教材中每次插入时的操作，当插入第 i 个记录时，如果该记录比它前面的那个记录小，则交换该记录与其前面的那个记录，即该记录向前移动一个位置，然后继续向前比较，直到遇到一个小于或等于它的记录，本次插入才完成**

### 8.2.2 奇偶交换排序是另一种交换排序。它的第一趟对序列中的所有奇数项 i 进行扫描，第二趟对序列中的所有偶数项 i 进行扫描。若 A[i]>A[i+1]，则交换它们。第三趟对所有的奇数项，第四趟对所有的偶数项，...，如此反复，直到整个序列全部排好序为止

**（1）这种排序方法的结束条件是什么？**  
**（2）写出奇偶交换排序的算法，并实验测试其时间代价**  
**（3）当待排序排序码序列的初始排序是从小到大有序，或从大到小有序时，在奇偶交换排序过程中的排序码比较次数是多少？分析奇偶交换排序的平均时间复杂度**

### 8.2.3 改写算法 8.8 中的快速排序算法，采用一种不同的轴值选择方法：选择序列中的所有记录的平均值作为轴值。试设计并实现一个 MeanPivotQuickSort 类，使其能把要排列的序列分割成比平均值大和比平均值小的的元素

**注意：需要修改原来的分割函数，因为现在轴值可能不是序列中的元素。试编程比较两种算法的实际运行时间。**  

### 8.2.4 试写一组英文单词按字典顺序排序的基数排序算法，单词区分大小，设最大的单词有 n 个字母

### 8.2.5 本章中介绍的排序算法大都是基于数组实现的，试采用链式存储来改写本章的排序算法，并试验比较算法的数组实现和链式实现效率。此时，可以发现大部分算法都能用链表来实现，但有些特殊算法不适于链式存储，试分析为什么这些算法不适合链式存储

## 8.3 教材习题解答

### 8.3.1 一个长度为n的有序序列加入了k个新元素(k<<n)。请编写算法对这个序列排序，并分析此算法的时间代价和空间代价

### 8.3.2 请用图示说明用直接插入排序和二分法插入排序分别对下面的序列进行排序的过程({26,33,35,29,18,57,266})，包括每次的比较和交换次数，并指出不同

### 8.3.3 [教材习题 8.1.5](#715-直接选择排序的最小交换次数为θn因为算法并不检查第-i-个元素是否已经在第-i-个位置即有可能带来不必要的交换)

### 8.3.4 [教材习题 8.1.2](#712-写一个处理整数排序吗的插入排序算法算法要满足以下条件输入数据存放于栈中不是存放于数组中并且程序中只许用一定的整数及栈算法结束时排序结果放在栈中栈顶元素最小最差情况下算法的执行时间为on2)

### 8.3.5~8.1.7 [教材习题 8.1.8](#718-冒泡排序相关) ~ [教材习题 8.1.10](#7110-在冒泡排序过程中什么情况下排序码会朝向与排序相反的反向移动试举例说明在快速排序过程中有这种现象吗)

### 8.3.8 [教材习题 8.1.6](#716-考虑这样一种计数排序对每个待排记录扫描整个序列统计比它小的记录个数-c则-c-就是他在序列中的正确位置值得注意的是计数排序只适用于不存在重复记录的情况编程实现这种算法并分析其时间代价与直接选择排序进行比较)

### 8.3.9 [教材习题 8.1.32](#7132-考虑把由-3-个不同记录组成的序列abc试分别画出表示下列排序算法的二叉判定树直接插入排序直接选择排序冒泡排序)

### 8.3.10 教材中介绍的几种排序算法是通过不断交换记录来减小序列中的逆置树，从而实现排序。那么交换序列中两个不同的记录，最多能减少多少个逆置

### 8.3.11 如果采用动态链表来实现Shell排序，会出现什么问题？为什么会这样

### 8.3.12 [教材习题 8.1.12](#7112-本章中算法-86-中给出的快速排序是通过递归来实现的)

### 8.3.13 如果一个整数序列中的数一半是奇数，一半是偶数，编写一个算法，重新排列这些整数，使得所有奇数位于奇数下标上，所有偶数位于偶数下标上

**提示：参考快速排序的分割算法。**

### 8.3.14 [教材习题 8.1.13](#7113-一个非零数列中有些为正数有些为负数试编写一个算法重新排列这些非零实数使得负数排在前面正数排在后面)

### 8.3.15 [教材习题 8.1.14](#7114-设有一个仅由红白蓝-3-种颜色的条块每个色块除了颜色外其他性质相同组成的序列各个色块的个数是随机的但-3-种颜色色块的总数为-n试编写一个时间复杂度为θn的算法使用辅助空间最少的算法使得这些条块按照红白蓝的顺序排号即排成荷兰国旗图案整个图案由三大色块组成第一块是红色第二块是白色第三块是蓝色试分析你的算法的时间和空间代价)

### 8.3.16 ~ 8.1.19[教材习题 8.1.18](#7118-本章中介绍的是两路归并算法如果是-4-路或者-8-路归并应该如何改写试分析改写后的算法代价并与原来的算法进行比较) ~ [教材习题 8.1.21](#7121-本章中介绍的归并函数中需要用到一个长度为-n-的辅助数组来保存合并后的记录试对该函数进行改进在不增加算法的时间代价前提下尽量减小空间代价)

### 8.3.20 [教材习题](#717-在堆排序中采用的堆是基于二叉树的因此时间代价为θnlogn如果采用基于三叉树的堆来实现堆排序时间代价是否会编程θnlog_3n试编写一个基于三叉树的堆排序算法并分析时间代价)

### 8.3.21 比较时间代价均为Θ(nlogn)的快速排序和堆排序，说明它， 分别适用于什么情况

### 8.3.22 [教材习题 8.1.22](#7122-编写一种对扑克牌进行排序的基数排序花色为高位排序码面值为低位排序码大小顺序为方块--梅花--红桃--黑桃2--3--4--5--6--7--8--9--10--j--k--a)

### 8.3.23 [教材习题 8.1.23](#7123-本章介绍了很多种排序算法分别列出哪些算法具有以下特性)

### 8.3.24 [上机题 8.2.5](#725-本章中介绍的排序算法大都是基于数组实现的试采用链式存储来改写本章的排序算法并试验比较算法的数组实现和链式实现效率此时可以发现大部分算法都能用链表来实现但有些特殊算法不适于链式存储试分析为什么这些算法不适合链式存储)]

### 8.3.25 [教材习题 8.1.25](#7125-在下列情况下你会选择哪种排序算法并说明理由)

### 8.3.26 举例说明在哪些情况下简单排序算法反而比那些代价小但复杂度更高的算法更适用

### 8.3.27 教材中的实验证明虽然二分法插入排序的时间代价和直接插入排序是同量级的，但是当数据规模较大时实际运行时间比直接插入排序的确要快一些。原因是二分法减少了比较次数，第i次排序时只需要logi次比较，请推理出二分法插入排序需要的总比较次数。(这道题目目的是通过具体的推理过程可以看出二分法插入排序在数据规模较大时的优势)

### 8.3.28 [教材习题 8.1.3](#713-试给出采用增量序列2k-1-2k-1-1731的-shell-排序的时间代价为θn32的推理过程)

### 8.3.29 [教材习题 8.1.4](#714-采用增量序列2k-1-2k-1-1731重新对图-85-中的例子进行排序试写排序各阶段时的数组状态与原来的排序过程进行比较)

### 8.3.30 [上机题 8.2.2](#722-奇偶交换排序是另一种交换排序它的第一趟对序列中的所有奇数项-i-进行扫描第二趟对序列中的所有偶数项-i-进行扫描若-aiai1则交换它们第三趟对所有的奇数项第四趟对所有的偶数项如此反复直到整个序列全部排好序为止)

### 8.3.31 设有n个待排元素存放在一个不带表头结点的单链表中，每个链表结点只存放一个元素，头指针为r0。试设计一个算法，对其进行2路归并排序，要求不移动节点中的元素，只修改各链结点中的指针，排序后r仍指示结果链表的第一个结点

**提示：先对待排序的单链表进行一次扫描，将它划分成若干有序的子链表，其表头指针存放在一个指针队列中。当队列不空时重复执行，从队列中推出两个有序子链表，对它们进行2路归并，结果链表的表头指针存放到队列中。如果队列中退出一个有序子链表后变成空链表，则算法结束。**

### 8.3.32 [教材习题 8.1.28](#7128-如果只想在一个有-n-个元素的任意序列中得到其中的最小的第-kkn个元素之前的部分排序序列而且这个-n-是比较小的值采用什么排序方法能得到比用堆排序比较次数更少例如有这样一个序列503017512908170897275653612154509612677765094要得到其第-4-个元素之前的部分有序序列017094154170用所选择的排序算法非堆排序实现时要执行多次比较若用堆排序算法要执行多少次比较)

### 8.3.33 [教材习题 8.1.29](#7129-设s_1s2s_k是k个集合每个集合均由n个实数组成试设计一个算法将所有的和x_1x_2x_k其中x_is_ii12k从小到大排序并分析算法时间代价)

### 8.3.34 [教材习题 8.1.15](#7115-定义中位数长度为-n-的序列的第n12个取上整或第n12个取下整若对该序列排序就是排在n12或低n12位置的值注意当-n-是偶数时中位数有两个试设计一个θn的算法求给定序列的中位数)

### 8.3.35 [教材习题 8.1.24](#7124-下面的各种操作中哪一个最适于先进行排序处理对于这些操作分别简短的描述一个实现算法并给出算法的渐进复杂性)

### 8.3.36 如果希望在排序过程中始终不移动记录，则可以在待排数组的元素中增加一个静态指针域，并且数组的第一个元素为头指针位

### 8.3.37 [教材习题 8.1.17](#7117-为了由-n-个元素构成的未排序序列ss_1s_2s_n种选择出第-k-个最大的元素考虑以下算法)

## 8.4 教材上机题解答

### 8.4.1 [上机题 8.2.2](#722-奇偶交换排序是另一种交换排序它的第一趟对序列中的所有奇数项-i-进行扫描第二趟对序列中的所有偶数项-i-进行扫描若-aiai1则交换它们第三趟对所有的奇数项第四趟对所有的偶数项如此反复直到整个序列全部排好序为止)

### 8.4.2 [教材习题 8.1.4](#714-采用增量序列2k-1-2k-1-1731重新对图-85-中的例子进行排序试写排序各阶段时的数组状态与原来的排序过程进行比较)

### 8.4.3 [上机题 8.2.3](#723-改写算法-88-中的快速排序算法采用一种不同的轴值选择方法选择序列中的所有记录的平均值作为轴值试设计并实现一个-meanpivotquicksort-类使其能把要排列的序列分割成比平均值大和比平均值小的的元素)

### 8.4.4 请用链式存储来改写教材中介绍的归并排序，并于原来的算法进行比较(事实上会发现，归并排序更适合于链式存储)
