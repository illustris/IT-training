# STL
## Vectors
`vector<int> v;`
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
`stack<int> s;`

```c++
for(int i=1;i<=10;i++)
	s.push(i);
cout<<s.size()<<endl;

int sum=0
while(!s.empty())
{
	sum+=s.top();
	s.pop();
}
```