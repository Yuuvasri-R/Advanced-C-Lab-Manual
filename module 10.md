## EXP NO:16 C PROGRAM TO SEARCH A GIVEN ELEMENT IN THE GIVEN LINKED LIST.
### Aim:
To write a C program to search a given element in the given linked list.

### Algorithm:
1.	Define the structure for a node in a linked list.
2.	Define the search function to find a specific character in the linked list.
3.	Initialize the head of the linked list as needed.
4.	Call the search function and perform other linked list operations as needed.
 
### Program:

```
#include <stdio.h>
#include <stdlib.h>

struct node {
    int data;
    struct node *next;
};

struct node *head = NULL;

void search(char data){
    struct node *temp = head;
    int pos = 0;
    
    while(temp != NULL) {
        if(temp->data == data) {
            printf("Element found at position %d\n", pos);        
            }
        temp = temp->next;
        pos++;
    }
    printf("Element not found\n");
}
``` 

### Output:

<img width="712" height="498" alt="Screenshot 2026-09-20 090257" src="https://github.com/user-attachments/assets/8aea7106-83a7-427b-8397-ecb16aaec3f0" />

### Result:
Thus, the program to search a given element in the given linked list is verified successfully.


 
## EXP NO:17  PROGRAM TO INSERT A NODE IN A LINKED LIST.
### Aim:
To write a C program to insert a node in a linked list.
### Algorithm:
1.	Define the structure for a node in a linked list
2.	Define the insert function to insert a new node with character data at the end of the linked list.
3.	Initialize the head of the linked list as needed.
4.	Call the insert function and perform other linked list operations as needed.
 
### Program:

```
#include <stdio.h>
#include <stdlib.h>

struct node {
    char data;
    struct node *next;
};

struct node *head = NULL;

void insert(char data) {
    struct node *newnode, *temp;
    
    newnode = (struct node *)malloc(sizeof(struct node));
    newnode->data = data;
    newnode->next = NULL;
    
    if(head == NULL) {
        head = newnode;
    } else {
        temp = head;
        while(temp->next != NULL) {
            temp = temp->next;
        }
        temp->next = newnode;
    }
}
```

### Output:

<img width="475" height="427" alt="Screenshot 2026-09-20 090313" src="https://github.com/user-attachments/assets/70521553-2b32-47dc-ab91-55ae114535b5" />
 
### Result:
Thus, the program to insert a node in a linked list is verified successfully.


 
## EXP NO:18 C PROGRAM TO TRAVERSE A DOUBLY LINKED LIST
### Aim:
To write a C program to traverse a doubly linked list.

### Algorithm:
1.	Initialize a temporary pointer (temp) to the head of the list.
2.	Use a while loop to traverse the list until the end (temp == NULL) is reached.
3.	Inside the loop, print the data of the current node.
4.	Move to the next node by updating the temp pointer to point to the next node (temp = temp->next).
 
### Program:

```
#include <stdio.h>
#include <stdlib.h>

struct node {
    int data;
    struct node *next;
    struct node *prev;
};

struct node *head = NULL;

void display() {
    struct node *temp = head;
    
    printf("Doubly linked list: ");
    while(temp != NULL) {
        printf("%d ", temp->data);
        temp = temp->next;
    }
    printf("\n");
}
```

### Output:

<img width="467" height="562" alt="Screenshot 2026-09-20 090327" src="https://github.com/user-attachments/assets/18165552-5f3a-499a-88bd-07e9b177df03" />

### Result:
Thus, the program to traverse a doubly linked list is verified successfully. 



## EXP NO:19 C PROGRAM TO INSERT AN ELEMENT IN DOUBLY LINKED LIST
### Aim:
To write a C program to insert an element in doubly linked list

### Algorithm:
1.	Create a new node (newNode) and allocate memory for it.
2.	Set the data of the new node to the provided value.
3.	If the list is empty, set the new node as the head.
4.	If the list is not empty, traverse the list to find the last node.
5.	Set the new node's prev pointer to the last node and update the last node's next pointer to the new node.
 
### Program:

```
#include <stdio.h>
#include <stdlib.h>

struct node {
    float data;
    struct node *next;
    struct node *prev;
};

struct node *head = NULL;

static struct node* create_node(float data) {
    struct node *newnode = (struct node *)malloc(sizeof(struct node));
    newnode->data = data;
    newnode->next = NULL;
    newnode->prev = NULL;
    return newnode;
}
void insert(float data) {
    struct node *newnode = create_node(data);
    if(head == NULL) {
        head = newnode;
        return;
    }
    struct node *temp = head;
    while(temp->next != NULL) {
        temp = temp->next;
    }
    temp->next = newnode;
    newnode->prev = temp;
}
```

### Output:

<img width="570" height="767" alt="Screenshot 2026-09-20 090344" src="https://github.com/user-attachments/assets/e4ce619d-d78f-43ee-a542-9e9be2fba9ea" />

### Result:
Thus, the program to insert an element in doubly linked list is verified successfully.




## EXP NO:20 C FUNCTION TO DELETE A GIVEN ELEMENT IN THE GIVEN LINKED LIST

### Aim:
To write a C function that deletes a given element from a linked list.

### Algorithm:
1.	Check if the Linked List is Empty:
o	If the head of the linked list is NULL, print a message indicating the list is empty and exit the function.
2.	Traverse the Linked List:
o	Start from the head node and iterate through the list to find the node that contains the given element (data).
3.	Handle Deletion of the First Node:
o	If the element to be deleted is found in the head node:
	Update the head of the linked list to point to the next node (i.e., head = head->next).
	Free the memory allocated to the node to be deleted.
	Exit the function.
4.	Traverse and Delete from the Middle or End:
o	If the element is not in the head node, continue traversing the list by checking each node’s next pointer.
o	When the node with the element is found, update the previous node’s next pointer to point to the next node of the node to be deleted (prev->next = current->next).
o	Free the memory allocated to the node to be deleted.
5.	Handle the Case when the Element is Not Found:
o	If the element is not found in any node, print a message indicating the element is not present in the list.
6.	End the Function.


### Program:


```
#include <stdio.h>
#include <stdlib.h>

struct Node{
    char data; 
    struct Node *next;
}*head;
void delete()
{
    if(head==NULL){
        printf("List is empty\n");
        return;
    }
    else if(head->next==NULL){
        head=NULL;
        free(head);
        printf("Node deleted from the begining ...\n");
    }
    else{
        struct Node *ptr;
        ptr=head;
        head=head->next;
        free(ptr);
        printf("Node deleted from the begining ...\n");
    }
}

```

### Output:

<img width="1182" height="772" alt="Screenshot 2026-09-20 090358" src="https://github.com/user-attachments/assets/84c0de3a-282b-49a0-9855-dd92d2f7899b" />

### Result:
Thus, the function that deletes a given element from a linked list is verified successfully.
