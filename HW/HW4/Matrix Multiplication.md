## Problem 2: Matrix Multiplication

### Algorithm Description
The MATRIX_MULTIPLY function takes two matrices, A and B, and returns their product if they are compatible for multiplication.

### Time Complexity
- **Best Case:** O(n^2) - When the number of rows in A is equal to the number of columns in B.
- **Average Case:** O(n^3) - The nested loops iterate over the elements of A, B, and the result matrix, resulting in cubic time complexity.
- **Worst Case:** O(n^3) - Similarly, when the number of rows in A is equal to the number of columns in B, resulting in cubic time complexity.

```java
MATRIX_MULTIPLY(A, B):
  if columns(A) ≠ rows(B): 
    raise ValueError("Matrix multiplication is not defined.") 

  rows_A ← number of rows in A 
  cols_A ← number of columns in A 
  cols_B ← number of columns in B 
  result ← matrix of size rows_A x cols_B filled with zeros 

  for i from 1 to rows_A do:            // (N + 1) times
    for j from 1 to cols_B do:         // (N) times
      sum ← 0                          // (N^2) times
      for k from 1 to cols_A do:      // (N^2) times
        sum ← sum + A[i][k] * B[k][j] // (N^3) times
      result[i][j] ← sum               // (N^3) times
  return result
```


### Big O
F(N)=2N^3 + 2N^2 +2n +1

F(n) = O(g(n)) if f(n) <= c*g(n) for n>= n0

2n^3 + 2n^2  +2n+ 1 <=  7n^3 for n >= 1

C = 7 g(n) = n^3 therefore,

f(n) = O(n^3)

### Big Omega
F(N)=2N^3 + 2N^2 +2n +1
F(n) = O(g(n)) if f(n) >= c*g(n) for n>= n0

2n^3 + 2n^2  +2n+ 1 >=  n^3 for n >= 1

C = 1 g(n) = n^3 therefore,

f(n) = O(n^3)

### Big Theta

Since Big O and Big Omega are equal Big theta is Theta(n^3)
