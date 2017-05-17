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
Given a list of n-1 numbers in the range 1 to 1-n with no duplicates, find the one missing number
### Brute force approach:
Iterate through the array and look for missing integer

### O(N) solution:
```c++
long long int sum=N*(N+1)/2;
for(int i=0;i<N-1;i++)
	sum-=arr[i];
cout<<sum<<endl;
```
### Alternative O(N) solution:
To avoid sum from overflowing,
```c++
int xor=0;
for(int i=0;i<N-1;i++)
{
	xor^=i+1;
	xor^=arr[i];
}
xor^=N
cout<<xor<<endl;
```

## Problem 3
1. In an array of numbers containing , one number occurs an odd number of times. Every other number occurs an even number of times. If the array has every number from 1 to N, find the odd and even numbers

### O(N) solution:
```c++
int xor=0;
for(int i=0;i<sizeof(arr);i++)
{
	xor^=arr[i];
}
cout<<"odd number: "<<xor<<"\n";
```
2. In an array of numbers containing , one number occurs an even number of times. Every other number occurs an odd number of times. If the array has every number from 1 to N, find the even number
### O(N) solution:
```c++
int xor=0;
for(int i=0;i<N+1;i++)
{
	xor^=i+1;
}
for(int i=0;i<sizeof(arr))
{
	xor^=arr[i];
}
cout<<"odd number: "<<xor<<"\neven numbers:\n";
```
## Problem 4
Given an array of size n, find teo elements such that their sum equals a given number k. Assume array is sorted
### O(N) solution:
```c++
int i=0, j=N-1;
while(i!=j)
{
	if(arr[i]+arr[j]>k)
		j--;
	else if(arr[i]+arr[j]<k)
		i++;
	else
		cout<<arr[i]<<"+"<<arr[j]<<endl;
}
if(i==j)
	cout<<"no\n";
```
### Other solutions:
Brute forcing, or taking each element and binary-searching its complement are less efficient approaches

## Problem 5
Let A be an n integer array ascenging till index k and descending after k. Find k

### O(N) solution:
Loop through array and find k such that k[i+1]<k[i]

### O(log(N)) solution:
```c++
#include <stdio.h>
 
// A binary search based function that returns index of a peak element
int findPeakUtil(int arr[], int low, int high, int n)
{
    // Find index of middle element
    int mid = low + (high - low)/2;  /* (low + high)/2 */
 
    // Compare middle element with its neighbours (if neighbours exist)
    if ((mid == 0 || arr[mid-1] <= arr[mid]) &&
            (mid == n-1 || arr[mid+1] <= arr[mid]))
        return mid;
 
    // If middle element is not peak and its left neighbour is greater 
    // than it, then left half must have a peak element
    else if (mid > 0 && arr[mid-1] > arr[mid])
        return findPeakUtil(arr, low, (mid -1), n);
 
    // If middle element is not peak and its right neighbour is greater
    // than it, then right half must have a peak element
    else return findPeakUtil(arr, (mid + 1), high, n);
}
 
// A wrapper over recursive function findPeakUtil()
int findPeak(int arr[], int n)
{
    return findPeakUtil(arr, 0, n-1, n);
}
 
/* Driver program to check above functions */
int main()
{
    int arr[] = {1, 3, 20, 4, 1, 0};
    int n = sizeof(arr)/sizeof(arr[0]);
    printf("Index of a peak point is %d", findPeak(arr, n));
    return 0;
}
```