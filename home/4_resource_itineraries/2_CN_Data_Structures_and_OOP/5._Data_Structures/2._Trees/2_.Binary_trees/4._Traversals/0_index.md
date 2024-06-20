# 4. Traversals
Created Saturday 01 February 2020

1. PreOrder traversal: self, LeftSubtree, RightSubtree. Recursion.
2. InOrder traversal:  LeftSubTree, self,  RightSubtree. Recursion.
3. Postorder traversal: LeftSubtree, RightSubtree, self. Recursion.
4. LevelOrder traversal: use a queue.

[BinaryTreeNode.h](4._Traversals/BinaryTreeNode.h)
[treeMain.cpp](4._Traversals/treeMain.cpp)

## Level order traversal (per level)
This is a little diff then usual level order traversal. But still easy.

https://leetcode.com/problems/binary-tree-level-order-traversal

```cpp
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
 * @return {number[][]}
 */

/*

 Level order traversal with a twist. Instead of a linear array. The answer must be one array per level.

 Observe that all levels are handled consecutively (if seen from a complete program flow), this means we traverse through levels one by one.
 Simply said, we can go all serial, and we don't need any hashmaps or anything.

 But there's no obvious way to keep track of what level we are at, except at root.
 So lets change the queue structure to contain both node and level, instead of just node, this way, we know during enqueueing that the element we are pushing
 is a children, and is therefore at parent + 1 level.

 Note: some fuckup (reference/pointer ig) happened with the C++ solution (this is exactly that, but in JS)
 */
var levelOrder = function(root) {
    const bag = [];
    if(!root) return bag;

    const q = [ {node: root, level: 1} ];
    let qFrontIndex = 0;
    let currentBagLevel = 0;

    while(qFrontIndex < q.length) {
        const currentNode = q[qFrontIndex].node;
        const currentLevel = q[qFrontIndex].level;
        qFrontIndex++;

        if(currentLevel != currentBagLevel) {
            bag.push([]);
            currentBagLevel = currentLevel;
        }

        const currentLevelBag = bag.at(-1);
        currentLevelBag.push(currentNode.val);

        if (currentNode.left)  q.push({ node: currentNode.left, level: currentLevel + 1});
        if (currentNode.right) q.push({ node: currentNode.right, level: currentLevel + 1});
    }

    return bag;
};
```
