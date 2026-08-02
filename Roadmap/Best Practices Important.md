# V-I-S-U-A-L Protocol

## V: Verbalize the Problem

**Say:**
* “The input gives me…”
* “I need to return…”
* “The important constraints are…”
* “The obvious brute force is…”

*Do not start coding until you can explain the input-output transformation.*

---

## I: Identify the Structural Signal

**Ask:**
* Is the input sorted?
* Is it contiguous?
* Are repeated minimum/maximum queries present?
* Is this a next/previous greater/smaller problem?
* Is there an overlapping subproblem?
* Is this a traversal or connectivity problem?
* Am I constructing combinations or testing choices?
* Does the answer have monotonic feasibility?

**Then state:**
> “This suggests ___ because ___.”

---

## S: State the Invariant or State Definition

**Examples:**
* **Binary search:** “The answer remains inside this interval.”
* **Sliding window:** “The current window satisfies this condition.”
* **DP:** `dp[i][j]` represents…
* **BFS:** “The queue contains the next frontier.”
* **Linked list:** `prev` is the completed portion, `curr` is the node being processed.
* **Monotonic stack:** “The stack stores unresolved indices in increasing/decreasing order.”

*If you cannot state the invariant, you probably do not understand the algorithm deeply enough.*

---

## U: Use a Concrete Example

**Draw or write:**
* Array indices
* Pointer positions
* Queue/stack contents
* Recursive frames
* Graph visited set
* DP table/state
* Linked-list arrows

*Use a small nontrivial example, not only the sample.*

---

## A: Attack Edge Cases

**Minimum checklist:**
* Empty input
* One element
* Two elements
* All equal
* Already sorted or reverse sorted
* Duplicates
* Negative or zero values
* Answer at first or last position
* Disconnected graph
* Skewed tree
* Impossible result
* Maximum-size constraints

*Choose only the relevant cases rather than reciting all of them mechanically.*

---

## L: Lock Complexity and Code

**Before coding, state:**
* Time complexity
* Auxiliary space
* Recursion stack space
* Why each element/node/state is processed that many times

**After coding:**
* Dry-run one normal case.
* Dry-run one boundary case.
* Check loop termination.
* Check indexing.
* Check state restoration in recursion.
* Check whether the input is mutated.
* Reconfirm complexity from the code actually written.

---

# 7. Thinking-Out-Loud Script

Use this compact interview script:

> “I’ll first restate the problem and inspect the constraints. A brute-force solution would be ___ with complexity ___. The key structure I notice is ___. That suggests using ___ because ___. I will maintain the invariant/state ___. Let me dry-run it on a small example. The main edge cases are ___. The implementation will proceed in these steps: ___. The final time complexity is ___ and auxiliary space is ___.”

**If stuck:**
> “The difficulty is specifically deciding ___. I’m going to test whether ___ remains monotonic/invariant after a choice.”

*This sounds much stronger than becoming silent or saying “I don’t know.”*

---

# 8. Revision System to Fix Recall Anxiety

Your file specifically describes anxiety when a previously solved problem does not immediately return to mind.

Use a three-level recall test:

### Level 1: Recognition
From the title alone, write:
* Pattern
* Key observation
* Complexity
*(Limit: 2 minutes)*

### Level 2: Reconstruction
Without code, write:
* Data structure/state
* Algorithm steps
* Edge cases
*(Limit: 5 minutes)*

### Level 3: Reimplementation
Code from scratch and dry-run it.

> *A problem is genuinely revised only after Level 3.*

---

### Spaced Schedule
Revisit a problem:
1. Next day
2. Three days later
3. Seven days later
4. Final mixed review

*Do not retype every solved problem at every interval. At early intervals, use Levels 1–2. Use Level 3 for failed recalls and important interview patterns.*

---

### Error Tags
Tag every failure as one of:
* **PR:** Pattern recognition
* **IN:** Invariant/state definition
* **IM:** Implementation
* **EC:** Edge case
* **DR:** Dry run
* **TC:** Complexity
* **RC:** Recall
* **CM:** Communication

*Your weekly priority should be based on recurring error tags, not only topic counts.*
