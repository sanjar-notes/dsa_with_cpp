---
tags:
  - dsa-model
  - combinatorics
---
# 5. Modeling the Problem
Created Wed May 1, 2024 at 6:10 PM

## Modeling
Modeling is the art of formulating your application in terms of precisely described, well-understood (or already known) problems.

Proper modeling is the key to applying algorithmic design techniques to real-world problems. 

Indeed, proper modeling can eliminate the need to design or even implement algorithms, by relating your application to what has been done before.

Breakdown of problem into the language of existing algorithms literature is a must:
Problems you face have lot of context (network traffic, classroom schedules, pattern identification in large databases), but most algorithms (and libraries), however, are designed to work on rigorously defined abstract structures such as permutations, graphs, and sets. To exploit the algorithms literature, *you must learn to describe your problem abstractly, in terms of procedures on such fundamental structures.*

## Combinatorial objects
We are usually working on widgets (apps). But it's seldom easy to look for the exact solution in a cookbook for optimization problems, because widgets don't have cookbooks (since they have their own unique context).

But it's also true that almost any algorithm problem we are facing, has already been experienced by somebody else, perhaps in a very different context.

The solution is to formulate the widget optimization in terms of computing properties of common structures described below:
1. *Permutations* - orderings. Permutations are likely the object in question whenever your problem seeks an “arrangement,” “tour,” “order- ing,” or “sequence.”
2. *Subsets* - represent selections from a set of items. They are likely the object in question whenever your problem seeks a “cluster,” “collection,” “committee,” “group,” “packaging,” or “selection.”
3. *Trees* - are likely the object in question whenever your problem seeks a “hierarchy,” “dominance relationship,” “ancestor/descendant relationship,” or “taxonomy.”
4. *Graphs* represent relationships between arbitrary pairs of objects. Graphs are likely the object in question whenever you seek a “network,” “circuit,” “web,” or “relationship.”
5. *Points* define locations in some geometric space. Points are likely the object in question whenever your problems work on “sites,” “positions,” “data records,” or “locations.” For example, the locations of McDonald’s restaurants can be described by points on a map/plane. **Graph vs Points, is that geometry matters in points.**
6. Polygons define regions in some geometric spaces. For example, the borders of a country can be described by a polygon on a map/plane. Polygons and polyhedra are likely the object in question whenever you are working on “shapes,” “regions,” “configurations,” or “boundaries.” Points vs Polygons: points vs perimeter/area.
7. *Strings* represent sequences of characters, or patterns. Strings are likely the object in question whenever you are dealing with “text,” “characters,” “patterns,” or “labels.”

*These fundamental structures all have associated algorithm problems, which are presented in the catalog of Part II. Familiarity with these problems is important, because they provide the **language we use to model applications**.* To become fluent in this vocabulary, browse through the catalog and study the in- put and output pictures for each problem. **Understanding these problems, even at a cartoon/definition level**, will enable you to know where to look later when the problem arises in your application.

**Fundamental details of your problem** - The act of modeling breaks down your application to a small number of (simple) existing problems and structures. Such a process is inherently constraining, and certain details might seem to have gotten missed, but don’t be too quick to say that your problem is unique and special. Temporarily ignoring details that don’t fit can free the mind to ask whether they really were fundamental in the first place.


> [!NOTE] Take-Home Lesson:
> Modeling your application in terms of well-defined (and existing) structures and algorithms is the most important single step towards a solution.

## Recursive objects
*Learning to think recursively is learning to look for big things that are made from smaller things of exactly the same type as the big thing. If you think of houses as sets of rooms, then adding or deleting a room still leaves a house behind.*

- Recursive structures occur everywhere in the algorithmic world.
- Recursive descriptions of objects require both decomposition rules and basis cases, namely the specification of the smallest and simplest objects where the decomposition stops.
- The decision of whether the basis case contains zero or one element is more a question of taste and convenience than any fundamental principle. 🥹 (much needed clarification).