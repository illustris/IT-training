# Strongly connected graphs
There is a path from one node to any other node in a strongly connected graph
```
1-->2    ->5
^  / \  /  |
| V  V /   V
--3->4<----6
     ^     |
     |     V
     ------7
```
1,2,3 are strongly connected
4,5,6,7 is strongly connected

## Kosaraju algorithm
```
1. For each vertex u of the graph, mark u as unvisited. Let L be empty.
2. For each vertex u of the graph do Visit(u), where Visit(u) is the recursive subroutine:
	If u is unvisited then:
		1. Mark u as visited.
		2. For each out-neighbour v of u, do Visit(v).
		3. Prepend u to L.
	Otherwise do nothing.#
3. For each element u of L in order, do Assign(u,u) where Assign(u,root) is the recursive subroutine:
	If u has not been assigned to a component then:
		1. Assign u as belonging to the component whose root is root.
		2. For each in-neighbour v of u, do Assign(v,root).
	Otherwise do nothing.
```