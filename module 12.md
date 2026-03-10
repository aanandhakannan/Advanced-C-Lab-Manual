

## EXP NO 26: C PROGRAM TO DISPLAY STACK ELEMENTS USING LINKED LIST.
##  Aim:
To write a C program to display stack elements using linked list.

## Algorithm:
1.	Define a structure Node with two members: data to store the integer value and next to point to the next node in the linked list.
2.	Declare a global variable head representing the starting node of the linked list.
3.	Define a function display to print the elements of the linked list.
4.	Declare a pointer p and initialize it with the head of the linked list.
5.	Use a while loop to traverse the linked list:
6.	Print the data of the current node.
7.	Move to the next node using the next pointer.
 
## Program:

```
#include <stdio.h>
#include <stdlib.h>

struct Node
{
    int data;
    struct Node* next;
};

struct Node* head = NULL;

void push(int value)
{
    struct Node* newNode = (struct Node*)malloc(sizeof(struct Node));
    newNode->data = value;
    newNode->next = head;
    head = newNode;
}

void display()
{
    struct Node* p = head;
    if(p == NULL)
    {
        printf("Stack is empty\n");
        return;
    }

    printf("Stack elements: ");
    while(p != NULL)
    {
        printf("%d ", p->data);
        p = p->next;
    }
    printf("\n");
}

int main()
{
    int n, value;
    scanf("%d", &n);

    for(int i = 0; i < n; i++)
    {
        scanf("%d", &value);
        push(value);
    }

    display();

    return 0;
}
```

## Output:

<img width="594" height="254" alt="image" src="https://github.com/user-attachments/assets/4d2ad7e2-3689-474d-a108-d61ebb1d9e84" />



## Result:
Thus, the program to display stack elements using linked list is verified successfully. 



## EXP.NO 27: C PROGRAM TO POP AN ELEMENT FROM THE GIVEN STACK USING 
LINKED LIST.
## Aim:
To write a C program to pop an element from the given stack using liked list.

## Algorithm:
1.	Check for Empty Stack
2.	If head is equal to NULL, Print "Stack is empty."
3.	Else Proceed to the next step.
4.	Set head to point to the next node in the stack.
 
## Program:

```
#include <stdio.h>
#include <stdlib.h>

struct Node
{
    int data;
    struct Node* next;
};

struct Node* head = NULL;

void push(int value)
{
    struct Node* newNode = (struct Node*)malloc(sizeof(struct Node));
    newNode->data = value;
    newNode->next = head;
    head = newNode;
}

void pop()
{
    if(head == NULL)
    {
        printf("Stack is empty\n");
        return;
    }
    struct Node* temp = head;
    head = head->next;
    free(temp);
}

void display()
{
    struct Node* p = head;
    if(p == NULL)
    {
        printf("Stack is empty\n");
        return;
    }

    while(p != NULL)
    {
        printf("%d ", p->data);
        p = p->next;
    }
    printf("\n");
}

int main()
{
    int n, value;
    scanf("%d", &n);

    for(int i = 0; i < n; i++)
    {
        scanf("%d", &value);
        push(value);
    }

    pop();

    display();

    return 0;
}
```

## Output:

<img width="508" height="231" alt="image" src="https://github.com/user-attachments/assets/cd0aabc4-2102-477d-967b-13628b18b906" />




## Result:
Thus, the program to pop an element from the given stack using liked list is verified successfully.

 
## EXP NO:28 C PROGRAM TO DISPLAY QUEUE ELEMENTS USING LINKED LIST.
## Aim:
To write a C program to display queue elements using linked list.
## Algorithm:
1.	Check if Queue is Empty
2.	Display Queue Elements
3.	Print the data of the current node pointed to by front
4.	Update front to point to the next node.
5.	End the display function.
 
## Program:

```
#include <stdio.h>
#include <stdlib.h>

struct Node
{
    int data;
    struct Node* next;
};

struct Node* front = NULL;
struct Node* rear = NULL;

void enqueue(int value)
{
    struct Node* newNode = (struct Node*)malloc(sizeof(struct Node));
    newNode->data = value;
    newNode->next = NULL;
    if(rear == NULL)
    {
        front = rear = newNode;
        return;
    }
    rear->next = newNode;
    rear = newNode;
}

void display()
{
    struct Node* p = front;
    if(p == NULL)
    {
        printf("Queue is empty\n");
        return;
    }
    while(p != NULL)
    {
        printf("%d ", p->data);
        p = p->next;
    }
    printf("\n");
}

int main()
{
    int n, value;
    scanf("%d", &n);

    for(int i = 0; i < n; i++)
    {
        scanf("%d", &value);
        enqueue(value);
    }

    display();

    return 0;
}
```
## Output:
<img width="812" height="251" alt="image" src="https://github.com/user-attachments/assets/dd5a9a0c-3b9d-45ae-acf9-e8c47ee83f19" />


## Result:
Thus, the program to display queue elements using linked list is verified successfully.


 
## EXP NO:29 C PROGRAM TO INSERT ELEMENTS IN QUEUE USING LINKED LIST

## Aim:
To write a C program to insert elements in queue using linked list

## Algorithm:
1.	Allocate Memory for New Node
2.	Set Data and Next Pointer
3.	Check if Queue is Empty
4.	Set both front and rear to point to the new node p.
5.	Set the next pointer of the current rear to point to the new node p.
6.	End of Enqueue Operation
 
## Program:

```
#include <stdio.h>
#include <stdlib.h>

struct Node
{
    int data;
    struct Node* next;
};

struct Node* front = NULL;
struct Node* rear = NULL;

void enqueue(int value)
{
    struct Node* p = (struct Node*)malloc(sizeof(struct Node));
    p->data = value;
    p->next = NULL;

    if(rear == NULL)
    {
        front = rear = p;
        return;
    }

    rear->next = p;
    rear = p;
}

void display()
{
    struct Node* p = front;
    if(p == NULL)
    {
        printf("Queue is empty\n");
        return;
    }

    while(p != NULL)
    {
        printf("%d ", p->data);
        p = p->next;
    }
    printf("\n");
}

int main()
{
    int n, value;
    scanf("%d", &n);

    for(int i = 0; i < n; i++)
    {
        scanf("%d", &value);
        enqueue(value);
    }

    display();

    return 0;
}
```

## Output:
<img width="600" height="217" alt="image" src="https://github.com/user-attachments/assets/ebb9d054-a619-4867-886a-f231078e4c74" />


## Result:
Thus, the program to insert elements in queue using linked list is verified successfully.



## EXP NO:30 C FUNCTION TO FIND THE PEEK OF QUEUE USING LINKED LIST.


## Aim:

The aim of this function is to retrieve the "peek" (the front element) of a queue implemented using a linked list

## Algorithm:

1.	Check if the queue is empty:
o	If the queue is empty (i.e., the front pointer is NULL), return an error or a message indicating that the queue is empty.
2.	Access the front element:
o	If the queue is not empty, return the data stored in the front node of the linked list (i.e., the element at the head of the queue).

## Program:

```
#include <stdio.h>
#include <stdlib.h>

struct Node
{
    int data;
    struct Node* next;
};

struct Node* front = NULL;
struct Node* rear = NULL;

void enqueue(int value)
{
    struct Node* p = (struct Node*)malloc(sizeof(struct Node));
    p->data = value;
    p->next = NULL;

    if(rear == NULL)
    {
        front = rear = p;
        return;
    }

    rear->next = p;
    rear = p;
}

int peek()
{
    if(front == NULL)
    {
        printf("Queue is empty\n");
        return -1;
    }
    return front->data;
}

int main()
{
    int n, value;
    scanf("%d", &n);

    for(int i = 0; i < n; i++)
    {
        scanf("%d", &value);
        enqueue(value);
    }

    int front_value = peek();
    if(front_value != -1)
        printf("Front element: %d\n", front_value);

    return 0;
}
```

## Output:

<img width="706" height="237" alt="image" src="https://github.com/user-attachments/assets/efdad485-abde-463f-b1e4-df9ca087a84d" />




## Result:

Thus, the program to retrieve the "peek" (the front element) of a queue implemented using a linked list is verified successfully.


