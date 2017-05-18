# Linked list
Each node has a value, and a pointer to the next node

## Singly linked list:
```c++
struct ll;
struct ll
{
	int val;
	ll *next;
};
```

This memory map:
```
addr val next | addr val next | addr val next | addr val next |
1200   3 1208 | 1208  12 1224 | 1216   7 null | 1224   5 1216 |
```
corresponds to:
3->12->5->7

## Doubly linked list:
```c++
struct ll;
struct ll
{
	int val;
	ll *next;
	ll *prev;
};
```

## Circular lined list:
Singly linked list where the last element links to the first element

## Linked list practice questions
### Q. Find the nth last node in a linked list
O(N), O(1) space Solution:
```
Move pointer a to n+1th element
Move pointer b to 0th element
keep incrementing both till a is at the last element
pointer b has l-nth element
```
### Q. Check if a given linked list ends in a cycle
O(N) solution:
```
There are two pointers, slow and fast. Slow increments by 1, fast increments by 2. If fast->next == NULL, it is a singly linked list. If at some point fast==slow, the list ends in a cycle
```

### Q. Find the midpoint of a singly linked list
O(N) solution:
```
Increment fastptr by 2, slowptr by 1. When fastptr is at the end, slowptr is at the midpoint
```

### Q. Reverse a singly linked list
O(N) solution:
```
Remember previous address and current node's next address
replace current.next with the previous address
remember current node's address as prev
move to next node
repeat
```