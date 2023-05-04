# Entropy and Rand Roads [v2]

## 熵和随机道路 [v2]

**EN**: You have already finished v1 problem, right? The v1 problem is so easy, so in this v2 problem, I will introduce you the **ENTROPY**. An Entropy is a value defined as:
$$
E = \texttt{Turn} \times \sum_{r = 1}^{a} \sum_{c = 1}^{b} \texttt{Diff\_Sum}(r, c)
$$

- where `Turn` is the count for change direction in your generated matrix:

  ```plain
  1 2
  4 3
  ```

  [(1, 2) -- (2, 3)] makes a turn, and [(2, 3) -- (3, 4)] makes another turn, so the `Turn` in this matrix is 2.

- and the `Diff_Sum` is the absolute value sum of those differences: the $(r, c)$ number and its neighbour numbers, code as:

  ```plain
  u_diff = abs(matrix[r][c] - matrix[r][c + 1])  # up direction, if (r, c) has a neighbour in up direction, else u_diff = 0
  d_diff = abs(matrix[r][c] - matrix[r][c - 1])  # down direction, condition as above
  l_diff = abs(matrix[r][c] - matrix[r - 1][c])  # left
  r_diff = abs(matrix[r][c] - matrix[r + 1][c])  # right
  diff_sum = u_diff + d_diff + l_diff + r_diff
  ```

Your task is to find a full-filled matrix satisfying v1 requirements and has the maximum entropy you can reach.

**CN**: v1 的题很简单，这里向你介绍一种衡量复杂度的概念：**熵**。本题里的熵的定义如下：
$$
\text{熵} = \text{转弯次数} \times \sum_{r = 1}^{a} \sum_{c = 1}^{b} \text{邻差值和}(r, c)
$$

- 其中 *转弯次数* 是指你生成的矩阵中转弯的次数，比如：

  ```plain
  1 2
  4 3
  ```

  [(1, 2) -- (2, 3)] 是一次转弯，[(2, 3) -- (3, 4)] 是又一次转弯，所以这个矩阵的 *转弯次数* 是 2。

- 而 *邻差值和* 是指 $(r, c)$ 这个位置的数和它的上下左右四个邻居的差值的绝对值之和，代码如下：

  ```plain
  u_diff = abs(matrix[r][c] - matrix[r][c + 1])  # 上方，如果 (r, c) 有上方的邻居，没邻居就 u_diff = 0
  d_diff = abs(matrix[r][c] - matrix[r][c - 1])  # 下方，相同上述条件
  l_diff = abs(matrix[r][c] - matrix[r - 1][c])  # 左方
  r_diff = abs(matrix[r][c] - matrix[r + 1][c])  # 右方
  diff_sum = u_diff + d_diff + l_diff + r_diff
  ```

你的任务是找到一个满足 v1 题目条件的矩阵，使得它的熵最大（尽你所能）。

### Example

No example, enjoy your coding.