

# Lowest Common Ancestor in Binary Search Tree (BST)

## Problem Statement

Given a binary search tree (BST), find the lowest common ancestor (LCA) node of two given nodes `p` and `q` in the BST.

The lowest common ancestor is defined between two nodes `p` and `q` as the lowest node in the tree that has both `p` and `q` as descendants (where we allow a node to be a descendant of itself).

## Approach

To find the lowest common ancestor (LCA) of two nodes `p` and `q` in a binary search tree (BST), we can follow these steps:

1. Start from the root node of the BST.
2. Traverse down the tree.
3. If both nodes `p` and `q` are greater than the current node, move to the right subtree.
4. If both nodes `p` and `q` are less than the current node, move to the left subtree.
5. If one node is on the left subtree and the other is on the right subtree, then the current node is the LCA.
6. Otherwise, continue traversing until the LCA is found.

