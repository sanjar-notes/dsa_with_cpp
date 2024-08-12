# 4. Ordered partition problem
Created Fri Aug 9, 2024 at 12:26 AM

## Statement
Story - Suppose that three workers are given the task of scanning through a shelf of books in search of a given piece of information. And we don't want to rearrange the books (because we're lazing), so we can only choose 3 sectors. Q: how to divide the books into fairest 3 regions (i.e. the 3 regions have the same number of pages overall).

If all books are of the same length (pages), its trivial.
```sh
100 100 100 | 100 100 100 | 100 100 100
```

But what if books vary in size (pages). Simple 1/3 division won't work.
```sh
100 200 300 | 400 500 600 | 700 800 900
```

