# 2. --Coding BST  - BST Node class
Created Sunday 09 February 2020


* We will store a tree in a class;

We need the following data members:

1. Root of the BST


We also need the following member functions:

1. bool hasData(int data)
2. void insertData(int data)
3. BST data(int data).


1. bool hasData(int data) - Here we need to search for the data, but how do we indicate our root, this we do by making a function with the same name, i.e overloading it with the root address
2. void insertData(int data) - Again we make a helper function in private, we insert nodes only as leaves, so no worries about changing the root.
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
	 * @param {number} val
	 * @return {TreeNode}
	 */
	 // Approach: Tree abstraction, have to go left or right, and can always go. Will reach an empty place for sure.
	 // It's kind of difficult to visualize and one may doubt they are missing "add new between" case, but it's fine.
	 // global variables dir, prevNode
	var insertIntoBST = function(root, val, dir = 0, prevNode = null) {
	    if (!root) {
	        const newNode = new TreeNode();
	        newNode.val = val;
	
	        if (!prevNode) return newNode; // empty tree
	
	        if (dir === -1) {
	            prevNode.left = newNode;
	        } else {
	            prevNode.right = newNode;
	        }
	        return;
	    }
	
	    const currentDir = val < root.val ? -1 : 1;
	    insertIntoBST(currentDir === -1 ? root.left : root.right, val, currentDir, root);
	
	    return root;
	}; 
	```

*****


3. deleteData(int data)

Again, here we have 4 scenarios:

1. We have root as NULL, do nothing. Return the root, as it is. 
2. We have a leaf which needs to be deleted. Delete it, return NULL. 
3. We have a non lead node to be deleted, two different solutions are possible
	1. Find the node with the largest value in the left subtree. Replace the root with the obtained max value. Call delete(max, root->left);
	2. Find the node with the smallest value in the right subtree. Replace the root with the obtained min value. Call  
4. If data < root->data, do root->left = deleteData(data, root->left)
5. If data < root->data, do root->right = deleteData(data, root->right). Return root;

T.C = O(h)
Doubt: Delete data works for the case of non leaf as well because we are always keeping the property of BST intact. 

*****

![./BinaryTreeNode.h](2._Coding_BST__-_BST_Node_class/BinaryTreeNode.h)

