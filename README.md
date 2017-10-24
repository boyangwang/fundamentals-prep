# fundamentals-prep
<!-- TOC depthFrom:2 -->

- [1. Data structures](#1-data-structures)
    - [1.1. Arrays](#11-arrays)
        - [1.1.1. Resizable array](#111-resizable-array)
    - [1.2. Linked Lists](#12-linked-lists)
    - [1.3. Stack / queue](#13-stack--queue)
    - [1.4. Hash table (collison)](#14-hash-table-collison)
    - [1.5. Heap / priority Queue](#15-heap--priority-queue)
    - [1.7. Binary search tree](#17-binary-search-tree)
        - [1.7.1. AVL, Red–black tree](#171-avl-redblack-tree)
        - [1.7.2. preorder, inorder, postorder, BFS, DFS, invert](#172-preorder-inorder-postorder-bfs-dfs-invert)
    - [1.8. Graph](#18-graph)
        - [1.8.1. adjacency matrix / adjacency list](#181-adjacency-matrix--adjacency-list)
- [2. Algorithms](#2-algorithms)
    - [2.1. Sorting](#21-sorting)
        - [2.1.1. bubblesort](#211-bubblesort)
        - [2.1.2. selection insertion](#212-selection-insertion)
        - [2.1.3. quicksort mergesort](#213-quicksort-mergesort)
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

#### 1.1.1. Resizable array

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
- load factor e.g. .75

### 1.5. Heap / priority Queue

- parent is >= child for max heap, or parent <= child for min heap. Root is max/min
- not like bst where left is small, right is big
- stored using array
- find-max/min peek `O(1)`
- extract-max/min pop `O(logn)` remove root and put last to first, then sift down
- add `O(logn)` add to last and sift up
- my children `(2*idx + 1) (2*idx + 2)`
- heapsort, if constructed by insertions, `O(nlogn)`, in place.
- Robert Floyd's optimization:
    ```
    function buildHeap(arr) {
        for (let i=Math.floor; i>=0; i++)
            headpify(arr, i);
    }
    function heapify(arr, i)
        let left = 2i+1, right = 2i+2;
        let max = Math.max(left, right i);
        if (max != i) {
            swap(max, i);
            // observe here. We recurse on max, which is either left or right child
            // it's lower down the height. And it's checking only if swap happened
            heapify(arr, max)
        }
    ```
    The difference is subtle here. For insertion method, it goes up from bottom, it's bound to be nlogn because more than half of all will be climbing up tree at logn height. But for Floyd, because it goes down, half of it will have only height 1, etc.

- heap property: a node has the heap property if the value in the node is as large as or larger than the values in its children. All leaf nodes automatically have the heap property

### 1.7. Binary search tree

#### 1.7.1. AVL, Red–black tree

- avl tree
    - https://en.wikipedia.org/wiki/AVL_tree
    - insert delete search `O(logn)`
    - keep balance factor, left-heavy, right-heavy, or balanced. When balance is broken, do rotation.
    - insert case below as example. If parent factor is offset to 0, break from loop. If parent balanced, but I make it inbalance by 1, it's ok continue up the tree. If parent is inbalanced, and I cause it to be +2/-2, do rotation
    - rotation, make the deep subtree to be root. So root's shorter subtree increase height since root is now at height 1. For the 2 subtrees of deep subtree of root, one remain to be a subtree and is now height-1 because deep sub is the root. The other will become sub of original root, staying same height, but it's ok, because others have h+1
- red-black tree

#### 1.7.2. preorder, inorder, postorder, BFS, DFS, invert

- traversals: 
- bfs, dfs
    - just use a queue, enqueue root, dequeue root, process root, enqueue left, enqueue right, continue
    ```
    exports.bfs = function(root, processor) {
        let queue = [], curLevel = 0, levelSize;
        if (root) {
            queue.push(root);
        }
        while (queue.length !== 0) {
            levelSize = queue.length;
            for (let i=0; i<levelSize; i++) {
                let node = queue.shift();
                processor(node);
                if (node.left) {
                    queue.push(node.left);
                }
                if (node.right) {
                    queue.push(node.right);
                }
            }
            curLevel += 1;
        }
    };
    ```
    - just use a stack, push root, pop root. Dependind on pre/in/post order, it can be:
    ```
     
    ```
- invert, recur: swapLeftRight(root); invert(root.left); invert(root.right);
- invert, iterative: stack

### 1.8. Graph

#### 1.8.1. adjacency matrix / adjacency list

## 2. Algorithms

### 2.1. Sorting

#### 2.1.1. bubblesort

#### 2.1.2. selection insertion

#### 2.1.3. quicksort mergesort

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
