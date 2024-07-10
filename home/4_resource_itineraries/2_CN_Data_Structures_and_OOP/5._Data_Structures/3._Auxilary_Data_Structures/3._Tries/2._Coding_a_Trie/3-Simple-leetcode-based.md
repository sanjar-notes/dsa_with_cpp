# 3. Simple leetcode based
Created Wed Jul 10, 2024 at 11:05 PM

## Note
- Recursion is needed only by `delete`. Other ops (add, search, startsWith) can be done iteratively (are tail recursions).
## Code
https://leetcode.com/problems/implement-trie-prefix-tree/
```js
/** 
 * Your Trie object will be instantiated and called as such:
 * var obj = new Trie()
 * obj.insert(word)
 * var param_2 = obj.search(word)
 * var param_3 = obj.startsWith(prefix)
 */

var Trie = function() {
    this.root = { end: true };
};

/** 
 * @param {string} word
 * @return {void}
 */
Trie.prototype.insert = function(word) {
    let node = this.root;
    for(let i = 0; i < word.length; i++) {
        if (!node[word[i]])
            node[word[i]] = {};
        node = node[word[i]];
    }
    node.end = true;
};

/** 
 * @param {string} word
 * @return {boolean}
 */
Trie.prototype.search = function(word) {
    let node = this.root;
    for(let i = 0; i < word.length; i++) {
        if (!node[word[i]])
            return false;
        
        node = node[word[i]];
    }
    return !!node.end;
};

/** 
 * @param {string} prefix
 * @return {boolean}
 */
Trie.prototype.startsWith = function(word) {
    let node = this.root;
    for(let i = 0; i < word.length; i++) {
        if (!node[word[i]])
            return false;
        
        node = node[word[i]];
    }
    return true;
};
```