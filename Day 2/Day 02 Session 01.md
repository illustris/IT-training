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

```c++
#include <iostream>
#include <stack>
using namespace std;

class minStack
{
	stack<int> s;
	stack<int> m;
public:
	void push(int a)
	{
		if(s.empty() || a<m.top())
			m.push(a);
		else
		{
			m.push(m.top());
		}
		s.push(a);
	}
	void pop()
	{
		s.pop();
		m.pop();
	}
	int top()
	{
		return s.top();
	}
	int min()
	{
		return m.top();
	}
	int size()
	{
		return s.size();
	}
	bool empty()
	{
		return s.empty();
	}
}s1;

int main()
{
	for(int i=10;i>=1;i--)
	{
		s1.push(i);
		cout<<"Pushing "<<i<<" into stack. Min: "<<s1.min()<<endl<<flush;
	}

	for(int i=1;i<=10;i++)
	{
		s1.push(i);
		cout<<"Pushing "<<i<<" into stack. Min: "<<s1.min()<<endl<<flush;
	}

	cout<<"Size: "<<s1.size()<<endl;
	while(!s1.empty())
	{
		cout<<"Current min: "<<s1.min()<<". Popping "<<s1.top()<<endl;
		s1.pop();
	}
}
```

## Evaluate arithmetic expression in Reverse Polish Notation

```c++
#include <iostream>
#include <vector>
#include <stack>
using namespace std;

double evaluateRP(vector<string> in)
{
	stack<double> s;
	double x,y,z;
	while(!in.empty())
	{
		try
		{
			z=stof(in[0]);
			s.push(z);
		}
		catch(...)
		{
			x=s.top();
			s.pop();
			y=s.top();
			s.pop();
			if(in[0]=="+")
				z=y+x;
			else if(in[0]=="-")
				z=y-x;
			else if(in[0]=="*")
				z=y*x;
			else if(in[0]=="/")
				z=y/x;
			s.push(z);
		}
		in.erase(in.begin());
	}
	return(s.top());
}

int main()
{
	vector<string> in = {"4","13","5","/","+"};
	cout<<evaluateRP(in)<<endl;
}
```

## Given an array, find the nearest smaller element for every element with a smaller index

```c++
Someone do and send a pull request please
```
## Given an expression with only { and }, find minimum bracket reversals to balance the expression

```c++
#include <iostream>
#include <vector>
#include <stack>
using namespace std;

int balance(string in)
{
	int unb_closed=0;
	int unb_open=0;
	for(char& c : in)
	{
		if(unb_open==0)
			if(c=='}')
				unb_closed++;
			else
				unb_open++;
		else if(c=='}')
			unb_open--;
		else
			unb_open++;
	}
	int r=(unb_open<unb_closed?unb_open:unb_closed);
	r+=(unb_open<unb_closed?(unb_closed-unb_open)/2:(unb_open-unb_closed)/2);
	return r;
}

int main()
{
	string in="}}}{{{";
	cout<<balance(in)<<endl;
}
```