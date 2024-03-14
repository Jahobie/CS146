# Validating a Binary Search Tree (BST)

## Problem Statement
Given the root of a binary tree, determine if it is a valid binary search tree (BST) with the following property:
- The left subtree of a node contains only nodes with keys less than the node's key.
- The right subtree of a node contains only nodes with keys greater than the node's key.
- This property should apply to all subtrees as well.

## Approach
To validate a binary tree as a BST, we can use a recursive approach:
1. Define a helper function that takes a node, along with a minimum and maximum value allowed for that node's subtree.
2. At each node, check if its value is within the valid range defined by the minimum and maximum values.
3. Recursively check the left and right subtrees, updating the valid range accordingly.

