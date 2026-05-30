# DSA Sorting Algorithms with Code Examples

---

# Interview Importance

| Algorithm      | Importance |
| -------------- | ---------- |
| Quick Sort     | ⭐⭐⭐        |
| Merge Sort     | ⭐⭐⭐        |
| Heap Sort      | ⭐⭐⭐        |
| Insertion Sort | ⭐⭐         |
| Counting Sort  | ⭐⭐         |
| Bubble Sort    | ⭐          |
| Selection Sort | ⭐          |

---

# Must Remember

```text id="k9svyb"
Bubble     → Swap Adjacent
Selection  → Select Minimum
Insertion  → Insert in Order
Merge      → Divide and Merge
Quick      → Pivot Partition
Heap       → Heap Structure
Counting   → Count Frequency
```

## 1. Bubble Sort

### Idea

Compare adjacent elements and swap if needed.

### Example

```text id="w9nw9c"
Input : [5,3,8,4,2]

Pass 1:
5 3 8 4 2
↓
3 5 8 4 2
↓
3 5 4 8 2
↓
3 5 4 2 8

Final:
2 3 4 5 8
```

### Java Code

```java id="4lkj5p"
public static void bubbleSort(int[] arr){

    int n = arr.length;

    for(int i=0;i<n-1;i++){

        for(int j=0;j<n-i-1;j++){

            if(arr[j] > arr[j+1]){

                int temp = arr[j];
                arr[j] = arr[j+1];
                arr[j+1] = temp;
            }
        }
    }
}
```

### Complexity

```text id="qnn9nh"
Time  : O(n²)
Space : O(1)
```

---

# 2. Selection Sort

### Idea

Find minimum element and place at correct position.

```
if(nums[i] > nums[j]) {
    minIndex = j;
}
```

You should compare with the current minimum element, not always with nums[i].

### Example

```text id="x3e8nk"
Input

5 3 8 4 2

Minimum = 2

2 3 8 4 5

Minimum = 3

2 3 8 4 5

Minimum = 4

2 3 4 8 5

2 3 4 5 8
```

### Java Code

```java id="g5z7wi"
public static void selectionSort(int[] arr){

    int n = arr.length;

    for(int i=0;i<n-1;i++){

        int minIndex = i;

        for(int j=i+1;j<n;j++){

            if(arr[j] < arr[minIndex]){
                minIndex = j;
            }
        }

        int temp = arr[i];
        arr[i] = arr[minIndex];
        arr[minIndex] = temp;
    }
}
```

### Complexity

```text id="xlp2eg"
Time  : O(n²)
Space : O(1)
```

---

# 3. Insertion Sort

### Idea

Insert current element into sorted portion.

### Example

```text id="khp4pw"
5 3 8 4 2

5

3 5

3 5 8

3 4 5 8

2 3 4 5 8
```

### Java Code

```java id="okh2z4"
public static void insertionSort(int[] arr){

    for(int i=1;i<arr.length;i++){

        int key = arr[i];
        int j = i-1;

        while(j>=0 && arr[j] > key){

            arr[j+1] = arr[j];
            j--;
        }

        arr[j+1] = key;
    }
}
```

### Complexity

```text id="5p5duf"
Best  : O(n)
Worst : O(n²)
```

---

# 4. Merge Sort ⭐

### Idea

Divide → Sort → Merge

### Example

```text id="7d3x9q"
5 3 8 4 2

5 3 | 8 4 2

5 | 3

8 | 4 2

4 | 2

Merge

3 5

2 4

2 4 8

2 3 4 5 8
```

### Java Code

```java id="ytuxgx"
public static void mergeSort(int[] arr, int left, int right){

    if(left >= right){
        return;
    }

    int mid = (left + right) / 2;

    mergeSort(arr,left,mid);
    mergeSort(arr,mid+1,right);

    merge(arr,left,mid,right);
}
```

### Complexity

```text id="lzg1gw"
Time  : O(n log n)
Space : O(n)
```

---

# 5. Quick Sort ⭐⭐⭐

### Idea

Choose Pivot → Partition

### Example

```text id="8u9l6h"
5 3 8 4 2

Pivot = 5

3 4 2 | 5 | 8

Pivot = 3

2 | 3 | 4

Final

2 3 4 5 8
```

### Java Code

```java id="5otd0s"
public static void quickSort(int[] arr,int low,int high){

    if(low < high){

        int pivot = partition(arr,low,high);

        quickSort(arr,low,pivot-1);

        quickSort(arr,pivot+1,high);
    }
}
```

### Complexity

```text id="vxzn4g"
Average : O(n log n)
Worst   : O(n²)
```

---

# 6. Heap Sort ⭐⭐

### Idea

Build Max Heap → Remove Root

### Example

```text id="w8mg67"
Input

5 3 8 4 2

Max Heap

      8
    /   \
   4     5
  / \
 3   2

Output

2 3 4 5 8
```

### Java Code

```java id="xq9d2e"
public static void heapSort(int[] arr){

    PriorityQueue<Integer> pq =
            new PriorityQueue<>();

    for(int num : arr){
        pq.add(num);
    }

    int i = 0;

    while(!pq.isEmpty()){

        arr[i++] = pq.poll();
    }
}
```

### Complexity

```text id="r16z9q"
Time  : O(n log n)
Space : O(1)
```

---

# 7. Counting Sort

### Idea

Count frequency.

### Example

```text id="6xrrza"
1 4 2 1 3

Count

1 → 2
2 → 1
3 → 1
4 → 1

Result

1 1 2 3 4
```

### Java Code

```java id="4hnd0z"
int[] count = new int[10];

for(int num : arr){

    count[num]++;
}

for(int i=0;i<count.length;i++){

    while(count[i] > 0){

        System.out.print(i + " ");

        count[i]--;
    }
}
```

### Complexity

```text id="u8uy1n"
O(n + k)
```


