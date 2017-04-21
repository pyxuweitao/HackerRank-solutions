# Sparse Arrays

@(OJ)[hackerrank, datastructure]

> **Problem Information:**
>
> [problem's link](https://www.hackerrank.com/challenges/sparse-arrays)
>
> **AC date** : **2017-04-20**
>
> **Category** : data structure->array


-------------------

## Question

There are $N$ strings. Each string's length is no more than $20$ characters. There are also $Q$ queries. For each query, you are given a string, and you need to find out how many times this string occurred previously.

### Input Format

The first line contains $N$, the number of strings.
The next $N$ lines each contain a string.
The $N+2^{nd}$ line contains $Q$, the number of queries.
The following $Q$ lines each contain a query string.

### Constraints

- $1 \le N \le 1000$
- $1 \le Q \le 1000$
- $1 \le length of any string \le 20$

### Output Format

Print a single line of $n$ space-separated integers denoting the final state of the array after performing $d$ left rotations.

### Sample Input

> 4
> 
> aba
> 
> baba
> 
> aba
> 
> xzxb
> 
> 3
> 
> aba
> 
> xzxb
> 
> ab
> 


### Sample Output

> 2
>
> 1
>
> 0

## Answer

### Python 2

```python

string_seq = [raw_input().strip() for _ in xrange(int(raw_input()))]
for _ in xrange(int(raw_input())):
    print string_seq.count(raw_input().strip())


```

code shown above is clean but not efficient because it uses linea search(search in the list),so the time complexity is O(N*Q).The better solution is to use dict and the time complexity of using dict is O(N).

```python

from collections import defaultdict

seq_counter = defaultdict(int)
for _ in xrange(int(raw_input())):
    seq_counter[raw_input().strip()] += 1

for _ in xrange(int(raw_input())):
    query = raw_input().strip()
    try:
        print seq_counter[query]
    except KeyError:
        print 0


```