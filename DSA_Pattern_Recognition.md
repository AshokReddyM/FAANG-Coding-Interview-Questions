# DSA Pattern Recognition — Covers ~90% Interview Problems

Most coding interviews are NOT random.

Around 90% of problems come from these patterns:

| Pattern | Main DS/Algo |
|---|---|
| Frequency Counting | HashMap |
| Fast Lookup | HashSet |
| Two Pointer | Two Indexes |
| Sliding Window | Window Expansion |
| Binary Search | Divide Search Space |
| Stack | LIFO |
| Heap / Top K | PriorityQueue |
| BFS | Queue |
| DFS / Backtracking | Recursion |
| Dynamic Programming | Memoization |
| Greedy | Local Best Choice |
| Graph | BFS/DFS |
| Trie | Prefix Tree |

---

# 1. Frequency Counting Pattern

## Keywords
- frequency
- count
- duplicate
- anagram

## Use
`HashMap`

## Example

```java
nums = [1,1,2,3,3,3]
```

Count:

```text
1 -> 2
2 -> 1
3 -> 3
```

## Thinking

```text
Need value → count mapping
→ HashMap
```

## Common Problems
- Top K Frequent
- Group Anagrams
- Majority Element

---

# 2. Fast Lookup Pattern

## Keywords
- contains
- seen before
- duplicate detection

## Use
`HashSet`

## Example

```java
[1,2,3,1]
```

Process:

```text
1 seen
2 seen
3 seen
1 already exists
```

Duplicate found.

## Thinking

```text
Need O(1) lookup
→ HashSet
```

## Common Problems
- Contains Duplicate
- Happy Number

---

# 3. Two Pointer Pattern

## Keywords
- sorted array
- pair sum
- reverse
- palindrome

## Use
`left++, right--`

## Example

Find pair sum = 10

```java
[1,2,3,4,6]
```

```text
1 + 6 = 7
move left

2 + 6 = 8
move left

4 + 6 = 10
found
```

## Thinking

```text
Sorted data
→ eliminate possibilities
```

## Common Problems
- Two Sum II
- Valid Palindrome

---

# 4. Sliding Window Pattern

## Keywords
- substring
- subarray
- longest
- shortest
- continuous

## Use
`expand + shrink window`

## Example

Longest substring without repeating chars.

```java
"abcabcbb"
```

Window:

```text
abc ✓
abca ✗
remove a
bca ✓
```

## Thinking

```text
Continuous range optimization
→ Sliding Window
```

## Common Problems
- Max Sum Subarray
- Longest Unique Substring

---

# 5. Binary Search Pattern

## Keywords
- sorted
- search efficiently
- minimum possible
- monotonic

## Use
`mid = (l+r)/2`

## Example

Search 7

```java
[1,3,5,7,9]
```

```text
mid=5
7 > 5

search right
```

## Thinking

```text
Can discard half?
→ Binary Search
```

## Common Problems
- Search Insert Position
- Rotated Sorted Array

---

# 6. Stack Pattern

## Keywords
- next greater
- brackets
- undo
- expression

## Use
`Stack`

## Example

```java
"(())"
```

Process:

```text
( push
( push
) pop
) pop
```

Valid.

## Thinking

```text
Need latest item first
→ Stack
```

## Common Problems
- Valid Parentheses
- Daily Temperatures

---

# 7. Heap / Top K Pattern

## Keywords
- top k
- kth largest
- most frequent

## Use
`PriorityQueue`

## Example

Top 2 largest:

```java
[1,5,2,9,7]
```

Keep heap size 2:

```text
[5,9]
```

## Thinking

```text
Need only best K
→ Heap
```

## Common Problems
- Top K Frequent
- Kth Largest Element

---

# 8. BFS Pattern

## Keywords
- shortest path
- minimum steps
- level order

## Use
`Queue`

## Example

Tree traversal:

```text
    1
   / \
  2   3
```

Output:

```text
1
2 3
```

## Thinking

```text
Visit level by level
→ BFS
```

## Common Problems
- Binary Tree Level Order
- Rotting Oranges

---

# 9. DFS / Backtracking Pattern

## Keywords
- all combinations
- all paths
- permutations

## Use
`Recursion`

## Example

Subsets of:

```java
[1,2]
```

Result:

```text
[]
[1]
[2]
[1,2]
```

## Thinking

```text
Try every possibility
→ Backtracking
```

## Common Problems
- Subsets
- Permutations

---

# 10. Dynamic Programming Pattern

## Keywords
- optimal
- maximum/minimum
- repeated work

## Use
`Store previous answers`

## Example

Fibonacci:

```text
f(5)=f(4)+f(3)
```

Avoid recalculating.

## Thinking

```text
Repeated subproblems
→ DP
```

## Common Problems
- Climbing Stairs
- House Robber

---

# 11. Greedy Pattern

## Keywords
- best immediate choice
- minimum intervals
- maximize

## Use
`Choose local best`

## Example

Coins:

```text
41
```

Take biggest first:

```text
25 + 10 + 5 + 1
```

## Thinking

```text
Local optimum works
→ Greedy
```

## Common Problems
- Jump Game
- Merge Intervals

---

# 12. Graph Pattern

## Keywords
- connections
- routes
- dependencies

## Use
`Adjacency List`

## Example

```text
A → B
A → C
```

Traverse with BFS/DFS.

## Thinking

```text
Node relationships
→ Graph
```

## Common Problems
- Number of Islands
- Course Schedule

---

# 13. Trie Pattern

## Keywords
- prefix
- autocomplete
- dictionary

## Use
`Trie`

## Example

Words:

```text
apple
app
ape
```

Shared prefix:

```text
ap
```

## Thinking

```text
Character-by-character search
→ Trie
```

---

# MASTER THINKING FLOW

## Step 1

Ask:

```text
What operation is repeated?
```

---

## Step 2

Match keyword

| Keyword | Pattern |
|---|---|
| frequency | HashMap |
| top k | Heap |
| continuous | Sliding Window |
| sorted | Binary Search |
| pair | Two Pointer |
| shortest path | BFS |
| all combinations | Backtracking |
| optimal | DP |

---

# UNIVERSAL INTERVIEW FORMULA

```text
1. Brute Force
2. Find bottleneck
3. Choose DS/Algo
4. Optimize
```

---

# FAST MEMORY TRICK

## Arrays
Think:
`Two Pointer / Sliding Window`

## Strings
Think:
`HashMap / Sliding Window`

## Trees
Think:
`DFS / BFS`

## Graphs
Think:
`BFS / DFS`

## Top K
Think:
`Heap`

## Optimization
Think:
`DP`

---

# THE MOST IMPORTANT THING

Strong programmers don’t memorize problems.

They recognize:

```text
Pattern → Data Structure → Solution
```

That is the real interview skill.
