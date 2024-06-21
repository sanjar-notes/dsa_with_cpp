# 1. Pre and In
Created Saturday 01 February 2020

Pre has the first element as the root. **Root finder**
In has all left to the root as left subtree. **Space segregator.**

Are both needed, yes. Why?

1. Root finder helps find nodes.
2. Space segregator helps in giving them correct left and right subtrees.

1 and 2 are sufficient for making the tree.
Removing any of these, makes the construction impossible(due to muliple different having the same 1 or 2). 
Hence 1 and 2 are necessary.

Proof by contradiction.
Proved: 1 and 2 are necessary and sufficient for a unique tree, as each step of the recursion is unique for all trees, a yielding unique tree. 

// This is the best way, coz we get a node at each activation record. Which the best any algorithm can do. It has to be recursive as we need to work on more than one level.

**Caveat: No duplicate nodes should be present when using this method.**
 Code in exercise no.

## Code
Simpler explanation
https://leetcode.com/problems/construct-binary-tree-from-preorder-and-inorder-traversal/ (unique values assumed)
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
Approach.

Lets observe the given vectors.

preOrder = self left-st right-st
inOrder  = left-st self right-st

At the start, we know preOrder[0] is root, and also from pre what left and right subtrees are.
But do we?, no, we don't know length of left-st.
That we find by linear searching `self` in inOrder. i.e. we need in just for finding the length of left subtree.

Root is done. Lets see ahead.
We know that left nodes will be limited to within left-st. And same goes for right nodes for right-st.
This also means that only left-st and right-st portions will be relevant for each side, respectively.

Simply said, our search space is pretty cleanly divided, simple recursion should be enough. 
tip: We can use start, end to denote the portions, for both in and pre travs.

*/
class Solution {
public:
    TreeNode* helper(vector<int>& preorder, vector<int>& inorder, 
	    int pStart, int pEnd, 
	    int iStart, int iEnd) // exclusive ends
	{
        if(pStart == pEnd) return NULL; // didn't think much, it should be this

        int rootValue = preorder[pStart];
        TreeNode* root = new TreeNode(rootValue);

        int rootPositionInInorder;
        for(int i = iStart; i < iEnd; i++) {
            if (inorder[i] == rootValue) {
                rootPositionInInorder = i;
                break;
            }
        }

        root -> left = helper(preorder, inorder, 
                pStart + 1, pStart + 1 + (rootPositionInInorder - iStart), 
                iStart, rootPositionInInorder);

        root -> right = helper(preorder, inorder, 
                pStart + 1 + (rootPositionInInorder - iStart), pEnd, 
                rootPositionInInorder + 1, iEnd);

        return root;
    }
    
    TreeNode* buildTree(vector<int>& preorder, vector<int>& inorder) {
        return helper(preorder, inorder, 0, preorder.size(), 0, inorder.size());
    }
};
```