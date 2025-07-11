AmazonDelivery.java – BFS Shortest Path

Problem Description

Given a 2D grid of characters where

'A' represents starting positions (like delivery stations)

'O' represents open cells that can be moved through

'C' or other values represent blocked or invalid cells

You are given a list of query coordinates. For each query, return the shortest distance from any 'A' cell to that location, moving only in 4 directions (up, down, left, right) through 'O' cells.

Solution Overview

The solution uses multi-source BFS.
All 'A' cells are enqueued with distance 0.
BFS explores all reachable 'O' cells.
A distance matrix stores the shortest distance to each cell.
For each query, the result is retrieved from this matrix.

Time Complexity: O(m * n) – each cell is visited once
Space Complexity: O(m * n) – for the distance matrix and queue

Sample Use

char[][] map = {
{'A', 'O', 'C'},
{'O', 'O', 'O'},
{'C', 'O', 'O'}
};
int[][] queries = {{1, 2}, {2, 1}};

Output:
[3, 2] // Shortest distances from nearest 'A' to each query cell
