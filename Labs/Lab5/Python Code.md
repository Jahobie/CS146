```Python
def isValidBST(self, root):
        return self.is_valid_bst(root, float('-inf'), float('inf'))
    
    def is_valid_bst(self, node, min_val, max_val):
        if not node:
            return True
        
        if node.val <= min_val or node.val >= max_val:
            return False
        
        return (self.is_valid_bst(node.left, min_val, node.val) and 
                self.is_valid_bst(node.right, node.val, max_val))
```
