Complexity:

Big O notation: Relation between N and time taken

examples:

```c++
for(i=0;i<N;i++)
{
	a=a+j;
}```
Complexity: Order of N {written ad O(N)}, as time taken is linearly proportional to N

```c++
for(j=0;j<N;j++)
	for(i=0;i<N;i++)
	{
		a=a+j+i;
	}```
Complexity: O(N^2), as time taken is proportional to the square of N (Number of iterations = N^2).

```c++
int a=0,i=N;
while(i>0)
{
	a+=i;
	i/=2;
}```
Complexity: O(log(N)), as number of iterations is proportional to log(N)


Sorting Algorithms

Insertion sort

```c++
for(int j=1;j<n;j++)
{
	key=A[j];
	i=j-1;
	while(i>=0 && A[i]>key)
	{
		A[i+1] = A[i]
		i=i-1;
	}
	A[i+1]=key;
}```

Merge sort:
