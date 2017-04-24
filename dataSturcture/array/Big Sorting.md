# Big Sorting

@(OJ)[hackerrank, datastructure]

> **Problem Information:**
>
> [problem's link](https://www.hackerrank.com/challenges/big-sorting)
>
> **AC date** : **2017-04-21**
>
> **Category** : data structure->array


-------------------

## Question

Consider an array of numeric strings, $unsorted$, where each string is a positive number with anywhere from $1$ to $10^6$ digits. Sort the array's elements in non-decreasing (i.e., ascending) order of their real-world integer values and print each element of the sorted array on a new line.

### Input Format

The first line contains an integer, $n$, denoting the number of strings in $unsorted$. 
Each of the $n$ subsequent lines contains a string of integers describing an element of the array.

### Constraints

- $1 \le n \le 2 \times 10^5$
- Each string is guaranteed to represent a positive integer without leading zeros.
- The total number of digits across all strings in $unsorted$ is between $1$ and $10^6$ (inclusive).

### Output Format

Print each element of the sorted array on a new line.

### Sample Input

> 6
> 
> 31415926535897932384626433832795
> 
> 1
> 
> 3
> 
> 10
> 
> 3
> 
> 5


### Sample Output

> 1
> 
> 3
> 
> 3
> 
> 5
> 
> 10
> 
> 31415926535897932384626433832795

## Answer

### Python 2

```python

#!/bin/python

import sys

n = int(raw_input().strip())
unsorted = []
unsorted_i = 0
for unsorted_i in xrange(n):
    unsorted_t = str(raw_input().strip())
    unsorted.append(unsorted_t)
# your code goes here

print "\n".join(sorted(unsorted, cmp=lambda a, b: cmp(a,b) if len(a)==len(b) else len(a)-len(b)))

```
