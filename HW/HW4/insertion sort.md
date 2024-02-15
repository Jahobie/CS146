# Time Complexity Analysis

## Problem 1: Insertion Sort

### Algorithm Description
Insertion Sort is a simple sorting algorithm that builds the final sorted array one item at a time. It iterates through an array, growing the sorted array behind it.

### Time Complexity
- **Best Case:** O(n) Omega(n) Theta(n) - When the array is already sorted, it only requires a single pass through the array.
- **Average Case:** O(n^2)  Omega(n) Theta(n) - On average, each element must be compared with every other element in the array.
- **Worst Case:** O(n^2)  Omega(n) Theta(n) - When the array is in reverse order, each element must be moved to the beginning of the array.



```java
public static int[] insertionSort(int[] A, int n) {
    for (int i = 1; i < n; ++i) {
        int key = A[i];
        int j = i - 1;
        while (j >= 0 && A[j] > key) {
            A[j + 1] = A[j];
            j = j - 1;
        }
        A[j + 1] = key;
    }
    return A;
}
```
### Worst Case:    

## Big O
- while (j >= 0 && A[j] > key) {      // (1 + 2 + 3 + ... + N) times = n(n-1)/2 = n^2 - n

- F(n) = O(g(n)) if f(n) <= c*g(n) for n >= n0

- n^2 - n <= 2n^2 for n>=1

- C = 2 g(n) = n^2  

- Therefore, f(n) = O(n^2) 

## Big Omega
- while (j >= 0 && A[j] > key) {      // (1 + 2 + 3 + ... + N) times = n(n-1)/2 = n^2 - n

- F(n) = O(g(n)) if f(n) >= c*g(n) for n >= n0

- n^2 - n >= n^2 for n>=1

- C = 1 g(n) = n^2  

-Therefore, f(n) = Omega(n^2) 

## Big Theta
-since Big O and Big omega are equal big theta is Theta(n^2) for the worst and average cases
