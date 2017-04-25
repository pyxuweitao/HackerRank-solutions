# Print the Elements of a Linked List

@(OJ)[hackerrank, datastructure]

> **Problem Information:**
>
> [problem's link](https://www.hackerrank.com/challenges/print-the-elements-of-a-linked-list)
>
> **AC date** : **2017-04-25**
>
> **Category** : data structure->linked list


-------------------

## Question

If you're new to linked lists, this is a great exercise for learning about them. Given a pointer to the head node of a linked list, print its elements in order, one element per line. If the head pointer is null (indicating the list is empty), don’t print anything.



### Input Format

The `void Print(Node* head)` method takes the head node of a linked list as a parameter. Each struct Node has a data field (which stores integer data) and a next field (which points to the next element in the list).

**Note**: Do not read any input from stdin/console. Each test case calls the Print method individually and passes it the head of a list.

### Output Format

Print the integer data for each element of the linked list to stdout/console (e.g.: using printf, cout, etc.). There should be one element per line.

### Sample Input

> NULL
>   
> 1->2->3->NULL


### Sample Output

> 1
> 
> 2
> 
> 3

## Answer

### C++

```c++
/*
  Print elements of a linked list on console 
  head pointer input could be NULL as well for empty list
  Node is defined as 
  struct Node
  {
     int data;
     struct Node *next;
  }
*/
void Print(Node *head)
{
    Node * temp = head;
    if(head!=NULL){
        while(temp!=NULL){
        cout<<temp->data<<endl;
        temp = temp->next;
        }
    }
 }

```

