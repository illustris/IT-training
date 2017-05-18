# Pattu's Practice Problems

## Implement a stack using 2 queues

```c++
#include <iostream>
#include <queue>
using namespace std;

class stack
{
	queue<int> q;
	queue<int> b;
public:
	void push(int a)
	{
		while(!q.empty())
		{
			b.push(q.front());
			q.pop();
		}
		q.push(a);
		while(!b.empty())
		{
			q.push(b.front());
			b.pop();
		}
	}
	void pop()
	{
		q.pop();
	}
	int top()
	{
		return q.front();
	}
	int size()
	{
		return q.size();
	}
	bool empty()
	{
		return q.empty();
	}
}s1;

int main()
{
	for(int i=1;i<=10;i++)
	{
		cout<<"Pushing "<<i<<" into stack\n";
		s1.push(i);
	}

	cout<<"Size: "<<s1.size()<<endl;
	while(!s1.empty())
	{
		cout<<"Popping "<<s1.top()<<endl;
		s1.pop();
	}
}
```

## Design a stack that can retrieve min element in O(1)