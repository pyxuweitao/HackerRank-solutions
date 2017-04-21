# Arrays - DS

@(OJ)[hackerrank, datastructure]

> **Problem Information:**
> 
> [problem's link](https://www.hackerrank.com/challenges/arrays-ds)
>
> **AC date** : **2017-04-17**
>
> **Category** : data structure->array



-------------------

## Question

An array is a type of data structure that stores elements of the same type in a contiguous block of memory. In an array,$A$, of size $N$, each memory location has some unique index,  $i$(where $0 \le i \lt n $), that can be referenced as $A[i]$ (you may also see it written as $A_i$).

Given an array, $A$, of $N$ integers, print each element in reverse order as a single line of space-separated integers.

**Note**: If you've already solved our C++ domain's Arrays Introduction challenge, you may want to skip this.

### Input Format

The first line contains an integer,  $N$(the number of integers in $A$). 
The second line contains $N$ space-separated integers describing $A$.

### Constraints

- $1 \le N \le 10^3$
- $1 \le A_i \le 10^4$, where $A_i$ is the $i^{th}$integer in $A$

### Output Format

Print all $N$ integers in $A$ in reverse order as a single line of space-separated integers.

### Sample Input

> 4

> 1 4 3 2

### Sample Output

>  2 3 4 1

## Answer

### C++

```c++
//head.h
using namespace std;

int main(){
    int n;
    cin >> n;
    vector<int> arr(n);
    for(int arr_i = 0;arr_i < n;arr_i++){
       cin >> arr[arr_i];
    }

    for(int i = (int)arr.size() - 1; i > 0; i--)
        cout << arr[i] << ' ';

    cout << arr[0];
    return 0;
}


```