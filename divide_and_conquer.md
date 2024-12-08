# divide and conquer
- **merge sort**
- **closest pair of points(二维空间上点的最近距离)**
  1. 按照点的x坐标升序divide所有坐标，分为左右两部分
  2. 算左边、右边最近距离
  3. 用 $\delta = min(l_{min},r_{min})$ 去限制分割线附近的点，计算这些点的距离，取最小
  4. 不仅可以用x限制，还可以用y限制，减少计算。 因为在$\delta \cdot 2\delta$ 区域内最多存在8个点，我们就每次选8个点进行计算，按照y升序.
    e.g. $(y_0,y_1,y_2,\dots,y_8)$ $(y_1,y_2,y_3,\dots,y_9)$
  5. recursion relation:
    $$ T(n)= 
    \begin{cases} 
    \Theta(1), & \text {if $n \leq 3$} 
    \\\\ 
    2T(\frac{n}{2})+\Theta(nlogn), & \text{if $n > 3$} 
    \end{cases} $$
    time complexity is $O(nlog^2n)$

- **Maximum Subarray Problem**
  可以用分治法，比较左，中，右
  最优是用Kadane 算法