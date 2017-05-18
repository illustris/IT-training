# Linked list
Each node has a value, and a pointer to the next node
```c++
struct ll;
struct ll
{
	int val;
	ll *next;
}
```

```
addr val next | addr val next | addr val next | addr val next |
1200   3 1208 | 1208  12 1224 | 1216   7 null | 1224   5 1216 |

This corresponds to:
3->12->5->7
```