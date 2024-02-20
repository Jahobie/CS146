## Problem 1:
### 1. 10000000000n^2 vs n^3
 - n^3 is aympyotically greater as it is O(n^3) VS O(n^2)

### 2. n2 log(n) vs n(log(n))^10
  - n^2log(n) is asympotically greater because it is O(n^2logn) vs O(nlogn)

### 3. n^logn vs 2^sqrt(N) 
 - n^logn  2^sqrt(n)
 - logn^logn log2^sqrt(n)
 - log^2n  sqrt(n)log2
 ## Therefore, n^logn is asymptotically greater than 2^sqrt(n) 


### 4. 2^n vs 2^2n

 - 2^2n is asymptotically greater as 2n > n 
 - however they are both O(n)



# Problem 2:
## Pseudocode for isPrime(n)

```python
isPrime(n):
    for i in range(2, int(n**0.5) + 1):
        if n % i == 0:
            return False
    return True
```

### 1. Best case O(1)
### 2. Worst Case O(sqrt(n))
### 3. Average Case O(n)
