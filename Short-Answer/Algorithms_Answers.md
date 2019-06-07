## Exercise I

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

## Exercise II

## Understanding the Problem:

n - Number of Stories building
f - Cut-off or Limit for egg breaking. 
If eggs are dropped from this floor or higher then it breaks.
If eggs are dropped form floor lower than f, then it wont break.

Problem is to find the value of f.

## Plan

Brute force method for handling this problem would be to drop an egg from each floor and determine the value of f.

### Pseudo code

```
for i between 0 to n
    drop an egg at each floor
    
    if egg breaks, then return i - 1
```

This logic has complexity of O(n).

However since we are talking of n story building, we can consider it to be a sorted array of floors.
So instead we can use binary search algorithm. Start by dropping an egg from middle floor of building. 
If it breaks we need to search for f downwards else we should search for f upwards.

This will give complexity of O(logn) since we are cutting the search by half each time.

```
low = 0
high = n

while low < high:
    mid = (high + low) // 2
    drop egg from middle
    if egg breaks, then search for f in lower floors
        high = mid -1
    else search for f in higher floors
        low = mid + 1
 ```
