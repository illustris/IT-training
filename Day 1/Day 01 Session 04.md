# DSA
## Graphs
Representing a collection of interconnected nodes:
Consider
```
A----->B------C
      / \
     /   \
    /     \
   D-------E
```
### Adjacency list
```
A(B)
B(C,D,E)
C(B)
D(B,E)
E(D,B)
```
### Adjacency matrix
```
 
  A B C D E
 +-       -+
A|0 1 0 0 0|
B|0 0 1 1 1|
C|0 1 0 0 0|
D|0 1 0 0 1|
E|0 1 0 0 0|
 +-       -+
```

### Tree
Conditions for a collection of connected nodes to be a tree:
1. Vertices = Edges + 1
2. there are no isolated groups of nodes

#### Binary trees ####
1. Directed tree
2. Each node has 0, 1 or 2 children

### Searching and traversing graphs
DFS and BFS are O(Edges+Vertices)
*[DFS]: Depth First Search
*[BFS]: Breadth First Search
#### DFS ####
Keep traversing a branch till the destination is reached, there is nowhere further to go or a previously traversed node is reached again. On reaching the end, go up one level and try another branch
```
Example: Reach E feom A
A->B->C
   |
   -->D->E *
```
#### BFS ####
Check nodes at a distance N from current node iteratively
```
Example: Reach E feom A

1. A->B

2. A->B->C
   A->B->D
   A->B->E *
```

#### Graph code example ####

```c++
#include <bits/stdc++.h>
using namespace std;
vector<int> graph[100];
int visited[100];

void dfs(int current)
{
	if(visited[current])
		return;
	visited[current]=1;
	cout<<x<<endl;
	for(auto x: graph[current]) //iterate over all elements of vector "graph[current]"
	{							//not over elements of array "graph"
		dfs(x);
	}
}

int main()
{
	int N, E;
	cin>>N>>E;
	for(int i=1;i<=N;i++)
	{
		graph[i].clear();
		visited[i]=0;
	}
	for(int i=1;i<=E;i++)
	{
		int u,v;
		cin>>u>>v
		graph[u].push_back(u);
		graph[u].push_back(v);
	}
	dfs(5);
}

```
input:
```
5 6
2 3
3 1
3 5
5 4
4 1
1 2
```
graph:
```
5-----4
|     |
|     |
3-----1
 \   /
  \ /
   2
```
Followed path:
```
1->3->2
|  |
|  -->5
-->4
```

#### Example problem ####
Consider
```
R--R--B  R
|  |     |
R  B--R  B--R
      |  |
      B--R
```
Find number of pairs of red nodes with ar least one blue node in the path between them

Solution 1:
1. Start at a red node
2. DFS till a blue node is reached. Mark all red nodes till then as done
3. Find number of red nodes beyond that red node
4. total += red bunch size * number of red beyond the blue node
5. Repeat for other red nodes not belonging to the bunch

#### Example problem ####
Solution 2: connected component approach
```c++
int dfs(int current)
{
	if(visited[current] || color[current]=='B')
		return 0;
	visited[current]=1;
	int ret = 1
	for(auto x: graph[current]) //iterate over all elements of vector "graph[current]"
	{							//not over elements of array "graph"
		ret+=dfs(x);
	}
	return ret
}

int main()
{
	int N, E;
	cin>>N>>E;
	for(int i=1;i<=N;i++)
	{
		graph[i].clear();
		visited[i]=0;
		cin>>color[i];
	}
	for(int i=1;i<=E;i++)
	{
		int u,v;
		cin>>u>>v
		graph[u].push_back(v);
		graph[v].push_back(u);
	}
	for(i=1;i<=Ni++)
	{
		if(color[i]=='R' && !visited[i] )
		{
			comps.push_back(dfs(i));
		}
	}
	int total=0;
	for(i=0;i<comps.size())
	{
		total+=comps[i];
	}
	for(i=0;i<comps.size();i++)
	{
		ans=comps[i]*(total-comps[i]);
	}
	cout<<ans/2<<endl;

}
```