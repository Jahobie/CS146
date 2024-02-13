# Time Complexity Analysis

## Problem 1: Insertion Sort

### Algorithm Description
Insertion Sort is a simple sorting algorithm that builds the final sorted array one item at a time. It iterates through an array, growing the sorted array behind it.


## Java Implementation



```java
public static int[] insertionSort(int[] A, int n) {
    for (int i = 1; i < n; ++i) {           // (N + 1) times
        int key = A[i];                     // (N) times
        int j = i - 1;                       // (N) times
        while (j >= 0 && A[j] > key) {      // (1 + 2 + 3 + ... + N) times = n^2/2
            A[j + 1] = A[j];
            j = j - 1;
        }
        A[j + 1] = key;
    }
    return A;
}
```

-F(N)=(N+1) + 3N + N^2/2 

- The dominant term in this polynomial expression is n^2/2 therefore the complexity for insertion sort is quadratic.
​






