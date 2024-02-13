## Problem 2: Matrix Multiplication

### Algorithm Description
The MATRIX_MULTIPLY function takes two matrices, A and B, and returns their product if they are compatible for multiplication.

### Time Complexity
- **Best Case:** O(n^2) - When the number of rows in A is equal to the number of columns in B.
- **Average Case:** O(n^3) - The nested loops iterate over the elements of A, B, and the result matrix, resulting in cubic time complexity.
- **Worst Case:** O(n^3) - Similarly, when the number of rows in A is equal to the number of columns in B, resulting in cubic time complexity.
