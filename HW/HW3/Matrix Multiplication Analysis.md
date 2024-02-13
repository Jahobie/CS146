# Time Complexity Analysis

## Problem 2: Matrix Multiplication

### Algorithm Description
The MATRIX_MULTIPLY function takes two matrices, A and B, and returns their product if they are compatible for multiplication.

## Pseudocode

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
        sum ← sum + A[i][k] * B[k][j] // (N^2) times
      result[i][j] ← sum               // (N^2) times
  return result
```
F(N)=(N+1)+N+4N^2
The dominant term in this polynomial expression is 4N^2 therefore the time complexity for this matrix multiplication is quadratic.
