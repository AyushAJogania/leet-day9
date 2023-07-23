# leet-day9

## Same Tree

### Problem Description

You are given the root nodes of two binary trees, `p` and `q`. You need to determine whether the two trees are identical or not.

Two binary trees are considered the same if they have the same structure and the same node values at each corresponding position.

### Example

#### Input

```cpp
TreeNode* p = new TreeNode(1);
p->left = new TreeNode(2);
p->right = new TreeNode(3);

TreeNode* q = new TreeNode(1);
q->left = new TreeNode(2);
q->right = new TreeNode(3);
```

#### Output

```
true
```

### Approach

To check if two binary trees are identical, we can use a recursive approach. We start by checking if both trees are empty, in which case they are considered the same. Next, we check if either of the trees is empty while the other is not, in which case they are not the same. If both trees are non-empty, we compare the values of the current nodes. If they are different, the trees are not the same. Otherwise, we recursively check the left and right subtrees.

### Complexity Analysis

- Time complexity: O(N), where N is the number of nodes in the larger of the two trees.
- Space complexity: O(H), where H is the height of the larger of the two trees (due to the recursive call stack).

### Implementation

The `Solution` class contains a `isSameTree` function that takes two `TreeNode` pointers as input and returns a boolean indicating whether the two trees are the same or not.

