# DSA Pattern Recognition Master Document
## Covers ~90% Coding Interview Problems

---

# 1. Frequency Counting Pattern

| Topic | Details |
|---|---|
| Main DS | HashMap |
| Used For | Counting frequency |
| Keywords | count, frequency, duplicate, anagram |

---

## Example Question

### Top K Frequent Elements

Given:
```java
nums = [1,1,1,2,2,3]
k = 2
```

Return top 2 frequent elements.

---

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

Top 2:

```text
[1,2]
```

---

## Answer

```java
Map<Integer,Integer> map = new HashMap<>();

for(int num : nums){
    map.put(num, map.getOrDefault(num,0)+1);
}
```

---

# 2. Fast Lookup Pattern

| Topic | Details |
|---|---|
| Main DS | HashSet |
| Used For | Fast contains check |
| Keywords | duplicate, seen before |

---

## Example Question

### Contains Duplicate

```java
nums = [1,2,3,1]
```

Return true if duplicate exists.

---

## Thinking

```text
Need fast lookup
→ HashSet
```

Process:

```text
1 added
2 added
3 added
1 already exists
```

Answer:
```text
true
```

---

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

| Topic | Details |
|---|---|
| Main DS | Two Pointers |
| Used For | Sorted arrays |
| Keywords | pair sum, palindrome |

---

## Example Question

### Two Sum II

```java
numbers = [1,2,3,4,6]
target = 10
```

---

## Thinking

```text
1 + 6 = 7
move left

2 + 6 = 8
move left

4 + 6 = 10
found
```

Answer:
```text
[4,6]
```

---

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

| Topic | Details |
|---|---|
| Main DS | Sliding Window |
| Used For | Continuous range |
| Keywords | substring, subarray |

---

## Example Question

### Longest Substring Without Repeating Characters

```java
"abcabcbb"
```

---

## Thinking

Window:

```text
abc ✓
abca ✗
remove a
bca ✓
```

Longest:
```text
3
```

---

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

| Topic | Details |
|---|---|
| Main DS | Binary Search |
| Used For | Sorted arrays |
| Keywords | search, sorted |

---

## Example Question

### Search Insert Position

```java
nums = [1,3,5,7,9]
target = 7
```

---

## Thinking

```text
mid = 5
7 > 5

search right
```

Found:
```text
index = 3
```

---

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

| Topic | Details |
|---|---|
| Main DS | Stack |
| Used For | Latest item first |
| Keywords | brackets, next greater |

---

## Example Question

### Valid Parentheses

```java
"(()())"
```

---

## Thinking

```text
( push
( push
) pop
( push
) pop
) pop
```

Valid:
```text
true
```

---

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

| Topic | Details |
|---|---|
| Main DS | PriorityQueue |
| Used For | Top K |
| Keywords | kth largest, top k |

---

## Example Question

### Kth Largest Element

```java
nums = [3,2,1,5,6,4]
k = 2
```

---

## Thinking

Keep only 2 largest.

Heap:

```text
[5,6]
```

Answer:
```text
5
```

---

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

| Topic | Details |
|---|---|
| Main DS | Queue |
| Used For | Level order |
| Keywords | shortest path |

---

## Example Question

### Binary Tree Level Order Traversal

```text
    1
   / \
  2   3
```

---

## Thinking

```text
Visit level by level
```

Output:

```text
1
2 3
```

---

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

| Topic | Details |
|---|---|
| Main DS | Recursion |
| Used For | All combinations |
| Keywords | subsets, permutations |

---

## Example Question

### Generate Subsets

```java
nums = [1,2]
```

---

## Thinking

```text
[]
[1]
[2]
[1,2]
```

Try all possibilities.

---

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

| Topic | Details |
|---|---|
| Main DS | DP Array |
| Used For | Optimization |
| Keywords | maximum, minimum |

---

## Example Question

### Climbing Stairs

```text
n = 5
```

---

## Thinking

```text
f(n)=f(n-1)+f(n-2)
```

Reuse previous answers.

Answer:
```text
8
```

---

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

# 11. Greedy Pattern

| Topic | Details |
|---|---|
| Main DS | Greedy |
| Used For | Best immediate choice |
| Keywords | minimum jumps |

---

## Example Question

### Jump Game

```java
[2,3,1,1,4]
```

---

## Thinking

```text
Keep farthest reachable index
```

Answer:
```text
true
```

---

## Answer

```java
int reach = 0;

for(int i=0; i<nums.length; i++){

    if(i > reach){
        return false;
    }

    reach = Math.max(reach, i + nums[i]);
}

return true;
```

---

# 12. Graph Pattern

| Topic | Details |
|---|---|
| Main DS | Graph |
| Used For | Connections |
| Keywords | routes, dependencies |

---

## Example Question

### Number of Islands

Grid:

```text
1 1 0
0 1 0
1 0 1
```

---

## Thinking

```text
Connected land
→ DFS/BFS
```

Answer:
```text
3 islands
```

---

## Answer

```java
void dfs(int r, int c){

    if(r<0 || c<0 || r>=rows || c>=cols || grid[r][c]=='0'){
        return;
    }

    grid[r][c] = '0';

    dfs(r+1,c);
    dfs(r-1,c);
    dfs(r,c+1);
    dfs(r,c-1);
}
```

---

# 13. Trie Pattern

| Topic | Details |
|---|---|
| Main DS | Trie |
| Used For | Prefix search |
| Keywords | autocomplete |

---

## Example Question

Words:

```text
apple
app
ape
```

Search:
```text
ap
```

---

## Thinking

```text
Character by character traversal
```

---

## Answer

```java
class TrieNode{

    TrieNode[] children = new TrieNode[26];

    boolean isWord;
}
```

---

# MASTER PATTERN RECOGNITION TABLE

| Keyword | Pattern |
|---|---|
| frequency | HashMap |
| duplicate | HashSet |
| pair sum sorted | Two Pointer |
| continuous | Sliding Window |
| sorted search | Binary Search |
| brackets | Stack |
| top k | Heap |
| shortest path | BFS |
| all combinations | Backtracking |
| optimal | DP |
| connections | Graph |
| prefix | Trie |

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

# MOST IMPORTANT INTERVIEW SKILL

Strong programmers do NOT memorize.

They recognize:

```text
Pattern
→ Data Structure
→ Algorithm
→ Solution
```
