# Dynamic programming
Breaking down a problem into sub-problems, and reusing computations that overlap

Example:
```
              F(n)
              / \
             /   \
            /     \
           /       \
     F(n-1)         F(n-2)
      / \            / \
     /   \          /   \
    /     \        /     \
   /       \      /       \
 F(n-2)     F(n-3)         F(n-4)
```

```c++
#include <iostream>
#include <vector>
using namespace std;

void fib();

int n;
vector<long long int> fibresult;

int main()
{
	n=65535;
	fibresult.resize(n);
	fib();
	
	cout<<fibresult[n-1]<<endl;
}

void fib()
{
	fibresult[0] = 1;
	fibresult[1] = 1;
	for (int i = 2; i<n; i++)
		fibresult[i] = fibresult[i-1] + fibresult[i-2];
}
```

## Substrings and subsequences
Number of substrings = NC2
Number of subsequences = 2^N

### Q. Write a program to find the largest common subsequence of two strings

### Q. Find the largest palindrome subsequence of a string

### Q. FInd the edit distance between two strings

```c++
#include <string>
#include <iostream>
using namespace std;

size_t EditDistance(const std::string &s1, const std::string &s2)
{
	const size_t m(s1.size());
	const size_t n(s2.size());

	if( m==0 ) return n;
	if( n==0 ) return m;

	size_t *costs = new size_t[n + 1];

	for( size_t k=0; k<=n; k++ ) costs[k] = k;

	size_t i = 0;
	for ( std::string::const_iterator it1 = s1.begin(); it1 != s1.end(); ++it1, ++i )
	{
		costs[0] = i+1;
		size_t corner = i;

		size_t j = 0;
		for ( std::string::const_iterator it2 = s2.begin(); it2 != s2.end(); ++it2, ++j )
		{
			size_t upper = costs[j+1];
			if( *it1 == *it2 )
			{
				costs[j+1] = corner;
			}
			else
			{
				size_t t(upper<corner?upper:corner);
				costs[j+1] = (costs[j]<t?costs[j]:t)+1;
			}

			corner = upper;
		}
	}

	size_t result = costs[n];
	delete [] costs;

	return result;
}
 
int main()
{
	string s0 = "tomato";
		string s1 = "potato";
	cout << "distance between " << s0 << " and " << s1 << " : " 
		 << EditDistance(s0,s1) << std::endl;
 
		return 0;
}
```