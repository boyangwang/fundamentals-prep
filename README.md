# fundamentals-prep
<!-- TOC depthFrom:2 -->

- [1. Data structures](#1-data-structures)
    - [1.1. Arrays](#11-arrays)
        - [Resizable array](#resizable-array)
    - [1.2. Linked Lists](#12-linked-lists)
    - [1.3. Stack / queue](#13-stack--queue)
    - [1.4. Hash table (collison)](#14-hash-table-collison)
    - [1.5. Heap](#15-heap)
    - [1.6. Priority Queue](#16-priority-queue)
    - [1.7. Binary search tree](#17-binary-search-tree)
        - [1.7.1. AVL, Red–black tree](#171-avl-redblack-tree)
        - [1.7.2. preorder, inorder, postorder, BFS, DFS](#172-preorder-inorder-postorder-bfs-dfs)
    - [1.8. Graph](#18-graph)
        - [1.8.1. adjacency matrix / adjacency list](#181-adjacency-matrix--adjacency-list)
- [2. Algorithms](#2-algorithms)
    - [2.1. Sorting](#21-sorting)
        - [2.1.1. bubblesort](#211-bubblesort)
        - [2.1.2. selection insertion](#212-selection-insertion)
        - [2.1.3. heapsort](#213-heapsort)
        - [2.1.4. quicksort mergesort](#214-quicksort-mergesort)
    - [2.2. Binary search](#22-binary-search)
    - [2.3. Dijkstra](#23-dijkstra)
    - [2.4. Floyd–Warshall (All pair shortest path)](#24-floydwarshall-all-pair-shortest-path)
    - [2.5. Backpack X](#25-backpack-x)
    - [2.6. Recursion](#26-recursion)
    - [2.7. DP](#27-dp)
    - [2.8. Astar](#28-astar)
- [3. OS](#3-os)
- [4. System design](#4-system-design)
- [5. Bits & bytes](#5-bits--bytes)
- [6. Probability & combinatorics](#6-probability--combinatorics)
- [7. Review leetcode questions](#7-review-leetcode-questions)

<!-- /TOC -->

## 1. Data structures

### 1.1. Arrays

- insert(append) `O(1)`
- insert(in the middle) `O(n)`
- access(index) `O(1)`
- search `O(n)`
- continuous memory block, access nearby elements for efficiency
- homogenous element size, so can calculate mem addr and access

#### Resizable array

- insert(amortized) `O(1)`

### 1.2. Linked Lists

- insert(with ref to head/tail) `O(1)`
- access(index) `O(n)`
- search `O(n)`
- singly or doubly linked, point to next node by mem addr
- advantage: easy to insert in the middle when have ref to node, no shifting needed

### 1.3. Stack / queue

- stack, push pop
- queue, enqueue, dequeue

### 1.4. Hash table (collison)

- chaining, put `O(1)`, get `O(1)` worst `O(n)`. You can have multiple times keys than tablesize
- open addressing, with some probe sequence e.g. linear. Hard to have too high load factor
- resize, need to move everything because hash % tablesize, `O(n)`
- load factor: .75

### 1.5. Heap

### 1.6. Priority Queue

### 1.7. Binary search tree

#### 1.7.1. AVL, Red–black tree

#### 1.7.2. preorder, inorder, postorder, BFS, DFS

### 1.8. Graph

#### 1.8.1. adjacency matrix / adjacency list

## 2. Algorithms

### 2.1. Sorting

#### 2.1.1. bubblesort

#### 2.1.2. selection insertion

#### 2.1.3. heapsort

#### 2.1.4. quicksort mergesort

### 2.2. Binary search

### 2.3. Dijkstra

### 2.4. Floyd–Warshall (All pair shortest path)

### 2.5. Backpack X

### 2.6. Recursion

### 2.7. DP

### 2.8. Astar

## 3. OS

## 4. System design

## 5. Bits & bytes

## 6. Probability & combinatorics

## 7. Review leetcode questions
