

EXP NO 26: C PROGRAM TO DISPLAY STACK ELEMENTS USING LINKED LIST.
Aim:
To write a C program to display stack elements using linked list.

Algorithm:
1.	Define a structure Node with two members: data to store the integer value and next to point to the next node in the linked list.
2.	Declare a global variable head representing the starting node of the linked list.
3.	Define a function display to print the elements of the linked list.
4.	Declare a pointer p and initialize it with the head of the linked list.
5.	Use a while loop to traverse the linked list:
6.	Print the data of the current node.
7.	Move to the next node using the next pointer.
 
Program:

```
#include <stdio.h>
#include <stdlib.h>
struct Node {
    int data;
    struct Node *next;
} *head = NULL;
void push(int val) {
    struct Node *newNode = (struct Node*)malloc(sizeof(struct Node));
    newNode->data = val;
    newNode->next = head;
    head = newNode;
}
void display() {
    if (head == NULL) {
        printf("Stack is empty\n");
        return;
    }
    struct Node *p = head;
    while (p != NULL) {
        printf("%d\n", p->data);
        p = p->next;
    }
}
int main() {
    push(10);
    push(20);
    push(30);
    display();
    return 0;
}
```

Output:

<img width="1477" height="1108" alt="image" src="https://github.com/user-attachments/assets/4595a5c3-2e5e-46f7-8f01-1134d0b94240" />

Result:
Thus, the program to display stack elements using linked list is verified successfully. 


EXP.NO 27: C PROGRAM TO POP AN ELEMENT FROM THE GIVEN STACK USING 
LINKED LIST.
Aim:
To write a C program to pop an element from the given stack using liked list.

Algorithm:
1.	Check for Empty Stack
2.	If head is equal to NULL, Print "Stack is empty."
3.	Else Proceed to the next step.
4.	Set head to point to the next node in the stack.
 
Program:

```
#include <stdio.h>
#include <stdlib.h>
struct Node {
    int data;
    struct Node *next;
} *head = NULL;
void push(int val) {
    struct Node *newNode = (struct Node*)malloc(sizeof(struct Node));
    newNode->data = val;
    newNode->next = head;
    head = newNode;
}
void pop() {
    if (head == NULL) {
        printf("Stack is empty.\n");
        return;
    }
    struct Node *temp = head;
    head = head->next;
    free(temp);
}
int main() {
    push(10);
    push(20);
    pop();
    struct Node *p = head;
    while (p != NULL) {
        printf("%d\n", p->data);
        p = p->next;
    }
    return 0;
}
```
Output:

<img width="1398" height="1074" alt="image" src="https://github.com/user-attachments/assets/250bcad2-67a8-4034-b32d-e011ecc94dbf" />

Result:
Thus, the program to pop an element from the given stack using liked list is verified successfully.

 
EXP NO:28 C PROGRAM TO DISPLAY QUEUE ELEMENTS USING LINKED LIST.
Aim:
To write a C program to display queue elements using linked list.
Algorithm:
1.	Check if Queue is Empty
2.	Display Queue Elements
3.	Print the data of the current node pointed to by front
4.	Update front to point to the next node.
5.	End the display function.
 
Program:

```
#include <stdio.h>
#include <stdlib.h>
struct Node {
    int data;
    struct Node *next;
} *front = NULL, *rear = NULL;
void enqueue(int val) {
    struct Node *p = (struct Node*)malloc(sizeof(struct Node));
    p->data = val;
    p->next = NULL;
    if (front == NULL && rear == NULL) front = rear = p;
    else { rear->next = p; rear = p; }
}
void display() {
    if (front == NULL) {
        printf("Queue is empty\n");
        return;
    }
    struct Node *temp = front;
    while (temp != NULL) {
        printf("%d\n", temp->data);
        temp = temp->next;
    }
}
int main() {
    enqueue(10);
    enqueue(20);
    enqueue(30);
    display();
    return 0;
}
```
Output:

<img width="1244" height="1088" alt="image" src="https://github.com/user-attachments/assets/3189b07c-1741-481d-93a7-89ea99e381ec" />

Result:
Thus, the program to display queue elements using linked list is verified successfully.


 
EXP NO:29 C PROGRAM TO INSERT ELEMENTS IN QUEUE USING LINKED LIST

Aim:
To write a C program to insert elements in queue using linked list

Algorithm:
1.	Allocate Memory for New Node
2.	Set Data and Next Pointer
3.	Check if Queue is Empty
4.	Set both front and rear to point to the new node p.
5.	Set the next pointer of the current rear to point to the new node p.
6.	End of Enqueue Operation
 
Program:

```
#include <stdio.h>
#include <stdlib.h>
struct Node {
    int data;
    struct Node *next;
} *front = NULL, *rear = NULL;
void enqueue(int val) {
    struct Node *p = (struct Node*)malloc(sizeof(struct Node));
    p->data = val;
    p->next = NULL;
    if (front == NULL && rear == NULL) {
        front = rear = p;
    } else {
        rear->next = p;
        rear = p;
    }
}
int main() {
    enqueue(100);
    enqueue(200);
    struct Node *temp = front;
    while (temp != NULL) {
        printf("%d\n", temp->data);
        temp = temp->next;
    }
    return 0;
}
```
Output:

<img width="1461" height="1005" alt="image" src="https://github.com/user-attachments/assets/7b2ca827-322f-4552-898b-5d4a221c75f8" />

Result:
Thus, the program to insert elements in queue using linked list is verified successfully.



EXP NO:30 C FUNCTION TO FIND THE PEEK OF QUEUE USING LINKED LIST.


Aim:

The aim of this function is to retrieve the "peek" (the front element) of a queue implemented using a linked list

Algorithm:

1.	Check if the queue is empty:
o	If the queue is empty (i.e., the front pointer is NULL), return an error or a message indicating that the queue is empty.
2.	Access the front element:
o	If the queue is not empty, return the data stored in the front node of the linked list (i.e., the element at the head of the queue).

Program:

```
#include <stdio.h>
#include <stdlib.h>
struct Node {
    int data;
    struct Node *next;
} *front = NULL, *rear = NULL;
void enqueue(int val) {
    struct Node *p = (struct Node*)malloc(sizeof(struct Node));
    p->data = val;
    p->next = NULL;
    if (front == NULL && rear == NULL) front = rear = p;
    else { rear->next = p; rear = p; }
}
void peek() {
    if (front == NULL) {
        printf("Queue is empty\n");
        return;
    }
    printf("%d\n", front->data);
}
int main() {
    enqueue(50);
    enqueue(100);
    peek();
    return 0;
}
```
Output:

<img width="1449" height="990" alt="image" src="https://github.com/user-attachments/assets/8b87fe7d-56c0-4717-a7eb-bf6c1d37ad08" />



Result:

Thus, the program to retrieve the "peek" (the front element) of a queue implemented using a linked list is verified successfully.


