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

