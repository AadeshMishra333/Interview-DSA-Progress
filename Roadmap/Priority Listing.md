# Priority 0: Immediate Foundation Building

## A. Binary Trees and BST

This is your largest absolute coverage gap: 0/54 coded, although you know a few concepts. Trees are also prerequisites for recursion visualization, DFS, BST problems, heaps, and parts of graph reasoning.

### Immediate Targets
* Recursive and iterative preorder, inorder, postorder
* Level-order traversal
* Tree height and balanced tree
* Diameter and maximum path concepts
* Identical and symmetric trees
* Root-to-node path
* Lowest common ancestor
* BST search, insertion, validation
* Kth smallest/largest
* Inorder successor and predecessor

**Verdict:** Do not leave trees to random exposure. Include Trees/BST on at least 9 of the 14 days.

---

## B. Graphs

Your coverage is 10/53, mostly theory and foundational BFS/DFS problems. You can often identify a traversal, but struggle to convert the idea into implementation and lose track of the process.

### Immediate Targets
* BFS/DFS templates
* Connected components
* Grid-as-graph modeling
* Cycle detection in directed and undirected graphs
* Bipartite graph
* Topological sorting
* Shortest path in unweighted graph
* Dijkstra fundamentals
* Disjoint Set Union
* Minimum spanning tree, if time permits

**Verdict:** High-frequency topic, but learn it in layers. Do not jump directly from basic DFS to advanced shortest-path hard problems.

---

## C. Dynamic Programming

You have solved 17/55, but report that recurrence formation and intuitive derivation are very difficult. Once the recurrence is available, implementation is comparatively manageable.

Your actual DP weakness is therefore:
> “How do I transform a decision process into state, transition, base case, and answer?”

### Immediate Targets
* One-dimensional take/not-take
* Grid DP
* Subsequence and subset DP
* Knapsack family
* String DP
* Stock-state DP

### Derivation Steps
For every DP problem, derive in this order:
1. What choices do I have?
2. What information changes after a choice?
3. What minimum information uniquely identifies a subproblem?
4. What does the function return?
5. What are the smallest valid states?
6. Can the recursion be memoized?
7. What is the tabulation order?
8. Can space be optimized?

**Verdict:** DP needs structured repetition, not isolated random questions.

---

# Priority 1: Urgent Pattern Repair

## Sliding Window and Two Pointers

You have completed 6/12, but left/right pointer movement and window maintenance are weak.

### Focus Window Families
* Fixed-size window
* Longest valid window
* Minimum valid window
* Exact-count problems using `atMost(k) - atMost(k-1)`

> **Rule:** For every question, explicitly say:
> “Right expands the candidate window. Left moves only while the invariant is violated, or while I can safely improve the answer.”

---

## Monotonic Stack

Although you have solved several stack problems, you report weak recognition of when a monotonic stack should be used.

### Trigger Phrases
* Next/previous greater or smaller
* First greater element to the left/right
* Span or boundary
* Contribution of each element as minimum/maximum
* Rectangle or range determined by smaller boundaries

---

## Recursion and Backtracking

You have solved 12/25, but variable flow across recursive depth, base cases, and complexity visualization remain weak.

### Main Drill (Draw these out)
* Current index/state
* Available choices
* State before choice
* Recursive call
* Undo operation
* Return value

---

## Heaps

You have solved 7/17, but do not consistently see why a heap is preferable to sorting or another data structure.

### Heap Triggers
* Repeatedly need current minimum/maximum
* Maintain best k
* Streaming data
* Merge sorted sources
* Scheduling by earliest time or highest priority
* Need partial ordering rather than a fully sorted collection

---

# Priority 2: Revision-Heavy Topics

## Arrays and Binary Search

Arrays are 14/40, and solved problems are not recalled fluently. Binary search is 13/32, with one-dimensional and answer-space binary search relatively stronger, while two-dimensional coverage is missing.

### Action Items
* Fast mixed revision
* One or two unseen variants daily
* Explicit invariant explanation
* More matrix-search practice
* Binary search boundary discipline

---

## Linked Lists

You have good basic intuition, but edge cases and pointer positions are unreliable.

### Drawings Required for Each Problem
* Dummy node, if applicable
* `prev`, `curr`, `next`
* Head and tail after modification
* Empty list
* One-node list
* Two-node list
* Operation affecting the head

---

## Strings

All 15/15 listed string questions are covered, but you dislike the topic and solved questions still feel unfamiliar.

**Strategy:** Strings should remain in cycling, but do not allocate large isolated blocks. Mix them with hashing, sliding window, two pointers, stack, and DP.

---

# Priority 3: Maintenance

## Topics
* Sorting fundamentals
* Bit manipulation
* Greedy
* Basic stack/queue implementation

## Key Takeaways
* **Quick Sort:** Deserves one implementation refresh.
* **Bit Manipulation:** Needs a small theoretical cheat sheet because you report low exposure to recurring tricks.
* **Greedy:** Needs emphasis on explaining why a local choice remains safe.
