EXP NO:16 C PROGRAM TO SEARCH A GIVEN ELEMENT IN THE GIVEN LINKED LIST.
Aim:
To write a C program to search a given element in the given linked list.

Algorithm:
1.	Define the structure for a node in a linked list.
2.	Define the search function to find a specific character in the linked list.
3.	Initialize the head of the linked list as needed.
4.	Call the search function and perform other linked list operations as needed.
 
Program:

```
#include <stdio.h>
#include <stdlib.h>
struct Node {
    char data;
    struct Node *next;
} *head = NULL;
void search(char key) {
    struct Node *temp = head;
    int pos = 1, found = 0;
    while (temp != NULL) {
        if (temp->data == key) {
            printf("Element %c found at position %d\n", key, pos);
            found = 1;
            break;
        }
        temp = temp->next;
        pos++;
    }
    if (!found) printf("Element not found\n");
}
int main() {
    struct Node *n1 = (struct Node*)malloc(sizeof(struct Node));
    struct Node *n2 = (struct Node*)malloc(sizeof(struct Node));
    n1->data = 'A'; n1->next = n2;
    n2->data = 'B'; n2->next = NULL;
    head = n1;
    search('B');
    return 0;
}
```
Output:

<img width="1478" height="1079" alt="image" src="https://github.com/user-attachments/assets/42c66955-f3f8-4015-92a0-a62128fa67db" />

Result:
Thus, the program to search a given element in the given linked list is verified successfully.


 
EXP NO:17  PROGRAM TO INSERT A NODE IN A LINKED LIST.
Aim:
To write a C program to insert a node in a linked list.
Algorithm:
1.	Define the structure for a node in a linked list
2.	Define the insert function to insert a new node with character data at the end of the linked list.
3.	Initialize the head of the linked list as needed.
4.	Call the insert function and perform other linked list operations as needed.
 
Program:

```
#include <stdio.h>
#include <stdlib.h>
struct Node {
    char data;
    struct Node *next;
} *head = NULL;
void insert(char val) {
    struct Node *newNode = (struct Node*)malloc(sizeof(struct Node));
    newNode->data = val;
    newNode->next = NULL;
    if (head == NULL) {
        head = newNode;
    } else {
        struct Node *temp = head;
        while (temp->next != NULL) temp = temp->next;
        temp->next = newNode;
    }
}
int main() {
    insert('X');
    insert('Y');
    struct Node *temp = head;
    while (temp != NULL) {
        printf("%c ", temp->data);
        temp = temp->next;
    }
    printf("\n");
    return 0;
}
```
Output:

<img width="1352" height="1089" alt="image" src="https://github.com/user-attachments/assets/9802ec66-9050-47f9-922a-f3a26134df8b" />

Result:
Thus, the program to insert a node in a linked list is verified successfully.

 
EXP NO:18 C PROGRAM TO TRAVERSE A DOUBLY LINKED LIST
Aim:
To write a C program to traverse a doubly linked list.

Algorithm:
1.	Initialize a temporary pointer (temp) to the head of the list.
2.	Use a while loop to traverse the list until the end (temp == NULL) is reached.
3.	Inside the loop, print the data of the current node.
4.	Move to the next node by updating the temp pointer to point to the next node (temp = temp->next).
 
Program:

```
#include <stdio.h>
#include <stdlib.h>
struct Node {
    int data;
    struct Node *prev;
    struct Node *next;
} *head = NULL;
void traverse() {
    struct Node *temp = head;
    while (temp != NULL) {
        printf("%d ", temp->data);
        temp = temp->next;
    }
    printf("\n");
}
int main() {
    struct Node *n1 = (struct Node*)malloc(sizeof(struct Node));
    struct Node *n2 = (struct Node*)malloc(sizeof(struct Node));
    n1->data = 10; n1->prev = NULL; n1->next = n2;
    n2->data = 20; n2->prev = n1; n2->next = NULL;
    head = n1;
    traverse();
    return 0;
}
```
Output:


<img width="1469" height="910" alt="image" src="https://github.com/user-attachments/assets/accdd1d0-b74e-49dd-8a70-862116a6cf04" />


Result:
Thus, the program to traverse a doubly linked list is verified successfully. 



EXP NO:19 C PROGRAM TO INSERT AN ELEMENT IN DOUBLY LINKED LIST
Aim:
To write a C program to insert an element in doubly linked list

Algorithm:
1.	Create a new node (newNode) and allocate memory for it.
2.	Set the data of the new node to the provided value.
3.	If the list is empty, set the new node as the head.
4.	If the list is not empty, traverse the list to find the last node.
5.	Set the new node's prev pointer to the last node and update the last node's next pointer to the new node.
 
Program:

```
#include <stdio.h>
#include <stdlib.h>
struct Node {
    int data;
    struct Node *prev;
    struct Node *next;
} *head = NULL;
void insert(int val) {
    struct Node *newNode = (struct Node*)malloc(sizeof(struct Node));
    newNode->data = val;
    newNode->next = NULL;
    newNode->prev = NULL;
    if (head == NULL) {
        head = newNode;
    } else {
        struct Node *temp = head;
        while (temp->next != NULL) temp = temp->next;
        temp->next = newNode;
        newNode->prev = temp;
    }
}
int main() {
    insert(100);
    insert(200);
    struct Node *temp = head;
    while (temp != NULL) {
        printf("%d ", temp->data);
        temp = temp->next;
    }
    printf("\n");
    return 0;
}
```
Output:

<img width="1415" height="1115" alt="image" src="https://github.com/user-attachments/assets/024e64d6-edf3-4fbc-bfcf-e5402a7a23bf" />

Result:
Thus, the program to insert an element in doubly linked list is verified successfully.

EXP NO:20 C FUNCTION TO DELETE A GIVEN ELEMENT IN THE GIVEN LINKED LIST

Aim:
To write a C function that deletes a given element from a linked list.

Algorithm:
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


Program:

```
#include <stdio.h>
#include <stdlib.h>
struct Node {
    int data;
    struct Node *next;
} *head = NULL;
void deleteNode(int val) {
    if (head == NULL) {
        printf("List is empty\n");
        return;
    }
    struct Node *temp = head, *prev = NULL;
    if (temp != NULL && temp->data == val) {
        head = temp->next;
        free(temp);
        return;
    }
    while (temp != NULL && temp->data != val) {
        prev = temp;
        temp = temp->next;
    }
    if (temp == NULL) {
        printf("Element not found\n");
        return;
    }
    prev->next = temp->next;
    free(temp);
}
int main() {
    struct Node *n1 = (struct Node*)malloc(sizeof(struct Node));
    struct Node *n2 = (struct Node*)malloc(sizeof(struct Node));
    n1->data = 5; n1->next = n2;
    n2->data = 10; n2->next = NULL;
    head = n1;
    deleteNode(5);
    struct Node *temp = head;
    while (temp != NULL) {
        printf("%d ", temp->data);
        temp = temp->next;
    }
    printf("\n");
    return 0;
}
```
Output:


<img width="1433" height="1096" alt="image" src="https://github.com/user-attachments/assets/0fa6e508-74db-40c6-8047-60c983f5b116" />

Result:
Thus, the function that deletes a given element from a linked list is verified successfully.





