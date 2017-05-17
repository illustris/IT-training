# Dijkstra's algorithm
Used to find the shortest distance from one node to every other node in a graph with weighted edges. It makes use of a minheap.
Runtime: O(Vlog(E))

consider
```
A--3--C
|     |
2     4
|     |
D--1--E--5--B
```
A->0
C->3
D->2

Explore from D because D is closer
E->3

Next, explore from C (second closest to A)
xE->7 : rejected because a shorter path exists

Explore from E
B->8

# Evaluating trees
Consider these binary trees:
```
      +                +
     / \              / \
    /   \            /   \
   V     V          V     V
   -     C          C     -
  / \                    / \
 /   \                  /   \
V     V                V     V
A     B                A     B
```
They are identical if:
```
      R                S
     / \              / \
    /   \            /   \
   V     V          V     V
   T     U          V     W
  / \                    / \
 /   \                  /   \
V     V                V     V
W     X                Y     Z
```

```
R==S if
	T==V and U==W
	or
	T==W and U==V
	T!=V, so considering case 2
		U==V
		T==W if
			W==Y and X==Z (- isn't commutative)
```

# Passi's Practice Problems
1. The diameter of a tree is the largest distance in the tree. Write code to find the diameter of a tree in O(N)
2. In a rooted tree, find the Lowest Common Ancestor of two nodes
3. Find the centroid of a tree (if the tree is broken off at the centroid, subtrees won't have more than n/2 nodes)
4. Mass of a tree = sum of (weight of node * distance of node). Find an edge to split an unrooted tree into two rooted trees at, such that they have equal masses