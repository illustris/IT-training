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