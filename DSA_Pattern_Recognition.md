# DSA Pattern Recognition Complete Guide
## Covers ~90% Coding Interview Problems

---

# MASTER DSA PATTERN TABLE

| Pattern | Main DS/Algo | When to Use | Example Question | Small Example | Answer |
|---|---|---|---|---|---|
| Frequency Counting | HashMap | Count occurrences | Top K Frequent Elements | `[1,1,2,3,3,3]` | `1→2, 2→1, 3→3` |
| Fast Lookup | HashSet | Check duplicates quickly | Contains Duplicate | `[1,2,3,1]` | `true` |
| Two Pointer | Two Indexes | Sorted arrays/pairs | Two Sum II | `[1,2,3,4,6], target=10` | `[4,6]` |
| Sliding Window | Window Expansion | Continuous subarray/substring | Longest Unique Substring | `"abcabcbb"` | `3 ("abc")` |
| Binary Search | Divide Search Space | Sorted search | Search Insert Position | `[1,3,5,7,9], target=7` | `index=3` |
| Stack | LIFO | Brackets/next greater | Valid Parentheses | `"(()())"` | `true` |
| Heap / PriorityQueue | Min/Max Heap | Top K problems | Kth Largest Element | `[3,2,1,5,6,4], k=2` | `5` |
| BFS | Queue | Level order/shortest path | Binary Tree Level Order | `1→2→3` | `1 2 3` |
| DFS / Backtracking | Recursion | All combinations | Subsets | `[1,2]` | `[],[1],[2],[1,2]` |
| Dynamic Programming | Memoization | Repeated calculations | Climbing Stairs | `n=5` | `8 ways` |
| Greedy | Local Best Choice | Best immediate decision | Jump Game | `[2,3,1,1,4]` | `true` |
| Graph | BFS/DFS | Connections/networks | Number of Islands | `grid` | `3 islands` |
| Trie | Prefix Tree | Prefix search | Implement Trie | `apple, app` | `prefix=ap` |
| Union Find | Disjoint Set | Connected components | Redundant Connection | `1-2,2-3,3-1` | `cycle found` |
| Prefix Sum | Running Sum | Range sum queries | Subarray Sum Equals K | `[1,2,3]` | `sum quickly` |
| Monotonic Stack | Increasing Stack | Next greater element | Daily Temperatures | `[73,74,75]` | `[1,1,0]` |
| Interval Problems | Sorting + Merge | Overlapping intervals | Merge Intervals | `[[1,3],[2,6]]` | `[[1,6]]` |
| Matrix Traversal | DFS/BFS | Grid movement | Word Search | `board[][]` | `path exists` |
| Bit Manipulation | XOR/AND | Binary tricks | Single Number | `[2,2,1]` | `1` |
| Linked List | Pointer Manipulation | Node traversal | Reverse Linked List | `1→2→3` | `3→2→1` |

---

# QUICK RECOGNITION CHEAT SHEET

| If Question Says... | Think... |
|---|---|
| frequency/count | HashMap |
| duplicate/seen before | HashSet |
| pair in sorted array | Two Pointer |
| substring/subarray | Sliding Window |
| sorted search | Binary Search |
| top k/kth largest | Heap |
| brackets/undo | Stack |
| shortest path | BFS |
| all combinations | Backtracking |
| optimal/max/min | DP |
| network/connections | Graph |
| autocomplete/prefix | Trie |
| overlapping intervals | Merge Intervals |

---

# 1. Frequency Counting Pattern

## Main DS
`HashMap`

## Example Question
Top K Frequent Elements

```java
nums = [1,1,1,2,2,3]
k = 2
```

## Thinking

```text
Need count of each number
→ HashMap
```

Count:

```text
1 -> 3
2 -> 2
3 -> 1
```

## Answer

```java
Map<Integer,Integer> map = new HashMap<>();

for(int num : nums){
    map.put(num, map.getOrDefault(num,0)+1);
}
```

---

# 2. Fast Lookup Pattern

## Main DS
`HashSet`

## Example Question
Contains Duplicate

```java
nums = [1,2,3,1]
```

## Thinking

```text
Need fast lookup
→ HashSet
```

## Answer

```java
Set<Integer> set = new HashSet<>();

for(int num : nums){

    if(set.contains(num)){
        return true;
    }

    set.add(num);
}

return false;
```

---

# 3. Two Pointer Pattern

## Main DS
`Two Pointers`

## Example Question
Two Sum II

```java
numbers = [1,2,3,4,6]
target = 10
```

## Thinking

```text
1 + 6 = 7
move left

4 + 6 = 10
found
```

## Answer

```java
int left = 0;
int right = numbers.length - 1;

while(left < right){

    int sum = numbers[left] + numbers[right];

    if(sum == target){
        return new int[]{left,right};
    }

    if(sum < target){
        left++;
    }else{
        right--;
    }
}
```

---

# 4. Sliding Window Pattern

## Main DS
`Sliding Window`

## Example Question
Longest Substring Without Repeating Characters

```java
"abcabcbb"
```

## Thinking

```text
abc ✓
abca ✗
remove a
```

## Answer

```java
Set<Character> set = new HashSet<>();

int left = 0;
int max = 0;

for(int right = 0; right < s.length(); right++){

    while(set.contains(s.charAt(right))){
        set.remove(s.charAt(left));
        left++;
    }

    set.add(s.charAt(right));

    max = Math.max(max, right-left+1);
}
```

---

# 5. Binary Search Pattern

## Main DS
`Binary Search`

## Example Question
Search Insert Position

```java
nums = [1,3,5,7,9]
target = 7
```

## Answer

```java
int left = 0;
int right = nums.length - 1;

while(left <= right){

    int mid = (left + right)/2;

    if(nums[mid] == target){
        return mid;
    }

    if(nums[mid] < target){
        left = mid + 1;
    }else{
        right = mid - 1;
    }
}
```

---

# 6. Stack Pattern

## Main DS
`Stack`

## Example Question
Valid Parentheses

```java
"(()())"
```

## Answer

```java
Stack<Character> stack = new Stack<>();

for(char ch : s.toCharArray()){

    if(ch == '('){
        stack.push(ch);
    }else{

        if(stack.isEmpty()){
            return false;
        }

        stack.pop();
    }
}

return stack.isEmpty();
```

---

# 7. Heap / PriorityQueue Pattern

## Main DS
`PriorityQueue`

## Example Question
Kth Largest Element

```java
nums = [3,2,1,5,6,4]
k = 2
```

## Answer

```java
PriorityQueue<Integer> heap = new PriorityQueue<>();

for(int num : nums){

    heap.add(num);

    if(heap.size() > k){
        heap.poll();
    }
}

return heap.peek();
```

---

# 8. BFS Pattern

## Main DS
`Queue`

## Example Question
Binary Tree Level Order Traversal

## Answer

```java
Queue<TreeNode> queue = new LinkedList<>();

queue.offer(root);

while(!queue.isEmpty()){

    TreeNode node = queue.poll();

    System.out.println(node.val);

    if(node.left != null){
        queue.offer(node.left);
    }

    if(node.right != null){
        queue.offer(node.right);
    }
}
```

---

# 9. DFS / Backtracking Pattern

## Main DS
`Recursion`

## Example Question
Subsets

```java
nums = [1,2]
```

## Answer

```java
void backtrack(List<Integer> temp, int start){

    result.add(new ArrayList<>(temp));

    for(int i = start; i < nums.length; i++){

        temp.add(nums[i]);

        backtrack(temp, i+1);

        temp.remove(temp.size()-1);
    }
}
```

---

# 10. Dynamic Programming Pattern

## Main DS
`DP Array`

## Example Question
Climbing Stairs

```java
n = 5
```

## Answer

```java
int[] dp = new int[n+1];

dp[1] = 1;
dp[2] = 2;

for(int i=3; i<=n; i++){
    dp[i] = dp[i-1] + dp[i-2];
}

return dp[n];
```

---

# UNIVERSAL INTERVIEW THINKING

```text
1. Understand problem
2. Think brute force
3. Find bottleneck
4. Choose better DS/Algo
5. Optimize
```

---

# MOST IMPORTANT RULE

```text
Pattern
→ Data Structure
→ Algorithm
→ Solution
```
