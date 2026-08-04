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
| 2026-08-02 | Subarray Sum Equals K | LeetCode | Prefix Sum + Hashing | Medium | Editorial | **PR, EC** | Tried two pointers; forgot array contains negative numbers. | Two pointers fails with negative numbers—use `PrefixSum[i] - K` map lookup instead. | 2026-08-05 |
| 2026-08-03 | Lowest Common Ancestor | LeetCode | Binary Trees | Medium | Independent | **EC** | Failed edge case where root itself is `p` or `q`. | Tree recursion base case must return `root` immediately if `root == p \|\| root == q`. | 2026-08-06 |
| 2026-08-03 | Sliding Window Maximum | LeetCode | Monotonic Queue | Hard | Hint Used | **IN, DR** | Couldn't maintain queue order properly when shrinking window. | Monotonic Deque should store *indices*, and remove from front when `index <= i - k`. | 2026-08-10 |
| 2026-08-02 | Binary Tree Preorder Traversal | LeetCode | Recursion | Easy | Solved |**TC** | Couldn't derive time and space complexities for recurrence relation | I have given in notes a general way to get the time and space complexities of recursive problems in particular | 2026-08-05 |
| 2026-08-02 | Diameter of a Binary Tree | LeetCode | Recursion | Easy | Solved by AI |**IM** | Confused in what to update and what to return | update `max_dia = max(left+right,max_dia)` and return `1+max of left and right` | 2026-08-05 |
| 2026-08-02 | Subarray sum equals K | LeetCode | Arrays | Medium | _FOR REVIEW_ | **IM, DR, PR** | Confused in how to manage negative numbers | To Review | 2026-08-03 |
| 2026-08-02 | Subarray product less than k | LeetCode | Sliding Window | Medium | Solved | **IM** | Order of Updation of sliding window and product was not correct | maintain this order, insert window, increment l, update answer | Done |
| 2026-08-02 | Perfect Squares | LeetCode | DP | Medium | Solved Saw Hint | **IM, DR, PR** | Didn't know how to implement non linear jumps in DP | An inner loop can help to give non linear jumps | 2026-08-05 |
| 2026-08-03 | 01 Matrix | LeetCode | DP | Medium | Solved Saw Hint | **IM, PR** | Didn't have a general idea of matrix neighbor traversal | Top left bottom right approach is excellent | 2026-08-06 |
| 2026-08-03 | Island Perimeter | LeetCode | Array 2d | Easy | Solved Saw Hint | **IM, PR** | Didn't have a general idea of matrix neighbor traversal | Top left approach is enough due to `+4 -2` rule | 2026-08-06 |
| 2026-08-03 | Magnetic Force Between 2 Balls | LeetCode | BS on answer | Medium | Solved Saw Hint | **DR, PR** | Didn't get the condition to update l,m,r correct | When trial of an answer, check if we can place all balls at distance `>= answer` | 2026-08-06 |
| 2026-08-03 | Shortest path with obstacle elimination | LeetCode | BFS,DP,Matrix | Hard | Unsolved | **IM, PR, DR** | Many concepts missing, can't visualize the easiest version that i can code as well | ___ | 2026-08-08 |

---

### How to Maintain This Repository

* **Immediate Logging:** Add an entry immediately after completing a problem or reviewing an editorial.
* **Combine Tags:** If you missed both the pattern and an edge case, tag it as **`PR, EC`**.
* **3-Level Spaced Revision:**
  1. **Level 1 (Day 1):** Title-only recall of pattern and invariant (2 mins).
  2. **Level 2 (Day 3):** Reconstruct algorithm steps and edge cases on paper (5 mins).
  3. **Level 3 (Day 7):** Code from scratch and dry-run without looking at past solutions.
