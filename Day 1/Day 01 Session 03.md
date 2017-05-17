# STL
## Vectors
```c++
#include <iostream>
#include <vector>

using namespace std;

int main()
{
	vector<int> v;
	v.push_back(100);
	v.push_back(200);
	cout<<v.size()<<endl;

	v.push_back(1100);
	cout<<v[0]<<endl;
	v.clear();

	v.push_back(1);
	v.push_back(2);
	v.push_back(3);
	v.push_back(4);

	cout<<v.front()<<endl;
	cout<<v.back()<<endl;
	v.pop_back();
	cout<<v.back()<<endl;
	cout<<v.at(0)<<endl;
}
```

### Iterators
iterate through vectors using pointers
```c++
vector<int>::iterator it;
for(it=v.begin();it!=v.end();++it)
	cout<<*it<<endl;
```

### Misc. functions of vectors
`v.empty()`

returns true if vector is empty

`v.resize(size_t)`

resize vector

## Stacks
```c++
#include <iostream>
#include <stack>
using namespace std;
int main()
{
	stack<int> s;
	for(int i=1;i<=10;i++)
		s.push(i);
	cout<<"size: "<<s.size()<<endl;
	int sum=0;
	while(!s.empty())
	{
		sum+=s.top();
		cout<<s.top()<<" ";
		s.pop();
	}
	cout<<"\nsum: "<<sum<<endl;
}
```

## Queue
Works like a FIFO
```c++
#include <iostream>
#include <queue>
using namespace std;
int main()
{
	queue<int> q;
	for(int i=1;i<=10;i++)
	{
		cout<<"Pushing "<<i<<" into queue\n";
		q.push(i);
	}
	cout<<"Size: "<<q.size()<<endl;
	cout<<"Back of queue: "<<q.back()<<endl;
	while(!q.empty())
	{
		cout<<"Front: "<<q.front()<<endl;
		q.pop();
	}
}
```

## Pairs
Singular entity with two elements
```c++
#include <iostream>
#include <utility>

using namespace std;

int main()
{
	pair<int,int> p;
	p=make_pair(10,20);
	cout<<p.first<<" "<<p.second<<endl;
}
```

## Maps
Associative containers that store elements formed by a key and mapped value

```c++
#include <iostream>
#include <map>

using namespace std;

int main()
{
	map<char,int> m;
	m.insert(pair<char,int>('a',100));
	m.insert(pair<char,int>('z',100));
	m['d']=120;
	cout<<m['a']<<" "<<m.at('d')<<endl;
}
```

## Set
Containers that sort and store unique elements.
```c++
#include <iostream>
#include <set>

using namespace std;

int main()
{
	set<int> s;
	s.clear();
	s.insert(10);
	s.insert(20);
	s.insert(30);
	cout<<s.size()<<endl;
	s.insert(20);
	cout<<s.size()<<endl;
	s.erase(20);
	cout<<s.size()<<endl;
}
```