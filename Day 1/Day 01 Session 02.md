# Practice
## Problem 1
Given an array of n numbers, give an algo for checking for duplicates
Assume array elements are +ve, from 0 to n-1
array is not read only

```c++
#include <iostream>

using namespace std;

int main()
{
	int N=6;
	bool flag;
	int arr[N]={1,2,3,4,5,7};
	for(int i=0;i<N && !flag;i++)
	{
		for(int j=i+1;j<N;j++)
		{
			if(arr[i]==arr[j])
			{
				flag=1;
				break;
			}
		}
	}
	cout<<(flag?"yes":"no")<<endl;
}
```