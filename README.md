# lintcode Ladder answer
  This is a file to record my code solution
  
  ## Some references:
  - BFS:
  https://zhuanlan.zhihu.com/p/136183284
  
  - 什么是快速幂？
  https://blog.csdn.net/qq_19782019/article/details/85621386
  
   - 什么是拓扑排序？
   https://www.cxyxiaowu.com/1084.html
   
   -入度与出度
在介绍算法之前，我们先介绍图论中的一个基本概念，入度和出度，英文为 in-degree & out-degree。
在有向图中，如果存在一条有向边 A-->B，那么我们认为这条边为 A 增加了一个出度，为 B 增加了一个入度。

算法流程
拓扑排序的算法是典型的宽度优先搜索算法，其大致流程如下：

统计所有点的入度，并初始化拓扑序列为空。
将所有入度为 0 的点，也就是那些没有任何依赖的点，放到宽度优先搜索的队列中.
将队列中的点一个一个的释放出来，放到拓扑序列中，每次释放出某个点 A 的时候，就访问 A 的相邻点（所有A指向的点），并把这些点的入度减去 1。
如果发现某个点的入度被减去 1 之后变成了 0，则放入队列中。
直到队列为空时，算法结束.
深度优先搜索的拓扑排序
深度优先搜索也可以做拓扑排序，不过因为不容易理解，也并不推荐作为拓扑排序的主流算法。

笔记：拓扑排序的大体思想为：
首先将入度为0的结点放入queue中，在一个一个向外pop的过程中，
每pop一个则将此节点放入访问顺序中，同时对于每个pop出的结点，
将他们指向的结点的入度全都减1，若此时又存在新的入度为0的结
点，则将此结点放入queue中

while queue不空：
pop结点
加入order
for 此结点所有出度结点：
每个结点入度减一
判断此结点是否入度为0，若为零加入queue

注意，这里为图的bfs，故没有层级遍历，故只有一个大循环while

对于如何寻找入度，方法为设置一个字典，key为结点，value为入度，
循环所有结点，每次将他们出度的结点的value加一即可
  
  ## Templates:
  
  [bfs basic template](Documentation/bfs.txt)
  
