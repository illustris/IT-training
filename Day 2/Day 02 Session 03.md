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
