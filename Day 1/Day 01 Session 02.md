# Practice
## Problem 1
Given an array of n numbers, give an algo for checking for duplicates
Assume array elements are +ve, from 0 to n-1
array is not read only

### Brute force O(N^2) solution:
```c++
#include <iostream>

using namespace std;

int main()
{
	int N;
	cin>>N
	int arr[N];
	bool flag=0;
	for(int i=0;i<n;i++)
	{
		cin>>arr[i];
	}
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

### O(N) solution:
```c++
void printRepeating(int arr[], int size)
{
	int i;
	for (i = 0; i < size; i++)
	{
		if (arr[abs(arr[i])] >= 0)
			arr[abs(arr[i])] = -arr[abs(arr[i])];
		else
		{
			cout<<"Duplicate found";
			break;
		}
}
```

### Brute force solution:

## Problem 2
Given a list of n-1 numbers in the range 1-n with no duplicates, find the one missing number
### Brute force approach:
Iterate through the array and look for missing integer

### O(N) solution:
```c++
int sum=N*(N+1)/2;
for(int i=0;i<N;i++)
	sum-=arr[i];
cout<<sum<<endl;
```
