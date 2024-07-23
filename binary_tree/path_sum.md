## Task ✍
Given the root of a binary tree and an integer targetSum, return true if the tree has a root-to-leaf path such that adding up all the values along the path equals targetSum.

A leaf is a node with no children.

#### Example 1:
Input: ```root = [5,4,8,11,null,13,4,7,2,null,null,null,1], targetSum = 22```

Output: ```true```

Explanation: The root-to-leaf path with the target sum is shown.

#### Example 2:
Input: ```root = [1,2,3], targetSum = 5```

Output: ```false```

Explanation: There two root-to-leaf paths in the tree:

(1 --> 2): The sum is 3.

(1 --> 3): The sum is 4.

There is no root-to-leaf path with sum = 5.

#### Example 3:
Input: ```root = [], targetSum = 0```

Output: ```false```

Explanation: Since the tree is empty, there are no root-to-leaf paths.

## Intuition 💬
<!-- Describe your first thoughts on how to solve this problem. -->
My initial thoughts on solving this problem was to traverse through the binary tree whilst keeping track of the targetSum and to check if that had been met at a leaf or not.

This is the approach I took to creating my solution.

## Approach 💡
<!-- Describe your approach to solving the problem. -->
1. I used an if statement for a base case that checked that if the node tree was empty
2. If so, return false
3. An else if statement checked if we had reached a leaf by checking that the left and right nodes were null and targetSum minus the value of the current node was equal to 0
4. If so, then return true
5. Else, return the method using the left node and the value of the targetSum minus the value of the current node as the parameters or, the right node and the value of the targetSum minus the value of the current node as the parameters 

## Code 📝
My solution to the task.
```java
/**
 * Definition for a binary tree node.
 * public class TreeNode {
 *     int val;
 *     TreeNode left;
 *     TreeNode right;
 *     TreeNode() {}
 *     TreeNode(int val) { this.val = val; }
 *     TreeNode(int val, TreeNode left, TreeNode right) {
 *         this.val = val;
 *         this.left = left;
 *         this.right = right;
 *     }
 * }
 */
class Solution {
    public boolean hasPathSum(TreeNode root, int targetSum) {
        
        if(root == null){
            return false;
        }
        else if(root.left == null && root.right == null && targetSum - root.val == 0){
            return true;
        }
        else{
            return hasPathSum(root.left, targetSum - root.val) || hasPathSum(root.right, targetSum - root.val);
        }
    }
}
```
