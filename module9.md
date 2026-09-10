EXP NO:11 C PROGRAM TO DISPLAY STACK ELEMENTS USING AN ARRAY.

Aim:
To write a C program to display stack elements using an array.
Algorithm:
1.	Include Necessary Header Files
2.	Declare Global Variables
3.	Define the Display Function
4.	Main Function (or Other Relevant Code)
5.	Initialize the stack and top as needed.
6.	Perform stack operations (push, pop, etc.).
7.	Use the display function to visualize the stack's contents
 
Program:

```
#include <stdio.h>
#define MAX 100
int stack[MAX];
int top = -1;
void push(int val) {
    if (top < MAX - 1) stack[++top] = val;
}
void display() {
    if (top == -1) {
        printf("Stack is empty\n");
        return;
    }
    for (int i = top; i >= 0; i--) printf("%d\n", stack[i]);
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

<img width="1499" height="878" alt="image" src="https://github.com/user-attachments/assets/407a77ab-7022-4a58-ab70-8bb47ec7badf" />

Result:
Thus, the program to display stack elements using an array is verified successfully.
 

EXP NO:12  PROGRAM TO PUSH THE GIVEN ELEMENT IN TO A STACK USING ARRAY.
Aim:
To create a C program to push the given element in to a stack using array.
Algorithm:
1.	Declare global variables for the stack size, top index, and the stack itself.
2.	Define the push function to add a floating-point number to the stack.
3.	Initialize the stack size, top index, and the stack itself.
4.	Call the push function as needed.
 
Program:

```
#include <stdio.h>
#define MAX 100
float stack[MAX];
int top = -1;
void push(float val) {
    if (top >= MAX - 1) {
        printf("Overflow\n");
        return;
    }
    stack[++top] = val;
}
int main() {
    push(10.5);
    push(20.5);
    push(30.5);
    for (int i = top; i >= 0; i--) printf("%.2f\n", stack[i]);
    return 0;
}
```
Output:

<img width="1479" height="888" alt="image" src="https://github.com/user-attachments/assets/1fd8f311-0262-4b6f-9584-9042c58ddc58" />

Result:
Thus, the program to push the given element in to a stack using array is verified successfully

 
EXP NO:13 C PROGRAM TO DISPLAY QUEUE ELEMENTS USING ARRAY.
Aim:
To write a C program to display queue elements using array

Algorithm:
1.	Declare global variables for the queue, rear, front, and iteration.
2.	Define the display function to print the elements of the queue.
3.	Initialize the queue, rear, and front as needed.
4.	Call the display function and perform other queue operations as needed.
 
Program:

```
#include <stdio.h>
#define MAX 100
int queue[MAX];
int front = -1, rear = -1;
void enqueue(int val) {
    if (rear >= MAX - 1) return;
    if (front == -1) front = 0;
    queue[++rear] = val;
}
void display() {
    if (front == -1 || front > rear) {
        printf("Queue is empty\n");
        return;
    }
    for (int i = front; i <= rear; i++) printf("%d\n", queue[i]);
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

<img width="1700" height="1018" alt="image" src="https://github.com/user-attachments/assets/632e7b9f-f0df-4d1b-af22-55ea4fe5d980" />

Result:
Thus, the program to display queue elements using array is verified successfully.


EXP NO:14 C PROGRAM TO INSERT ELEMENTS IN QUEUE USING ARRAY.
Aim:
To write a C program to insert elements in queue using array.

Algorithm:
1.	Declare global variables for the size, rear, front, and the queue itself.
2.	Define the enqueue function to add a float to the queue.
3.	Initialize the rear, front, and size of the queue as needed.
4.	Call the enqueue function as needed.

Program:

```
#include <stdio.h>
#define MAX 100
float queue[MAX];
int front = -1, rear = -1;
void enqueue(float val) {
    if (rear >= MAX - 1) {
        printf("Overflow\n");
        return;
    }
    if (front == -1) front = 0;
    queue[++rear] = val;
}
int main() {
    enqueue(1.1);
    enqueue(2.2);
    enqueue(3.3);
    for (int i = front; i <= rear; i++) printf("%.2f\n", queue[i]);
    return 0;
}
```
Output:

<img width="1532" height="903" alt="image" src="https://github.com/user-attachments/assets/3a9e7d2c-e1a9-4e1d-8946-0d9381d78268" />

Result:
Thus, the program to insert elements in queue using array is verified successfully.



 
EXP NO:15 C FUNCTION TO DELETE ELEMENTS IN QUEUE USING ARRAY



Aim:

To create a function in C that deletes an element from a queue implemented using an array.

Algorithm:

1.	Check if the Queue is Empty
o	If the front pointer is -1, it means the queue is empty, and there are no elements to delete. Print a message indicating that the queue is empty.
2.	Delete the Front Element
o	If the queue is not empty, the element at the front index is deleted.
o	Increment the front pointer by 1 to remove the element and point to the next element in the queue.
3.	Check if the Queue Becomes Empty After Deletion:
o	After deletion, check if the front pointer has passed the rear pointer (front > rear). If this is true, reset both front and rear to -1, indicating that the queue is now empty.
4.	End the Function.



Program:

```
#include <stdio.h>
#define MAX 100
int queue[MAX];
int front = -1, rear = -1;
void dequeue() {
    if (front == -1) {
        printf("Queue is empty\n");
        return;
    }
    front++;
    if (front > rear) {
        front = -1;
        rear = -1;
    }
}
int main() {
    front = 0; rear = 2;
    queue[0] = 10; queue[1] = 20; queue[2] = 30;
    dequeue();
    for (int i = front; i <= rear; i++) printf("%d\n", queue[i]);
    return 0;
}
```

Output:

<img width="1556" height="872" alt="image" src="https://github.com/user-attachments/assets/16de1f21-b029-4a25-b9d2-81e15902b3b7" />


Result:
Thus, the function that deletes an element from a queue implemented using an array is verified successfully.
