# 📚 DSA Encyclopedia — Python Data Structures & Algorithms

> Master DSA with detailed explanations, optimized Python implementations, complexity analysis, and real-world applications used by top tech companies.

![Topics](https://img.shields.io/badge/topics-10-blue.svg)
![Algorithms](https://img.shields.io/badge/algorithms-40+-green.svg)
![Code Examples](https://img.shields.io/badge/code%20examples-30+-orange.svg)
![Use Cases](https://img.shields.io/badge/real--world%20use%20cases-35+-purple.svg)
![No Install](https://img.shields.io/badge/installation-none-lightgrey.svg)

---

## 📖 About

A comprehensive, hands-on reference guide covering every essential DSA topic — with concept explanations, Python implementations, Big-O complexity analysis, and real-world production use cases from companies like Google, Netflix, Redis, and more.

Open `PYTHON-DSA-HELP.html` in any modern browser and you're ready to go. No build tools. No dependencies. No installation.

---

## 🗂️ Topics Covered

| # | Topic | Key Concepts | Complexity Highlights |
|---|-------|--------------|-----------------------|
| 01 | Arrays | Two Pointers, Sliding Window, Binary Search, Kadane's, Prefix Sums | O(1) access, O(log n) search |
| 02 | Strings | Sliding Window, KMP, Rabin-Karp, Manacher's, Anagram Detection | KMP O(n+m) |
| 03 | Recursion | Base Case, Call Stack, Memoization, Backtracking, N-Queens, Divide & Conquer | Varies |
| 04 | Sorting & Searching | Quick Sort, Merge Sort, Heap Sort, Counting Sort, Binary Search on Answer | O(n log n) |
| 05 | Linked List | Singly/Doubly, Floyd's Cycle Detection, Reverse, Merge Sorted Lists | O(n) traversal |
| 06 | Stack & Queue | Monotonic Stack, Deque, BFS Queue, Expression Evaluation | O(1) push/pop |
| 07 | Hashing | Dictionary, Set, Collision Handling, Rolling Hash | O(1) average |
| 08 | Trees | BST, AVL, Heap, Segment Tree, BFS/DFS Traversals | O(log n) BST ops |
| 09 | Graphs | BFS, DFS, Dijkstra, Topological Sort, Union-Find, Prim's, Kruskal's | O((V+E) log V) |
| 10 | Dynamic Programming | Memoization, Tabulation, Knapsack, LCS, Edit Distance, Coin Change, LIS | O(n²) typical |

---

## ✨ Features

- 🎞️ **Interactive Binary Search Visualizer** — step-by-step animation of the search algorithm
- 🗂️ **Tabbed Layout** — Concept / Implementation / Use Cases tabs per topic
- 📊 **Complexity Tables** — color-coded Big-O for every operation
- 🌍 **Real-World Use Cases** — production examples from Google, Netflix, NCBI BLAST, GPS, and more
- 🐍 **Syntax-Highlighted Python Code** — with one-click copy buttons
- 📈 **Progress Indicator** — tracks which topic you're on
- ⌨️ **Keyboard Navigation** — Arrow keys to move between topics
- 🔍 **Sidebar Search** — filter topics instantly
- 📱 **Responsive / Mobile Friendly** — hamburger menu on small screens

---

## 🔑 Key Algorithms at a Glance

### Arrays

```python
# Two Sum (sorted) — O(n) time, O(1) space
def two_sum_sorted(arr, target):
    left, right = 0, len(arr) - 1
    while left < right:
        current_sum = arr[left] + arr[right]
        if current_sum == target:
            return [left, right]
        elif current_sum < target:
            left += 1
        else:
            right -= 1
    return []
```

```python
# Kadane's Algorithm (Max Subarray) — O(n)
def max_subarray(nums):
    max_sum = current_sum = nums[0]
    for num in nums[1:]:
        current_sum = max(num, current_sum + num)
        max_sum = max(max_sum, current_sum)
    return max_sum
```

### Graphs

```python
# BFS — O(V + E)
from collections import deque

def bfs(graph, start):
    visited = {start}
    queue = deque([start])
    while queue:
        node = queue.popleft()
        for neighbor in graph.get(node, []):
            if neighbor not in visited:
                visited.add(neighbor)
                queue.append(neighbor)
```

```python
# Dijkstra — O((V + E) log V)
import heapq

def dijkstra(graph, source):
    distances = [float('inf')] * len(graph)
    distances[source] = 0
    pq = [(0, source)]
    while pq:
        current_dist, u = heapq.heappop(pq)
        if current_dist > distances[u]:
            continue
        for v, weight in graph[u]:
            if distances[u] + weight < distances[v]:
                distances[v] = distances[u] + weight
                heapq.heappush(pq, (distances[v], v))
    return distances
```

### Dynamic Programming

```python
# Coin Change — O(n × amount)
def coin_change(coins, amount):
    dp = [amount + 1] * (amount + 1)
    dp[0] = 0
    for current_amount in range(1, amount + 1):
        for coin in coins:
            if coin <= current_amount:
                dp[current_amount] = min(dp[current_amount], dp[current_amount - coin] + 1)
    return -1 if dp[amount] > amount else dp[amount]
```

```python
# Longest Increasing Subsequence — O(n log n)
from bisect import bisect_left

def length_of_lis(nums):
    tails = []
    for num in nums:
        pos = bisect_left(tails, num)
        if pos == len(tails):
            tails.append(num)
        else:
            tails[pos] = num
    return len(tails)
```

---

## 🌍 Real-World Use Cases

| Topic | Production Example |
|-------|--------------------|
| Arrays / Binary Search | Google Search autocomplete ranking |
| Strings / KMP | `grep`, DNA sequence search (NCBI BLAST) |
| Sorting | Python's Timsort in `sorted()` / `.sort()`, database `ORDER BY` |
| Linked List | Browser history, LRU cache implementations |
| Stack | Undo/Redo systems, Python call stack |
| Queue | OS process scheduling, BFS in social networks |
| Hashing | Redis key-value store, Git object storage |
| Trees | File systems, HTML DOM, database B-Trees |
| Graphs | Google Maps routing, Netflix recommendations |
| Dynamic Programming | Autocorrect (Edit Distance), video compression (Viterbi) |

---

## 🚀 How to Use

1. Open `PYTHON-DSA-HELP.html` in any modern browser — no installation required.
2. Use the **left sidebar** to navigate between topics.
3. Use the **search bar** to filter topics instantly.
4. Press **↑ ↓ Arrow keys** for keyboard navigation.
5. Click tabs within each topic to switch between **Concept / Code / Use Cases**.
6. Hit **Copy** on any code block to copy the Python snippet.
7. Try the **interactive Binary Search visualizer** on the Arrays page.

---

## 📋 Requirements

- Any modern browser (Chrome, Firefox, Safari, Edge)
- Internet connection (for Google Fonts — JetBrains Mono & Sora)
- No build tools · No dependencies · No installation

---

## 📁 File Structure

```
PYTHON-DSA-HELP.html   ← Single self-contained file (HTML + CSS + JS)
README.md
```

<p align="center">Built for developers who want to understand DSA deeply — not just pass interviews.</p>
