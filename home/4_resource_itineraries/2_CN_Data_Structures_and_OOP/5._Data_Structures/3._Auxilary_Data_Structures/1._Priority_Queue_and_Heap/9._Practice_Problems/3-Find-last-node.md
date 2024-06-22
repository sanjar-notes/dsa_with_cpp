# 3. Find last node
Created Fri Jun 21, 2024 at 10:11 PM

## Code
https://leetcode.com/problems/count-complete-tree-nodes/

This problem has 3 things:
1. Finding last node in CBT - yes it's possible (in pure tree structure). O(lgn * lgn) time where n = number of nodes
2. Path based counting in CBT

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
 Time complexity should be less than O(n), that means normal counting or traversals are not allowed.

 A. Suppose we knew the lastNode, and to reach this we followed some path, i.e. sequence of L or R. Then we could use this path to know count.
 Would it work? yes, it would, suppose the tree was complete, and we did all rightward movements, then path would be RRRRR... and count will be 2^h + 1 nodes.
 Lets see root node, the path is empty, and node count is 1. Another fact is that the max nodes is RRR..., and all other combinations "have to be" covered in some node.
 So L and R being 0/1 (or 1/0) should be good.

 Exact scheme is L = 0, R = 1 and we prepend a 1 and get a binary number. So if its a 3 node tree, and we do 'R' then the path is 1R => 11 => 3 correct. 
    left node => 'L' => 1L => 10 => 2
    Root node => '' => 1 => 1 (count)


 Okay, so if we know path we can count.

 But how do we know the last node (and therefore the path)?

 B. Find last node
 This is tricky, since even if we enumerate the last level node (level order traversal itself would be O(n)), then also the last level will be approx n/2 => O(n).
 
 Lets see another way. Suppose the CBT is a complete tree and one last level. When seen from the root, the lastNode will be either in the left or right subtree.
 We need to make a decision which direction to go, if leftStHeight > rightStHeight, then we go left (for sure lastNode is there). Else (eq) we go right (lastNode probably there).
    This worked at root level, but would it work in inner subtrees? See we go left once. Then we again have two choices, and one of them is right. This will do on any subtree. So we're good.

    But need to find max height (aka just height) of subtrees in less than O(n) time. 
    Lets see, at the root level, going just left as much as possible will give us max height. Same goes for right subtree.
    Lets check if this would work at an inner subtree? See, we go left once. Then we again have two choices, and we still can definitely do left-all, and we'd be good.

  Okay height calc is Ok, we can now find the last node.


  C. Path
  Once we know the node, we might have traversed LR... something correctly. Why am I saying this? coz knowing address (pointer) to lastNode is still useless to us, 
    since we can't reach there just knowing address. So we need to store traversed path while we are doing find-last-node itself.
*/

class Solution {
public:
    int getMaxHeight(TreeNode* root) {
        if(!root) return 0;

        return 1 + getMaxHeight(root -> left);
    }

    void buildLastNodePath(TreeNode* root, vector<int> &path) {
        if(!root) return;

        int leftHeight  = getMaxHeight(root -> left);
        int rightHeight = getMaxHeight(root -> right);

        if (leftHeight > rightHeight) {
            if(root -> left)
            {
                path.push_back(0);
                buildLastNodePath(root -> left, path);
            }
        }
        else {
            if (root -> right)
            {
                path.push_back(1);
                buildLastNodePath(root -> right, path);
            }
        }
    }

    int countNodes(TreeNode* root) {
        if (!root) return 0;

        vector<int> path {1};
        buildLastNodePath(root, path); // populate path

		// binary to decimal conversion
        int count = 0;
        int multiplier = 1;
        for(int i = path.size() - 1; i >= 0; i--) {
            count += path[i] * multiplier;
            multiplier *=2;
        }

        return count;
    }
};
```