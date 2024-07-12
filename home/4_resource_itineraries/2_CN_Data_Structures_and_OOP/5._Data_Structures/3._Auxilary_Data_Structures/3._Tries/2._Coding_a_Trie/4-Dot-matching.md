# 4. Dot matching
Created Fri Jul 12, 2024 at 12:27 PM

https://leetcode.com/problems/design-add-and-search-words-data-structure/

## Insight
Usually add and search in a trie can be done iteratively, but due to the "." character here, we can't know which node to choose so search will return true, so we check all, this requires "recursion".

```js
var WordDictionary = function() {
    this.root = { end: true };
};

/** 
 * @param {string} word
 * @return {void}
 */
WordDictionary.prototype.addWord = function(word) {
    let node = this.root;
    for(let i = 0; i < word.length; i++) {
        if (!node[word[i]]) node[word[i]] = {};
        node = node[word[i]];
    }
    node.end = true;
};

/** 
 * @param {string} word
 * @return {boolean}
 */
WordDictionary.prototype.search = function(word, start = 0, node = null) {
    if (node === null) node = this.root; // initial case

    if(!node) return false; // word > tree
    if (start === word.length) return !!node?.end; // tree > word

    // general case
    if (word[start] === '.') 
        return Object.keys(node).some(c => this.search(word, start + 1, node[c]));
    return !!node[word[start]] && this.search(word, start + 1, node[word[start]]);
};

/** 
 * Your WordDictionary object will be instantiated and called as such:
 * var obj = new WordDictionary()
 * obj.addWord(word)
 * var param_2 = obj.search(word)
 */
```
