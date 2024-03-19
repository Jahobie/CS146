# Level-Order Traversal of a Binary Tree

## Approach

The level-order traversal of a binary tree involves visiting all nodes of the tree level by level, starting from the root node. It explores the tree breadth-first, visiting nodes at each level before moving to the next level.

### Algorithm

1. Initialize an empty list `result` to store the traversal result.
2. Create an empty queue to store nodes.
3. Enqueue the root node into the queue.
4. While the queue is not empty:
   - Get the current size of the queue (`levelSize`) to determine the number of nodes at the current level.
   - Create an empty list `currentLevel` to store values of nodes at the current level.
   - Iterate `levelSize` times:
     - Dequeue a node from the front of the queue.
     - Add the value of the dequeued node to `currentLevel`.
     - Enqueue the left child and right child of the dequeued node if they exist.
   - Add `currentLevel` to the `result`.
5. Return the `result` containing the level-order traversal of the binary tree.





