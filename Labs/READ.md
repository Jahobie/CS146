# Two Sum Problem

## Approach to Problem

The brute force solution for the Two Sum problem is far too inefficient. Instead, I took advantage of HashMap's fast data access to quickly store and retrieve elements that add up to the target.

With this data structure, instead of comparing each individual element with every other element in the array, I can just look into the map and see if the complement is present, and return the value, which in this case is the index.

### Code Explanation

The code provided implements the solution using Java. Here's a breakdown of the main steps:

1. Initialize a HashMap to store the elements and their indices.
2. Iterate through the array of numbers.
3. Calculate the complement for each number (target - current number).
4. Check if the complement exists in the HashMap. If it does, return the indices of the current number and its complement.
5. If the complement does not exist, add the current number and its index to the HashMap.


