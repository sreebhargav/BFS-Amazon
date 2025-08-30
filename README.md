# AmazonDelivery.java – Multi-Source BFS Shortest Path

## 📌 Problem Description
We are given a 2D grid of characters where:
- `A` → delivery stations (starting points)
- `O` → open cells that can be moved through
- `C` (or any other character) → blocked or invalid cells

You are also given a list of query coordinates.  
For each query, return the **shortest distance from the nearest `A`** to that location, moving only in 4 directions:
- Up
- Down
- Left
- Right  

Only `O` cells can be traversed.

---

## 🔎 Solution Overview
The problem is solved using **Multi-Source BFS**:
1. Enqueue all `A` cells with distance `0`.
2. Perform BFS to explore all reachable `O` cells step by step.
3. Maintain a distance matrix to store the shortest distance for each cell.
4. For each query, simply look up its distance from the matrix.

This ensures that the first time we reach a cell, it’s through the shortest possible path.

---

## ⏱️ Complexity
- **Time Complexity:** `O(m × n)` → each cell is processed once.  
- **Space Complexity:** `O(m × n)` → distance matrix + BFS queue.  

---

## 💻 Sample Run
```java
char[][] map = { 
  {'A', 'O', 'C'}, 
  {'O', 'O', 'O'}, 
  {'C', 'O', 'O'} 
};

int[][] queries = {{1, 2}, {2, 1}};

// Output:
[3, 2] 
// → Shortest distances from the nearest 'A' to each query cell

