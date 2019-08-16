# Analysis of Algorithms

## Exercise I

Give an analysis of the running time of each snippet of
pseudocode with respect to the input size n of each of the following:

a)

The time complexity for this is O(n).
Since there is only one loop, each time the function loops (a) increases by n^2. The loop comes to an end when (a) is not < n^3.

```
a = 0
    while (a < n * n * n):
      a = a + n * n
```

b)

The time complexity is O(n^3). Since there are 3 nested loops, most of them (but not all) with running times proportional to n. The number of iterations in the inner loops is slightly smaller than n in each case, but it is smaller than n by a small amount that doesn't scale with n.

```
 sum = 0
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

c) The time complexity is O(n).
When bunnyEars(n) is called, the function will run once and then call itself for n-1. So, in the end the function winds up being called n times.

```
 def bunnyEars(bunnies):
      if bunnies == 0:
        return 0

      return 2 + bunnyEars(bunnies-1)
```

## Exercise II

Suppose that you have an _n_-story building and plenty of eggs. Suppose also that an egg gets broken if it is thrown off floor _f_ or higher, and doesn't get broken if dropped off a floor less than floor _f_. Devise a strategy to determine the value of _f_ such that the number of dropped eggs is minimized.

Write out your proposed algorithm in plain English or pseudocode and give the runtime complexity of your solution.

**_The best solution I believe is the binary search method. Since we are trying avoid breaking as many eggs as possible._**

**_We can divide our building into two top and bottom floors at floor n/2. If the egg breaks at n/2, we can repeat the process with the lower subset; if it does not break, try the higher floors instead. We should have a check for broken eggs and check whether now search only in the bottom half of the floors. The runtime for this would probably O((log n)^2), since multiple checks would be necessary to verify broken eggs._**
