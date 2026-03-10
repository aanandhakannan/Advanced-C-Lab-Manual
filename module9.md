## EXP NO:11 C PROGRAM TO DISPLAY STACK ELEMENTS USING AN ARRAY.

## Aim:
To write a C program to display stack elements using an array.
## Algorithm:
1.	Include Necessary Header Files
2.	Declare Global Variables
3.	Define the Display Function
4.	Main Function (or Other Relevant Code)
5.	Initialize the stack and top as needed.
6.	Perform stack operations (push, pop, etc.).
7.	Use the display function to visualize the stack's contents
 
## Program:

```
#include <stdio.h>
#define MAX 50

int stack[MAX];
int top = -1;

// Function to push an element onto the stack
void push(int x)
{
    if(top == MAX - 1)
    {
        printf("Stack Overflow\n");
        return;
    }
    stack[++top] = x;
}

// Function to pop an element from the stack
int pop()
{
    if(top == -1)
    {
        printf("Stack Underflow\n");
        return -1;
    }
    return stack[top--];
}

// Function to display stack elements
void display()
{
    if(top == -1)
    {
        printf("Stack is empty\n");
        return;
    }
    printf("Stack elements: ");
    for(int i = 0; i <= top; i++)
        printf("%d ", stack[i]);
    printf("\n");
}

int main()
{
    int choice, value;

    while(1)
    {
        printf("\n1. Push\n2. Pop\n3. Display\n4. Exit\n");
        printf("Enter your choice: ");
        scanf("%d", &choice);

        switch(choice)
        {
            case 1:
                printf("Enter value to push: ");
                scanf("%d", &value);
                push(value);
                break;

            case 2:
                value = pop();
                if(value != -1)
                    printf("Popped element: %d\n", value);
                break;

            case 3:
                display();
                break;

            case 4:
                return 0;

            default:
                printf("Invalid choice\n");
        }
    }

    return 0;
}
```

## Output:

<img width="686" height="251" alt="image" src="https://github.com/user-attachments/assets/26625098-a05c-4da1-821b-d6788ed72ac1" />




## Result:
Thus, the program to display stack elements using an array is verified successfully.
 

## EXP NO:12  PROGRAM TO PUSH THE GIVEN ELEMENT IN TO A STACK USING ARRAY.
## Aim:
To create a C program to push the given element in to a stack using array.
## Algorithm:
1.	Declare global variables for the stack size, top index, and the stack itself.
2.	Define the push function to add a floating-point number to the stack.
3.	Initialize the stack size, top index, and the stack itself.
4.	Call the push function as needed.
 
## Program:

```
#include <stdio.h>
#define MAX 50

float stack[MAX];
int top = -1;

// Function to push an element onto the stack
void push(float value)
{
    if(top == MAX - 1)
    {
        printf("Stack Overflow\n");
        return;
    }
    stack[++top] = value;
    printf("Pushed %.2f onto the stack\n", value);
}

int main()
{
    int n, i;
    float value;

    printf("Enter number of elements to push: ");
    scanf("%d", &n);

    for(i = 0; i < n; i++)
    {
        printf("Enter element %d: ", i + 1);
        scanf("%f", &value);
        push(value);
    }

    printf("Stack contents: ");
    for(i = 0; i <= top; i++)
        printf("%.2f ", stack[i]);
    printf("\n");

    return 0;
}
```

## Output:

<img width="880" height="219" alt="image" src="https://github.com/user-attachments/assets/4ac8ff11-4125-4f03-896f-50d0fbe86edb" />





## Result:
Thus, the program to push the given element in to a stack using array is verified successfully


 
## EXP NO:13 C PROGRAM TO DISPLAY QUEUE ELEMENTS USING ARRAY.
Aim:
To write a C program to display queue elements using array

Algorithm:
1.	Declare global variables for the queue, rear, front, and iteration.
2.	Define the display function to print the elements of the queue.
3.	Initialize the queue, rear, and front as needed.
4.	Call the display function and perform other queue operations as needed.
 
## Program:

```
#include <stdio.h>
#define MAX 50

int queue[MAX];
int front = -1, rear = -1;

// Function to enqueue an element
void enqueue(int value)
{
    if(rear == MAX - 1)
    {
        printf("Queue Overflow\n");
        return;
    }
    if(front == -1)
        front = 0;
    queue[++rear] = value;
    printf("Enqueued: %d\n", value);
}

// Function to dequeue an element
int dequeue()
{
    if(front == -1 || front > rear)
    {
        printf("Queue Underflow\n");
        return -1;
    }
    return queue[front++];
}

// Function to display queue elements
void display()
{
    if(front == -1 || front > rear)
    {
        printf("Queue is empty\n");
        return;
    }
    printf("Queue elements: ");
    for(int i = front; i <= rear; i++)
        printf("%d ", queue[i]);
    printf("\n");
}

int main()
{
    int choice, value;

    while(1)
    {
        printf("\n1. Enqueue\n2. Dequeue\n3. Display\n4. Exit\n");
        printf("Enter your choice: ");
        scanf("%d", &choice);

        switch(choice)
        {
            case 1:
                printf("Enter value to enqueue: ");
                scanf("%d", &value);
                enqueue(value);
                break;

            case 2:
                value = dequeue();
                if(value != -1)
                    printf("Dequeued element: %d\n", value);
                break;

            case 3:
                display();
                break;

            case 4:
                return 0;

            default:
                printf("Invalid choice\n");
        }
    }

    return 0;
}
```

## Output:

<img width="500" height="236" alt="image" src="https://github.com/user-attachments/assets/3b45ac5d-a74b-4e95-bc4d-9e786308bedb" />



## Result:
Thus, the program to display queue elements using array is verified successfully.


 
## EXP NO:14 C PROGRAM TO INSERT ELEMENTS IN QUEUE USING ARRAY.
Aim:
To write a C program to insert elements in queue using array.

## Algorithm:
1.	Declare global variables for the size, rear, front, and the queue itself.
2.	Define the enqueue function to add a float to the queue.
3.	Initialize the rear, front, and size of the queue as needed.
4.	Call the enqueue function as needed.

## Program:
```
#include <stdio.h>
#define MAX 50

float queue[MAX];
int front = -1, rear = -1;

// Function to insert (enqueue) an element into the queue
void enqueue(float value)
{
    if(rear == MAX - 1)
    {
        printf("Queue Overflow\n");
        return;
    }

    if(front == -1)
        front = 0;

    queue[++rear] = value;
    printf("Inserted %.2f into the queue\n", value);
}

int main()
{
    int n, i;
    float value;

    printf("Enter number of elements to insert: ");
    scanf("%d", &n);

    for(i = 0; i < n; i++)
    {
        printf("Enter element %d: ", i + 1);
        scanf("%f", &value);
        enqueue(value);
    }

    printf("Queue elements: ");
    for(i = front; i <= rear; i++)
        printf("%.2f ", queue[i]);
    printf("\n");

    return 0;
}
```

## Output:
<img width="782" height="239" alt="image" src="https://github.com/user-attachments/assets/af8b2ed7-9c49-4374-a8e0-da3cfcbf09f9" />


## Result:
Thus, the program to insert elements in queue using array is verified successfully.



 
## EXP NO:15 C FUNCTION TO DELETE ELEMENTS IN QUEUE USING ARRAY



## Aim:

To create a function in C that deletes an element from a queue implemented using an array.

## Algorithm:

1.	Check if the Queue is Empty
o	If the front pointer is -1, it means the queue is empty, and there are no elements to delete. Print a message indicating that the queue is empty.
2.	Delete the Front Element
o	If the queue is not empty, the element at the front index is deleted.
o	Increment the front pointer by 1 to remove the element and point to the next element in the queue.
3.	Check if the Queue Becomes Empty After Deletion:
o	After deletion, check if the front pointer has passed the rear pointer (front > rear). If this is true, reset both front and rear to -1, indicating that the queue is now empty.
4.	End the Function.



## Program:

```
#include <stdio.h>
#define MAX 50

float queue[MAX];
int front = -1, rear = -1;

// Function to delete (dequeue) an element from the queue
void dequeue()
{
    if(front == -1)
    {
        printf("Queue is empty. No elements to delete.\n");
        return;
    }

    printf("Deleted element: %.2f\n", queue[front]);
    front++;

    // Reset front and rear if queue becomes empty
    if(front > rear)
    {
        front = rear = -1;
    }
}

int main()
{
    int n, i;
    float value;

    // Example: Inserting elements
    printf("Enter number of elements to insert: ");
    scanf("%d", &n);

    for(i = 0; i < n; i++)
    {
        printf("Enter element %d: ", i + 1);
        scanf("%f", &value);

        if(rear == MAX - 1)
        {
            printf("Queue Overflow\n");
            break;
        }

        if(front == -1)
            front = 0;

        queue[++rear] = value;
    }

    // Example: Deleting all elements
    printf("\nDeleting elements from the queue:\n");
    while(front != -1)
    {
        dequeue();
    }

    return 0;
}
```
## Output:

<img width="654" height="229" alt="image" src="https://github.com/user-attachments/assets/39bc945f-bc03-42b5-b629-f3179993c0f0" />


## Result:
Thus, the function that deletes an element from a queue implemented using an array is verified successfully.
