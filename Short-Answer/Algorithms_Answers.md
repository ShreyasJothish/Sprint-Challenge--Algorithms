```
a)  a = 0
    while (a < n * n * n):
      a = a + n * n
```

### Answer: 

The run time complexity of above code is O(n).
On the initial thought it appears to be O(n^3) since while loop is getting executed n * n * n times. However for each iteration the value of a is updated n * n times, thus reducing the number of iterations needed. This effectively negates the n * n in the while loop condition.
So the complexity of above code is O(n)

```
b)  sum = 0
    for i in range(n):
      i += 1
      for j in range(i + 1, n):
        j += 1
        for k in range(j + 1, n):
          k += 1
          for l in range(k + 1, 10 + k):
            l += 1
            sum += 1
```
### Answer: 

The run time complexity of above code is O(n^3).
For relatively large values of n, following is the complexity of each for loop.
for i in range(n): - O(n) - Loop is dependent on n.

for j in range(i + 1, n): - O(n) - Loop is dependent on n.

for k in range(j + 1, n): - O(n) - Loop is dependent on n.

for l in range(k + 1, 10 + k): - O(1) - Loop is not dependent on n and shall remain constant irrespective of the value of n.

So overall runtime complexity is O(n^3)

```
c)  def bunnyEars(bunnies):
      if bunnies == 0:
        return 0

      return 2 + bunnyEars(bunnies-1)
```

### Answer: 
The recursive function calls itself n times. So complexity if O(n)
