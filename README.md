# Diagonal Matrix Sort (Python Optimization)

## 📌 Problem Overview
This repository contains an efficient solution for sorting matrix diagonals in ascending order. A matrix diagonal is a diagonal line of cells starting from any cell in the first row or column and proceeding in the top-left to bottom-right direction.

## 🧮 Algorithmic Approach
The solution leverages a brilliant mathematical property of matrix diagonals: **for any cell `mat[i][j]`, the value of `i - j` remains constant along the same diagonal.**

1. **Grouping:** We use a `defaultdict(list)` to group all elements sharing the same `i - j` key.
2. **Sorting:** Each diagonal list is sorted in reverse order (`reverse=True`). This allows us to efficiently use `pop()` (O(1) time complexity) to retrieve the smallest elements first.
3. **Reconstruction:** We iterate through the matrix again and overwrite the original cells with the sorted values.

## 🚀 Complexity Analysis
* **Time Complexity:** $O(N \times M \log(\min(N, M)))$ where $N$ is the number of rows and $M$ is the number of columns, due to sorting each diagonal.
* **Space Complexity:** $O(N \times M)$ to store the matrix elements inside the hash map.

## 🛠️ How to Use
Simply import the `Solution` class and pass a 2D list:
```python
sol = Solution()
matrix = [[3,3,1,1],[2,2,1,2],[1,1,1,2]]
print(sol.diagonalSort(matrix))
