# Insert a Node at the Tail of a Linked List 

@(OJ)[hackerrank, datastructure]

> **Problem Information:**
>
> [problem's link](https://www.hackerrank.com/challenges/insert-a-node-at-the-tail-of-a-linked-list)
>
> **AC date** : **2017-04-27**
>
> **Category** : data structure->linked list


-------------------

## Question

You are given the pointer to the head node of a linked list and an integer to add to the list. Create a new node with the given integer. Insert this node at the tail of the linked list and return the head node. The given head pointer may be null, meaning that the initial list is empty.


### Input Format

You have to complete the `Node* Insert(Node* head, int data) `method which takes two arguments - the head of the linked list and the integer to insert. You should NOT read any input from stdin/console.


### Output Format

Insert the new node at the head and `return` the head of the updated linked list. Do NOT print anything to stdout/console.

### Sample Input

NULL, data = $2$ 
 $2$--> NULL, data = 3


### Sample Output

> 2 -->NULL
> 
> 2 --> 3 --> NULL


## Answer

### C++

```c++

/*
  Insert Node at the end of a linked list 
  head pointer input could be NULL as well for empty list
  Node is defined as 
  struct Node
  {
     int data;
     struct Node *next;
  }
*/

Node* Insert(Node *head,int data)
{
    Node * temp_node = new Node;
    temp_node->data = data;
    temp_node->next = NULL;
    Node * temp = head;
    if(temp != NULL){
        while(temp->next!=NULL)
            temp = temp->next;
        temp->next = temp_node;
    }
    else
        head = temp_node;
    
    return head;
}


```

