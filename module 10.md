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

struct Node
{
    char data;
    struct Node *next;
};

void search(struct Node *head, char key)
{
    int pos = 1;
    while (head != NULL)
    {
        if (head->data == key)
        {
            printf("Element '%c' found at position %d\n", key, pos);
            return;
        }
        head = head->next;
        pos++;
    }
    printf("Element '%c' not found in the linked list\n", key);
}

int main()
{
    struct Node *head = NULL, *second = NULL, *third = NULL;
    char key;

    head = (struct Node *)malloc(sizeof(struct Node));
    second = (struct Node *)malloc(sizeof(struct Node));
    third = (struct Node *)malloc(sizeof(struct Node));

    head->data = 'A';
    head->next = second;

    second->data = 'B';
    second->next = third;

    third->data = 'C';
    third->next = NULL;

    printf("Linked List Elements: A -> B -> C\n");
    printf("Enter the element to search: ");
    scanf(" %c", &key);

    search(head, key);

    return 0;
}
```

Output:

<img width="765" height="209" alt="image" src="https://github.com/user-attachments/assets/6f2d10c1-f467-4077-b7a9-f12069b9d2b7" />




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

struct Node
{
    char data;
    struct Node *next;
};

struct Node *insert(struct Node *head, char value)
{
    struct Node *newNode, *temp;

    newNode = (struct Node *)malloc(sizeof(struct Node));
    newNode->data = value;
    newNode->next = NULL;

    if (head == NULL)
    {
        head = newNode;
    }
    else
    {
        temp = head;
        while (temp->next != NULL)
        {
            temp = temp->next;
        }
        temp->next = newNode;
    }

    return head;
}

void display(struct Node *head)
{
    struct Node *temp = head;
    while (temp != NULL)
    {
        printf("%c -> ", temp->data);
        temp = temp->next;
    }
    printf("NULL\n");
}

int main()
{
    struct Node *head = NULL;
    char value;

    head = insert(head, 'A');
    head = insert(head, 'B');
    head = insert(head, 'C');

    printf("Linked list before insertion:\n");
    display(head);

    printf("Enter a character to insert: ");
    scanf(" %c", &value);

    head = insert(head, value);

    printf("Linked list after insertion:\n");
    display(head);

    return 0;
}
```

Output:

<img width="451" height="196" alt="image" src="https://github.com/user-attachments/assets/ba3a2f1f-d7a7-4455-b991-0b349a96060d" />


 
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

struct Node
{
    int data;
    struct Node *prev;
    struct Node *next;
};

void traverse(struct Node *head)
{
    struct Node *temp = head;

    while (temp != NULL)
    {
        printf("%d ", temp->data);
        temp = temp->next;
    }
}

int main()
{
    struct Node *head = NULL;
    struct Node *second = NULL;
    struct Node *third = NULL;

    head = (struct Node *)malloc(sizeof(struct Node));
    second = (struct Node *)malloc(sizeof(struct Node));
    third = (struct Node *)malloc(sizeof(struct Node));

    head->data = 10;
    head->prev = NULL;
    head->next = second;

    second->data = 20;
    second->prev = head;
    second->next = third;

    third->data = 30;
    third->prev = second;
    third->next = NULL;

    printf("Doubly Linked List elements are: ");
    traverse(head);

    return 0;
}
```

Output:

<img width="482" height="152" alt="image" src="https://github.com/user-attachments/assets/6fa7f3e6-a468-4aa2-879c-795f128c94dc" />



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

struct Node
{
    int data;
    struct Node *prev;
    struct Node *next;
};

struct Node* insert(struct Node *head, int value)
{
    struct Node *newNode, *temp;

    newNode = (struct Node*)malloc(sizeof(struct Node));
    newNode->data = value;
    newNode->prev = NULL;
    newNode->next = NULL;

    if (head == NULL)
    {
        head = newNode;
    }
    else
    {
        temp = head;
        while (temp->next != NULL)
        {
            temp = temp->next;
        }
        temp->next = newNode;
        newNode->prev = temp;
    }

    return head;
}

void display(struct Node *head)
{
    struct Node *temp = head;
    while (temp != NULL)
    {
        printf("%d ", temp->data);
        temp = temp->next;
    }
}

int main()
{
    struct Node *head = NULL;

    head = insert(head, 10);
    head = insert(head, 20);
    head = insert(head, 30);
    head = insert(head, 40);

    printf("Doubly Linked List after insertion: ");
    display(head);

    return 0;
}
```

Output:
<img width="762" height="215" alt="image" src="https://github.com/user-attachments/assets/967d608a-0b41-4431-98f7-98193b1cc8d4" />


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

struct Node
{
    int data;
    struct Node *next;
};

struct Node* deleteElement(struct Node *head, int key)
{
    struct Node *temp = head;
    struct Node *prev = NULL;

    if (head == NULL)
    {
        printf("Linked list is empty\n");
        return head;
    }

    if (head->data == key)
    {
        temp = head;
        head = head->next;
        free(temp);
        printf("Element %d deleted\n", key);
        return head;
    }

    while (temp != NULL && temp->data != key)
    {
        prev = temp;
        temp = temp->next;
    }

    if (temp == NULL)
    {
        printf("Element %d not found in the list\n", key);
        return head;
    }

    prev->next = temp->next;
    free(temp);
    printf("Element %d deleted\n", key);

    return head;
}

void display(struct Node *head)
{
    struct Node *temp = head;
    while (temp != NULL)
    {
        printf("%d -> ", temp->data);
        temp = temp->next;
    }
    printf("NULL\n");
}

int main()
{
    struct Node *head = NULL;
    struct Node *first = NULL;
    struct Node *second = NULL;
    struct Node *third = NULL;

    first = (struct Node *)malloc(sizeof(struct Node));
    second = (struct Node *)malloc(sizeof(struct Node));
    third = (struct Node *)malloc(sizeof(struct Node));

    first->data = 10;
    first->next = second;

    second->data = 20;
    second->next = third;

    third->data = 30;
    third->next = NULL;

    head = first;

    printf("Linked list before deletion: ");
    display(head);

    head = deleteElement(head, 20);

    printf("Linked list after deletion: ");
    display(head);

    return 0;
}
```

Output:

<img width="784" height="249" alt="image" src="https://github.com/user-attachments/assets/b4857cb0-5906-4643-85a1-116f27a7515e" />






Result:
Thus, the function that deletes a given element from a linked list is verified successfully.





