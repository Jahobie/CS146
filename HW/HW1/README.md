# Palindrome Checker

## Problem Statement

Given a string `s`, determine if it is a palindrome, considering only alphanumeric characters and ignoring cases.

## Approach to Problem

To solve this problem, I implemented a Python class `Solution` with a method `isPalindrome`. Here's a breakdown of the approach:

1. Create a string `alphabet` containing all lowercase letters and digits.
2. Convert the input string `s` to lowercase using the `lower()` method.
3. Initialize two empty lists `forward` and `backward` to store the characters of `s` that are alphanumeric.
4. Iterate through the characters of `s`, and if a character is alphanumeric (i.e., it exists in `alphabet`), append it to the `forward` list.
5. Iterate through the characters of `s` in reverse order using `s[::-1]`, and if a character is alphanumeric, append it to the `backward` list.
6. Check if the `backward` list is equal to the `forward` list. If they are equal, return `True`, indicating that `s` is a palindrome. Otherwise, return `False`.

## Python Code Explanation

The provided Python code implements the solution to the problem. Here's a brief explanation of the code:

- The `isPalindrome` method takes a single parameter `s`, which is the input string to be checked for palindrome property.
- It initializes an `alphabet` string containing all lowercase letters and digits.
- The input string `s` is converted to lowercase using the `lower()` method.
- Two lists `forward` and `backward` are initialized to store alphanumeric characters of `s`.
- Characters of `s` are iterated through, and if a character is alphanumeric, it is appended to the `forward` list.
- Similarly, characters of `s` in reverse order are iterated through, and if a character is alphanumeric, it is appended to the `backward` list.
- Finally, the `backward` list is compared with the `forward` list. If they are equal, the method returns `True`, indicating `s` is a palindrome; otherwise, it returns `False`.

## Approach to Problem
-The Java solution is implemented in the `Solution` class with a method `isPalindrome`. Similar to the Python solution, it checks if the input string is a palindrome by considering only alphanumeric characters and ignoring cases. The implementation involves using two pointers (`start` and `last`) to iterate through the string and comparing characters from the beginning and end.

## Java Code Explanation

The provided Java code implements the solution to the problem. Here's a brief explanation of the code:

- The `isPalindrome` method takes a single parameter `s`, which is the input string to be checked for palindrome property.
- If the input string `s` is empty, the method returns `true`.
- Two pointers `start` and `last` are initialized to the beginning and end of the input string `s`.
- The method iterates through the string using the pointers `start` and `last`, comparing characters at each position.
- If the characters at the current positions are not alphanumeric, the pointers are adjusted accordingly.
- If the characters are alphanumeric and not equal (ignoring cases), the method returns `false`.
- If the characters are alphanumeric and equal (ignoring cases), the pointers are adjusted to continue the comparison.
- If the iteration completes without finding any non-matching characters, the method returns `true`, indicating `s` is a palindrome.
