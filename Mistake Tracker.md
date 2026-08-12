# DSA Mistake Tracker & Error Tag System

## 1. Error Tag System Definition

Use these standardized 2-letter tags to diagnose **why** a problem was missed, required editorial help, or took too long to solve. Focus on fixing the underlying cause rather than just counting solved problems.

| Tag | Category | Definition & Examples |
| :---: | :--- | :--- |
| **PR** | **Pattern Recognition** | Failed to recognize the underlying approach or data structure (e.g., missed that it was a Sliding Window, Monotonic Stack, or Topological Sort problem). |
| **IN** | **Invariant / State** | Knew the general approach, but couldn't define the loop invariant, window maintenance condition, or DP state/transition formula. |
| **IM** | **Implementation** | Knew the exact logic, but made implementation errors (e.g., off-by-one indexing, bad pointer reassignments, or syntax bugs). |
| **EC** | **Edge Case** | Logic failed on boundary conditions (e.g., empty array, single-element input, duplicates, negative numbers, integer overflow, or disconnected graphs). |
| **DR** | **Dry Run** | Skipped or rushed manual dry-running before submitting, missing state update bugs or loop termination flaws. |
| **TC** | **Time/Space Complexity** | Couldn't derive, state, or justify the time or auxiliary space complexity correctly while thinking out loud. |
| **RC** | **Recall** | Problem was solved in the past, but the core intuition felt entirely new or forgotten upon re-encountering it. |
| **CM** | **Communication** | Struggled to articulate thoughts, explain trade-offs, or speak through the intuition clearly before writing code. |

---

## 2. Mistake Tracker Log Template

Copy and fill out the table below whenever you face friction, fail a submission, or rely on solutions/hints.

| Date | Problem Title | Platform | Topic / Pattern | Difficulty | Solved Status | Error Tag(s) | Key Mistake / Root Cause | Actionable Takeaway / Pattern Rule | Next Review Date |
| :---: | :--- | :---: | :--- | :---: | :---: | :---: | :--- | :--- | :---: |
| 2026-08-02 | Binary Tree Preorder Traversal | LeetCode | Tree, Recursion | Easy | Solved | **TC** | Could not derive time and auxiliary-space complexity for recursive traversal | Count how many nodes are visited and separately count recursion-stack height. Time is `O(n)`; auxiliary space is `O(h)`, becoming `O(n)` for a skewed tree | 2026-08-05 |
| 2026-08-02 | Diameter of Binary Tree | LeetCode | Tree, Recursion, Postorder | Easy | Solved by AI | **IN, IM** | Confused between the value to update globally and the value to return to the parent | At each node, update diameter using `leftHeight + rightHeight`, but return `1 + max(leftHeight, rightHeight)` | 2026-08-05 |
| 2026-08-02 | Subarray Sum Equals K | LeetCode | Prefix Sum, HashMap | Medium | For Review | **PR, IN, DR** | Could not handle negative numbers and did not identify why ordinary sliding window fails | With negative numbers, use prefix sum plus frequency map. For current prefix `s`, count previous prefixes equal to `s - k` | 2026-08-03 |
| 2026-08-02 | Subarray Product Less Than K | LeetCode | Sliding Window | Medium | Solved | **IN, IM** | Window shrink, product update, and answer update were performed in the wrong order | Expand right, multiply, shrink while invalid, then add `right - left + 1` valid subarrays ending at right | Done |
| 2026-08-02 | Perfect Squares | LeetCode | Dynamic Programming | Medium | Solved, Saw Hint | **PR, IN, IM** | Did not know how to implement transitions involving non-linear jumps | Let `dp[i]` represent the minimum squares forming `i`; use an inner loop over every square `j*j <= i` | 2026-08-05 |
| 2026-08-03 | 01 Matrix | LeetCode | Matrix, Multi-source BFS / DP | Medium | Solved, Saw Hint | **PR, IM** | Lacked a reusable framework for traversing matrix neighbours | Use a four-direction array. For shortest distance from many sources, initialize all zero cells together and run multi-source BFS | 2026-08-06 |
| 2026-08-03 | Island Perimeter | LeetCode | Matrix Traversal, Local Contribution | Easy | Solved, Saw Hint | **PR, IM** | Lacked a consistent matrix-neighbour traversal method | Add `4` for every land cell and subtract `2` for every previously counted shared edge, checking only top and left | 2026-08-06 |
| 2026-08-03 | Magnetic Force Between Two Balls | LeetCode | Binary Search on Answer, Greedy Feasibility | Medium | Solved, Saw Hint | **PR, IN, DR** | Could not correctly derive the feasibility condition and boundary updates | Guess minimum distance `d`; greedily place balls. If all balls fit, `d` is feasible, so search for a larger answer | 2026-08-06 |
| 2026-08-03 | Shortest Path in a Grid with Obstacles Elimination | LeetCode | BFS, State-Space Search, Matrix | Hard | Unsolved | **PR, IN, IM, DR** | Could not visualize the enlarged state and combine BFS distance with remaining eliminations | A state is not only `(row, col)` but `(row, col, remainingEliminations)`. BFS explores states level by level; prune dominated states | 2026-08-08 |
| 2026-08-12 | Top K Frequent Elements | LeetCode | HashMap, Bucket Sort, Heap | Medium | Solved, Concept Review | **PR, IN, IM** | The mapping from element frequency to top-k selection was not fully internalized | First map `value -> frequency`. Then either heap by frequency or bucket by frequency. Separate counting from ranking | 2026-08-15 |
| 2026-08-12 | Kth Largest Element in a Stream | LeetCode | Min-Heap, Data Stream | Easy | Solved, Concept Review | **IN, IM, TC** | Need to understand why a min-heap of size `k` gives the kth largest and how Python `heapq` works internally | Maintain only the largest `k` values seen. The heap root is the smallest among those `k`, therefore it is the kth largest overall | 2026-08-15 |
| 2026-08-12 | K Closest Points to Origin | LeetCode | Sorting, TimSort, Heap / Quickselect | Medium | Solved, Algorithm Review | **PR, TC, CM** | Need to distinguish sorting, heap, and selection approaches and understand Python sorting | Compare squared distances. Full sorting is `O(n log n)`; a size-k heap is `O(n log k)`; Quickselect is average `O(n)` | 2026-08-15 |
| 2026-08-12 | Reverse Linked List II | LeetCode | Linked List, In-place Reversal | Medium | Solved, Edge-Case Review | **EC, IN, DR** | Main solution is understood, but head modification and boundary cases require analysis | Use a dummy node. Identify the node before the segment, reverse exactly `right-left+1` nodes, then reconnect both boundaries | 2026-08-15 |
| 2026-08-12 | Non-overlapping Intervals | LeetCode | Greedy, Intervals, Sorting by End | Medium | Solved, Concept Review | **PR, IN, CM** | Need a durable intuition for why sorting by ending time is optimal | Keep the interval with the earliest end because it leaves maximum room for future intervals. Count every overlapping interval removed | 2026-08-15 |
| 2026-08-12 | Serialize and Deserialize Binary Tree | LeetCode | Binary Tree, Recursion, Strings, Design | Hard | Solved, Deep Review | **PR, IN, IM, EC** | Need a clearer base-level understanding of preserving tree structure through a string | Store null markers as well as values. Traversal order plus null markers uniquely preserves both values and structure | 2026-08-16 |
| 2026-08-12 | Minimum Operations to Reduce X to Zero | LeetCode | Problem Transformation, Sliding Window | Medium | Solved, Concept Review | **PR, IN, CM** | Need to strengthen the transformation from removing ends to retaining a middle subarray | Convert the problem into finding the longest middle subarray with sum `totalSum - x`; answer is `n - longestLength` | 2026-08-15 |
| 2026-08-12 | Lowest Common Ancestor of a Binary Tree | LeetCode | Tree Recursion, Postorder, Divide and Conquer | Medium | Unsolved | **PR, IN, IM, DR** | Could not define what each recursive call should return or visualize information moving upward | Each subtree returns a found node or null. If left and right both return non-null, the current node is the split point and hence the LCA | 2026-08-16 |
| 2026-08-12 | Car Pooling | LeetCode | Intervals, Sweep Line, Difference Array | Medium | Solved, Concept Review | **PR, IN, IM** | Need to develop the interval-event intuition and connect it to Meeting Rooms II | Convert every trip into `+passengers` at pickup and `-passengers` at drop-off. Process events in position order and track active load | 2026-08-15 |
| 2026-08-12 | Top K Frequent Words | LeetCode | HashMap, Heap, Custom Ordering | Medium | Solved, Deep Review | **IN, IM, EC** | Need to understand heap comparison when frequency and lexicographic order interact | Ranking has two keys: higher frequency first and lexicographically smaller word first on ties. Define the desired order before choosing heap entries | 2026-08-16 |
| 2026-08-12 | Reorganize String | LeetCode | Greedy, Max-Heap, Frequency | Medium | Solved, Concept Review | **PR, IN, EC** | Need to understand why temporarily holding the previously used character prevents repetition | Repeatedly choose the most frequent currently valid character, hold the previous character out for one turn, then reinsert it if still available | 2026-08-16 |
| 2026-08-12 | Distant Barcodes | LeetCode | Greedy, Max-Heap, Frequency | Medium | Solved, Concept Review | **PR, IN, IM** | Need to unify it with the reusable no-adjacent-equal greedy pattern | Use the same dominant-frequency strategy as Reorganize String: choose a valid maximum-frequency item and delay reuse of the previous item | 2026-08-16 |
| 2026-08-12 | Minimum Absolute Difference in BST | LeetCode | BST, Inorder Traversal | Easy | Solved, Concept Review | **PR, IN, EC** | Need to connect the BST ordering property with adjacent-value comparison | Inorder traversal of a BST is sorted. Therefore the minimum difference must occur between two consecutive values in inorder order | 2026-08-15 |
| 2026-08-12 | Time Based Key-Value Store | LeetCode | HashMap, Sorted Timestamps, Binary Search | Medium | Solved, Deep Review | **PR, IN, IM, EC** | Need a reusable method for time-versioned data and predecessor search | Store a sorted list of `(timestamp, value)` for each key. Query the rightmost timestamp less than or equal to the requested time | 2026-08-16 |
| 2026-08-12 | Find if Path Exists in Graph | LeetCode | Graph, BFS, DFS, Adjacency List | Easy | Solved, Foundation Review | **PR, IM, CM** | Need stronger understanding of BFS versus DFS, visited-state handling, and `defaultdict` adjacency construction | For reachability, either BFS or DFS is valid. Mark nodes visited when discovered and represent every undirected edge in both directions | 2026-08-15 |
| 2026-08-12 | Accounts Merge | LeetCode | Union-Find / DSU, HashMap, Graph Components | Medium | Solved, Deep Review | **PR, IN, IM** | Need to understand how emails become connected components and how DSU groups them | Map every email to an owner/index, union emails from the same account, then group emails by their final representative | 2026-08-16 |
| 2026-08-12 | Symmetric Tree | LeetCode | Tree Recursion, Mirror Comparison | Easy | Solved, Foundation Review | **IN, EC, DR** | Need to develop the mirror-recursion invariant instead of treating it as ordinary equality | Two subtrees are mirrors when their roots match, left of one mirrors right of the other, and right mirrors left | 2026-08-15 |

---

### How to Maintain This Repository

* **Immediate Logging:** Add an entry immediately after completing a problem or reviewing an editorial.
* **Combine Tags:** If you missed both the pattern and an edge case, tag it as **`PR, EC`**.
* **3-Level Spaced Revision:**
  1. **Level 1 (Day 1):** Title-only recall of pattern and invariant (2 mins).
  2. **Level 2 (Day 3):** Reconstruct algorithm steps and edge cases on paper (5 mins).
  3. **Level 3 (Day 7):** Code from scratch and dry-run without looking at past solutions.
