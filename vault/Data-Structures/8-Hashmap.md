# 8. Hashmap
Created Mon Jul 15, 2024 at 10:27 PM

- [Hashmap implementation and collision mitigation](../../home/4_resource_itineraries/2_CN_Data_Structures_and_OOP/5._Data_Structures/3._Auxilary_Data_Structures/2._Hashmaps/0_index.md)

Hashmap common uses
1. Duplicate detection. Examples:
	- Unique check. Hash the objects. **Example**: Check if a document is unique in a large corpus of documents? Create a hash for each, and then compare. Much faster than word-by-word search. Do word-by-word only for matching hash docs.
	- Is a document partially plagiarized? A lazy student copies a portion of a web document into their term paper. “The web is a big place,” he smirks.“. How will anyone ever find the page I stole this from?”. **Example** Decide a length `w` and find out hashes for substrings of length. Do the same for potential sources. Better than word by word. The key here is to choose the smallest set of most likely sources.
	- How can I convince you that a file hasn't changed? Digest the data. **Example**: This is an important thing, like a closed-bid auction. If people submit real bids, and the data is compromised, the cracker would just bid 1$ above. Instead people submit the hash of their bid. And they all disclose real numbers together. This way, nobody can snoop.
2. Canonicalization - reducing complicated objects to a standard (i.e. “canonical”) form. String transformations like reducing letters to lower case or stemming (removing word suffixes like -ed, -s, or -ing) result in increased matches, because multiple strings collide on the same code. **Example**: given a set of selected alphabets, how many dictionary word can be formed by the permutations. Instead of scanning the dictionary, one can sort all dictionary words and hash them, this reduces the search space (creates bucket of multiple candidates). Finally do the one by one matching. much easier. there's a sound based schema called "Soundex" which does this.
3. Compaction. Represent large objects by a small part of them (these are hashable), and work on these hashes. Usually the small hashes preserve identity (i.e. the relation) to the original object. Example: sort all books in a library by their text content. Just pick first 100 words, and sort them. if collisions remain, increase the word limit. This way, we didn't need to sort 100k words per book among the library.

Controlled many - Hash functions provide useful tools for many things beyond powering hash tables. The fundamental idea is of *many-to-one* mappings, where *many* is controlled so it is very unlikely to be too *many*.