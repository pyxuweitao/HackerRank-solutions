# Left Rotation

@(OJ)[hackerrank, datastructure]

> **Problem Information:**
>
> [problem's link](https://www.hackerrank.com/challenges/array-left-rotation)
>
> **AC date** : **2017-04-19**
>
> **Category** : data structure->array


-------------------

## Question

A left rotation operation on an array of size $n$ shifts each of the array's elements $1$ unit to the left. For example, if $2$ left rotations are performed on array $[1,2,3,4,5]$, then the array would become $[3,4,5,1,2]$.

Given an array of $n$ integers and a number, $d$ , perform $d$ left rotations on the array. Then print the updated array as a single line of space-separated integers.

### Input Format

The first line contains two space-separated integers denoting the respective values of  $n$(the number of integers) and  $d$(the number of left rotations you must perform). 
The second line contains $n$ space-separated integers describing the respective elements of the array's initial state.

### Constraints

- $1 \le n \le 10^5$
- $1 \le d \le n$
- $1 \le a_i \le 10^6$

### Output Format

Print a single line of $n$ space-separated integers denoting the final state of the array after performing $d$ left rotations.

### Sample Input

> 5 4
 
> 1 2 3 4 5


### Sample Output

> 5 1 2 3 4

## Answer

### C++

```c++
//head.h
using namespace std;

int main() {
    /* Enter your code here. Read input from STDIN. Print output to STDOUT */  
    int n = 0;
    int d = 0;
    int seq[100010]={0};
    
    cin >> n >> d;
    for(int i = 0; i < n; i++)
        cin>>seq[i];
    
    for(int i = d; i < n; i++)
        cout<<seq[i]<<' ';
    
    for(int i = 0; i < d; i++)
        cout<<seq[i]<<' ';
    
    return 0;
}

```

Another C++

```c++

int main() {
    /* Enter your code here. Read input from STDIN. Print output to STDOUT */  
    int n = 0;
    int d = 0;
    int seq[100010]={0};
    
    cin >> n >> d;
    for(int i = 0; i < n; i++)
        cin>>seq[i];
    
    for(int i = 0; i < n; i++)
        cout<<seq[(i+d)%n]<<' ';
        
    return 0;
}

```