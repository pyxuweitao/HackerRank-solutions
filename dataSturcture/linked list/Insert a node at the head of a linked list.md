# Insert a node at the head of a linked list

@(OJ)[hackerrank, datastructure]

> **Problem Information:**
>
> [problem's link](https://www.hackerrank.com/challenges/insert-a-node-at-the-head-of-a-linked-list)
>
> **AC date** : **2017-04-26**
>
> **Category** : data structure->linked list


-------------------

## Question

You’re given the pointer to the head node of a linked list and an integer to add to the list. Create a new node with the given integer, insert this node at the head of the linked list and return the new head node. The head pointer given may be null meaning that the initial list is empty.


### Input Format

You have to complete the `Node* Insert(Node* head, int data) `method which takes two arguments - the head of the linked list and the integer to insert. You should NOT read any input from stdin/console.


### Output Format

Insert the new node at the head and `return` the head of the updated linked list. Do NOT print anything to stdout/console.

### Sample Input

NULL , data = 1 
1 --> NULL , data = 2


### Sample Output

> 1 --> NULL
> 
> 2 --> 1 --> NULL


## Answer

### C++

```c++
/*
  Insert Node at the begining of a linked list
  Initially head pointer argument could be NULL for empty list
  Node is defined as 
  struct Node
  {
     int data;
     struct Node *next;
  }
return back the pointer to the head of the linked list in the below method.
*/
Node* Insert(Node *head,int data)
{
    Node * node = new Node;
    node->data = data;
    node->next = head;
    head = node;
    return head;
}


```

