# DSA
Representing a collection of interconnected nodes:
Consider
```
A----->B------C
      / \
     /   \
    /     \
   D-------E
```
## Adjacency list
```
A(B)
B(C,D,E)
C(B)
D(B,E)
E(D,B)
```
## Adjacency matrix
```
 
  A B C D E
 +-       -+
A|0 1      |
B|0 0      |
C|    0    |
D|      0  |
E|        0|
 +-       -+
```

## Tree
Conditions for a collection of connected nodes to be a tree:
1. nodes = edges + 1
2. there are no isolated groups of nodes

### Binary trees
1. Directed tree
2. Each node has 0, 1 or 2 children