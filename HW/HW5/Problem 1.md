# Problem 1


		


# 1. T(N) = 2T(N-1) + 1
-  Recursion Tree Method:
  -  T(n) →  1
 - 1 T(n-1) → 1 T(n-1) →    2 2^1
 - 1 T(n-2) → 1 T(n-2) →  1 T(n-2) → 1 T(n-2) → 4 2^2
 - 1 T(n-3) → 1 T(n-3) →  1 T(n-3) → 1 T(n-3) → 1 T(n-3) → 1 T(n-3) →  1 T(n-3) → 1 T(n-3) 8 2^3

-  1 +2 + 2^2 + 2^3 + ….. +2^k = 2^k+1 -1


-  N-k = 0 assume n = k 
-  = 2^n+1 -1 
##  = O(2^n)



# 2. T(N) = 3T(N-1) + n

-  Recursion Tree Method:
-  T(n)  3^0
 - T(n-1) T(n-1) T(n-1) 3^1 
 -  T(n-2)  T(n-2)  T(n-2)  T(n-2)  T(n-2)    T(n-2)  T(n-2)  T(n-2)  T(n-2) 3^3 

-  = 3^k+1 -1
## = O(3^n)



# 3. T(N) = 9T(N/2) + n^2

-  Master Method -
-  T(n) = aT(n/b) + f(n)  
-  f(n) = O(n^k log^p(n)) 
-   Case 1: f(n) = O(nlogb(a)-e) where e>0 then T(n) = Θ(n^logb(a)
-  Case 2: f(n) = Θ(nlogb(a)logkn) where k>=0 then T(n) = Θ(n^logb(a)log^k+1(n))
-  Case 3: f(n) = Ω(n^logb(a)+e) where e>0 then T(n) = Θ(f(n))

 - a = 9 b = 2  f(n) = n^2
-  n^log(2)(9) ~ 3.17 > n^2
## Therefore, Case 3: T(n)  = Θ(n^2)






###4. T(N) = 100T(N/2) + nlog2cn + 1  (c is a constant)
-  a = 100 b = 2 f(n) = n^log2(cn+1) 
-  n^log(2)(100) ~ 6.64  
 - = n^6.64  < n^log2cn +1 for c > 100
 ## Therefore,  case 1: T(n) = n^log(2)(100)


# 5. T(N) = 4T(N/2) + n2/logn
-  a = 4 b = 2 f(n) = n^2/logn
-  n^ log(2)(4) = n^2
 - n^2 > n^2/logn 
## Therefore, Case 3: T(n) = Θ(n^2/logn)







# 6. T(N) = 5T(N/2) + n2/logn
  a = 4 b = 2 f(n) = n^2/logn
  n^ log(2)(5) = n^2.3
  n^2.3 > n^2/logn 
## Therefore, Case 3:  T(n) = Θ(n^2/logn)


# Problem 2

# Pseudocode for yetAnotherFunc(n)

```java
yetAnotherFunc(n):
    if n > 1:    //Base Case
        for( i = 0 i<10n; i++)  // itereates 10n times 
            doSomething   // runs everytime in loop
        yetAnotherFunc(n / 2);   // recursive call with n/2 as arugment
        yetAnotherFunc(n / 2); // ran twice so 2T(n/2)
```

### Recurrence Relation
{ 1
  2T(n/2) + 10n )
  
if n≤1
if n>1
​

## Master Method:
- a = 2 b = 2 f(n) = n
- n^log(2)(2) = 1
- 1 < n
## Therefore,, Case 3: T(n) = Θ(n)



