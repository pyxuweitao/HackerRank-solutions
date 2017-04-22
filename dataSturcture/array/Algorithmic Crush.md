# Algorithmic Crush

@(OJ)[hackerrank, datastructure]

> **Problem Information:**
>
> [problem's link](https://www.hackerrank.com/challenges/crush)
>
> **AC date** : **2014-04-22**
>
> **Category** : data structure->array


-------------------

## Question

Devendra在9号云上看到了他的教练朝他微笑。 每次教授选出Devendra单独问他一个问题，Devendra朦胧的头脑里全是他的教练和她的微笑，以至于他无法专注于其他事情。帮助他解决这个问题：

给你一个长度为N的列表，列表的初始值全是0。对此列表，你要进行M次查询，输出列表种最终N个值的最大值。对每次查询，给你的是3个整数——a,b和k，你要对列表中从位置a到位置b范围内的（包含a和b)的全部元素加上k。 

### Input Format

第一行包含两个整数 N和 M。
接下来 M行，每行包含3个整数 a, b 和 k。
**列表中的数位置编号为从1到 N**。

### Constraints


- 3 <= **N** <= 10^7 
- 1 <= **M** <= 2*10^5 
- 1 <= a <= b <= N 
- 0 <= k <= 10^9

### Output Format

单独的一行包含 **最终列表里的最大值**

### Sample Input

>5 3
>
>1 2 100
>
>2 5 100
>
>3 4 100



### Sample Output

>200

## Answer

### C++

```c++

#head.h

using namespace std;

int main(){
    long M, N;
    long a, b, k;
    long max=0;
    long temp=0;
    
    cin>>M>>N;
    long * res= new long[M+1]();
    
    while(N--){
        cin>>a>>b>>k;
        res[a-1]+=k;
        res[b]-=k;
    }

    for(int i=0; i<M; i++) {
        temp += res[i];
        max = temp > max ? temp : max;
    }
    
    cout<<max<<endl;
    return 0;
}


```
