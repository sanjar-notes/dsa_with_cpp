# 4. Pre and post
Created Fri Jun 21, 2024 at 12:00 AM

## Code
Simple explanation

https://leetcode.com/problems/construct-binary-tree-from-preorder-and-postorder-traversal/ (unique values assumed)
Approach is similar to pre-order and in-order [variation](1._Pre_and_In/0_index.md#Code). Just side is changed.

```cpp
/**
 * Definition for a binary tree node.
 * struct TreeNode {
 *     int val;
 *     TreeNode *left;
 *     TreeNode *right;
 *     TreeNode() : val(0), left(nullptr), right(nullptr) {}
 *     TreeNode(int x) : val(x), left(nullptr), right(nullptr) {}
 *     TreeNode(int x, TreeNode *left, TreeNode *right) : val(x), left(left), right(right) {}
 * };
 */

 /*
 
 preOrder:  self left-st right-st
 postOrder: left-st right-st self

 We know the root from pre, pre[0]. What about length of left-st?
 Lets observe inside left-st. preOrder.leftSt.first will be same as postOrder.leftSt.last, 
 and since we're guaranteed node's are unique. 
 We can find length. Cool.

 */
class Solution {
public:
    TreeNode* helper(vector<int>& preorder, vector<int>& postorder, int prSt, int prEnd, int poSt, int poEnd) {
        if(prSt == prEnd) return NULL; // po and pr will end together, so check any

        int rootValue = preorder[prSt];
        TreeNode* root = new TreeNode(rootValue);

        int lengthOfLeftTree;
        if(prSt + 1 == prEnd) lengthOfLeftTree = 0;
        else {
            for(int i = poSt; i < poEnd; i++) {
                if (postorder[i] == preorder[prSt + 1])
                {
                    lengthOfLeftTree = i - poSt + 1;
                    break;
                }
            }
        }

        root -> left  = helper(preorder, postorder, 
            prSt + 1, prSt + 1 + lengthOfLeftTree, 
            poSt, poSt + lengthOfLeftTree);
            
        root -> right = helper(preorder, postorder, 
            prSt + 1 + lengthOfLeftTree, prEnd, 
            poSt + lengthOfLeftTree, poEnd - 1);

        return root;
    }

    TreeNode* constructFromPrePost(vector<int>& preorder, vector<int>& postorder) {
        return helper(preorder, postorder, 0, preorder.size(), 0, postorder.size());
    }
};
```
