# 4. Check if CBT
Created Tue Jul 9, 2024 at 12:04 AM

## Simple and best solution
Level order traversal based. We use level-order movement's and do a serial check.
The check is that once we find node without both children (i.e. we are on second last node most probably), then all further nodes must have no children. If it was a full binary tree, this would still hold.

In this method, there's no need to consider height or level.
```js
/**
 * Definition for a binary tree node.
 * function TreeNode(val, left, right) {
 *     this.val = (val===undefined ? 0 : val)
 *     this.left = (left===undefined ? null : left)
 *     this.right = (right===undefined ? null : right)
 * }
 */
/**
 * @param {TreeNode} root
 * @return {boolean}
 */
var isCompleteTree = function(root) {
    if (!root) return true;
    
    const q = [root];
    let qIndex = 0;
    let incompleteNodeSeen = false;
    while(qIndex < q.length) {
        const currentNode = q[qIndex];
        if (!currentNode.left && currentNode.right) return false; // first end is itself a problem

        const numberOfChildren = +(!!currentNode.left) + +(!!currentNode.right);
        if (incompleteNodeSeen && numberOfChildren > 0) return false;
    
        if (numberOfChildren < 2 && !endSeen)
            incompleteNodeSeen = true;
        
        if (currentNode.left ) q.push(currentNode.left);
        if (currentNode.right) q.push(currentNode.right);
        qIndex++;
    }

    return true;
};
```

## The harder solution (seemingly efficient)
No need for this, as its worst is the same as level order traversal.
https://leetcode.com/problems/check-completeness-of-a-binary-tree/
```js
/**
 * Definition for a binary tree node.
 * function TreeNode(val, left, right) {
 *     this.val = (val===undefined ? 0 : val)
 *     this.left = (left===undefined ? null : left)
 *     this.right = (right===undefined ? null : right)
 * }
 */
/**
 * @param {TreeNode} root
 * @return {boolean}
 */
function helper(root, state, h, parent) {
    const { maxH, prevH, isSeenLeaf, isComplete } = state;
    if (!root) {
        if(h === state.maxH) {
            state.isComplete = true; // hole detect
        };

        if (state.maxH - h >= 1) return false;
        return true;
    };

    const isLeaf = root && !root.left && !root.right;
    if (isLeaf) {
        if (state.isComplete && h === state.maxH) { return false; } // a leaf after a hole is a problem

        const globalDelta = state.maxH - h;
        const prevDelta = state.prevH - h;
        state.maxH = (h > state.maxH) ? h : state.maxH;
        state.prevH = h;
        return (globalDelta <= 1 && globalDelta >=0) && (prevDelta <= 1 && prevDelta >=0);
    }
    else {
        return helper(root.left, state, h + 1, root) && helper(root.right, state, h + 1, root);
    }
}

var isCompleteTree = function(root) {
    // consider only leaf nodes
    // we'll do in-order traversal
    // we'll maintain height
    // so for each node, prevHeight - currentHeight <= 1
    // and only one diff point should come
    // and max delta (max - min) should be 1
    // for balanced trees - O(n) time, O(lgn) space
    // for skewed trees - O(n) time, O(n) space

    // worst O(n) time O(n) space

    let maxH = 0;
    let prevH = 0;
    let isSeenLeaf = false;
    let isComplete = false;

    let state = { maxH, prevH, isSeenLeaf, isComplete};

    let trav = root;
    while(trav) {
        state.maxH+=1;
        trav = trav.left;
    }
    state.prevH = state.maxH;
    const answer = helper(root, state, 1);
    return answer;
};
```

