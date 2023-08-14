# 一篇故事秒懂 Floyd-Warshall 最短路算法

![rw-book-cover](https://pic1.zhimg.com/v2-2117ab86c9610a1237ac05f77f5b123b_720w.jpg?source=172ae18b)

## Metadata
- Author: [[知乎专栏]]
- Full Title: 一篇故事秒懂 Floyd-Warshall 最短路算法
- Category: #articles
- URL: https://zhuanlan.zhihu.com/p/623757829

## Highlights
- // 设 f 是一个三维数组，每一维的下标范围从 0 到 n
  // f 的初值如下：
  // * f[0][i][i] = 0
  // * 若原图中有一条从节点 i 到节点 j，长度为 v 的有向边，则 f[0][i][j] = v
  // * f[0][*][*] 的其它位置初值为无穷大
  for (int k = 1; k <= n; k++) {
  for (int i = 1; i <= n; i++) {
  for (int j = 1; j <= n; j++) {
  f[k][i][j] = min(f[k - 1][i][j], f[k - 1][i][k] + f[k - 1][k][j]);
  }
  }
  }
  // 此时，f[n][i][j] 就是从节点 i 到节点 j 的最短路长度
  代码非常简短，仅由三层 for 循环构成。
  由于每层循环的范围是从 111 到 nnn，因此这段代码的时间复杂度为 O(n3)\mathcal{O}(n^3)\mathcal{O}(n^3)。而由于 `f` 是一个三维数组，每一维的下标范围从 000 到 nnn，因此这段代码的空间复杂度也为 O(n3)\mathcal{O}(n^3)\mathcal{O}(n^3)。 ([View Highlight](https://read.readwise.io/read/01gz8avxh16yzw8dr26frc6ttj))
