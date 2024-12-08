# P, NP,NP-hard and NP-C
- **ploynomial time algorithms(P)**:
  - can be solved in polynomial time.
  - worst-case running time is $O(n^k)$
- **Non-Deterministic Polynomial(NP)**
  - can be verified in polynomial time. 
  - can be solved in (deterministically) exponential time.
- **NP-hard**
  - it is at least as hard as all NP problems
  - if it can be solve in polynomial time, then all NP problems can be solved in polynomial time
- **NP-Complete**
  - it is NP-hard and
  - it is in NP
  - can reduct to any other NP problems in polynomial time
## 课上讲的一些NP-Complete 问题证明过程/思路
关键在于问题转换
- **circuit-SAT**
  最基本的NPC问题，作为base case
- **SAT**
  reduction： circuit-SAT $\leq _p$ SAT
  
- **3-CNF-SAT**
  reduction：SAT $\leq _p$ 3-CNF-SAT
- **Clique Problem**
  reduction：3-CNF-SAT $\leq _p$ Clique

- **Vertex Cover Problem(路灯问题)**
  reduction：Clique $\leq _p$ Vertex Cover
  There is an independent set of size k in graph G $\iff$ there is a clique of size k in its complement graph G’

- **maximum independent set**
  reduction：Clique Problem $\leq _p$ independent set
  A graph $G$ has a clique of size $k$ $\iff$ $G_c$ has a vertex cover of size $|V| - k$,一定要双向证明
  设clique里的点的集合为 $V^{'}$, $|V^{'}|=k$
  取原图 $G$ 的补图 $G_C$ , 新添加的边 $\{u,v\}$ 一定有一个点不属于 $V^{'}$, 所以 $u \space or\space  v $ 一定有一个属于集合 $V -V^{'}$ ,那么 $V -V^{'}$ 就构成了 补图 $G_C$ 的vertex cover(因为补图所有边已经在上一步证明了一定包含 $V -V^{'}$)

  反过来，...

  - **traveling salesman problem**(visit each city exactly once)