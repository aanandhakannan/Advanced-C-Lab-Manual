

## EXP NO:21 C PROGRAM TO CREATE A FUNCTION TO FIND THE GREATEST NUMBER
## Aim:
To write a C program to create a function to find the greatest number

## Algorithm:
1.	Include the necessary header #include <stdio.h>.
2.	Use a series of if and else if statements to compare the values and return the maximum among them.
3.	Declare variables n1, n2, n3, n4, and greater to store user input and the result.
4.	Use scanf to take four integers as input.
5.	Call the max_of_four function with the input integers and store the result in the greater variable
 
## Program:
```
#include <stdio.h>

// Function to find the greatest of four numbers
int max_of_four(int a, int b, int c, int d)
{
    int max = a;

    if(b > max)
        max = b;
    if(c > max)
        max = c;
    if(d > max)
        max = d;

    return max;
}

int main()
{
    int n1, n2, n3, n4, greater;

    printf("Enter four numbers: ");
    scanf("%d %d %d %d", &n1, &n2, &n3, &n4);

    greater = max_of_four(n1, n2, n3, n4);

    printf("The greatest number is: %d\n", greater);

    return 0;
}
```

## Output:
<img width="695" height="258" alt="image" src="https://github.com/user-attachments/assets/13fae08d-1e33-4d6e-8ea4-498fdadb6440" />


## Result:
Thus, the program  that create a function to find the greatest number is verified successfully.


 
## EXP NO:22 C PROGRAM TO PRINT THE MAXIMUM VALUES FOR THE AND, OR AND  XOR COMPARISONS
## Aim:
To write a C program to print the maximum values for the AND, OR and XOR comparisons

## Algorithm:
1.	Define a function calculate_the_max that takes two integers n and k as parameters.
2.	Declare variables a, o, and x to store the maximum values for AND, OR, and XOR operations, respectively.
3.	Use nested loops to iterate through pairs of integers (i, j) from 1 to n.
4.	Within the loops, check conditions for AND, OR, and XOR operations and update the corresponding maximum values (a, o, x).
5.	Declare variables n and k to store user input.
6.	Use scanf to take two integers as input.
7.	Call the calculate_the_max function with input values.
 
## Program:
```
#include <stdio.h>

void calculate_the_max(int n, int k)
{
    int max_and = 0, max_or = 0, max_xor = 0;
    int i, j;

    for(i = 1; i <= n; i++)
    {
        for(j = i + 1; j <= n; j++)
        {
            int and_val = i & j;
            int or_val  = i | j;
            int xor_val = i ^ j;

            if(and_val < k && and_val > max_and)
                max_and = and_val;

            if(or_val < k && or_val > max_or)
                max_or = or_val;

            if(xor_val < k && xor_val > max_xor)
                max_xor = xor_val;
        }
    }

    printf("Maximum AND value less than %d: %d\n", k, max_and);
    printf("Maximum OR value less than %d: %d\n", k, max_or);
    printf("Maximum XOR value less than %d: %d\n", k, max_xor);
}

int main()
{
    int n, k;

    printf("Enter values for n and k: ");
    scanf("%d %d", &n, &k);

    calculate_the_max(n, k);

    return 0;
}
```

## Output:
<img width="796" height="251" alt="image" src="https://github.com/user-attachments/assets/ecd23ac7-573d-4632-8143-6132c2e9b7d3" />


## Result:
Thus, the program to print the maximum values for the AND, OR and XOR comparisons
is verified successfully.


 
## EXP NO:23 C PROGRAM TO WRITE THE LOGIC FOR THE REQUESTS
## Aim:
To write a C program to write the logic for the requests

## Algorithm:
1.	Declare variables noshel and noque to store the number of shelves and the number of queries, respectively.
2.	Use scanf to take two integers as input for the number of shelves and queries.
3.	Declare a 2D array shelarr to represent shelves and books, and an array nobookarr to store the number of books on each shelf.
4.	Declare variables k and c to keep track of the book index and the total number of books.
5.	Use a for loop to iterate over the queries.
 
## Program:
#include <stdio.h>

int main()
{
    int noshel, noque;
    printf("Enter number of shelves and number of queries: ");
    scanf("%d %d", &noshel, &noque);

    int shelarr[noshel][100]; 
    int nobookarr[noshel];
    for(int i = 0; i < noshel; i++)
        nobookarr[i] = 0;

    int query_type, x, y;

    for(int q = 0; q < noque; q++)
    {
        printf("Enter query type (1 or 2): ");
        scanf("%d", &query_type);

        if(query_type == 1)
        {
            // Add a book to a shelf
            printf("Enter shelf number and number of pages: ");
            scanf("%d %d", &x, &y); // x = shelf index, y = pages
            shelarr[x][nobookarr[x]] = y;
            nobookarr[x]++;
        }
        else if(query_type == 2)
        {
            // Print number of books on a shelf
            printf("Enter shelf number to check: ");
            scanf("%d", &x);
            printf("Number of books on shelf %d: %d\n", x, nobookarr[x]);
        }
        else
        {
            printf("Invalid query\n");
        }
    }

    return 0;
}

## Output:
<img width="785" height="262" alt="image" src="https://github.com/user-attachments/assets/a349111a-541d-4446-87ec-bc7670de11f1" />



## Result:
Thus, the program to write the logic for the requests is verified successfully.


 
## EXP NO:24 C PROGRAM PRINT THE SUM OF THE INTEGERS IN THE ARRAY.
## Aim:
To write a C program print the sum of the integers in the array.

## Algorithm:
1.	Declare a variable n to store the number of integers.
2.	Use scanf to take an integer n as input.
3.	Declare an array a of size n to store the integers.
4.	Declare a variable sum and initialize it to zero.
5.	Use a for loop to iterate n times:
6.	Use scanf to input each integer and add it to the sum.
7.	Print the final sum using printf.



## Program:
```
#include <stdio.h>

int main()
{
    int n, sum = 0;

    printf("Enter number of integers: ");
    scanf("%d", &n);

    int a[n];

    printf("Enter %d integers: ", n);
    for(int i = 0; i < n; i++)
    {
        scanf("%d", &a[i]);
        sum += a[i];
    }

    printf("Sum of the integers: %d\n", sum);

    return 0;
}
```

## Output:
<img width="580" height="300" alt="image" src="https://github.com/user-attachments/assets/77cf2ea7-a640-4fd8-8206-ba051ba1522f" />


 


## Result:
Thus, the program prints the sum of the integers in the array is verified successfully.


 
## EXP NO 25: C PROGRAM TO COUNT THE NUMBER OF WORDS IN A      SENTENCE



## Aim:

To write a C program that counts the number of words in a given sentence.

## Algorithm:

1.	Input the sentence: Take a sentence from the user.
2.	Initialize a counter variable: This will keep track of the number of words.
3.	Process each character of the sentence:
o	Iterate through the sentence, checking each character.
o	If a character is not a space, it may belong to a word. If it's the first non-space character after a space or at the start, increment the word count.
4.	Handle spaces and punctuation: Skip over spaces, punctuation marks, and consider each word as a sequence of characters separated by spaces.
5.	Display the result: After processing the sentence, output the total word count.



## Program:
```
#include <stdio.h>
#include <ctype.h>

int main()
{
    char sentence[200];
    int i = 0, word_count = 0;
    int in_word = 0;

    printf("Enter a sentence: ");
    fgets(sentence, sizeof(sentence), stdin);

    while(sentence[i] != '\0')
    {
        if(!isspace(sentence[i]) && sentence[i] != '\n')
        {
            if(!in_word)
            {
                word_count++;
                in_word = 1;
            }
        }
        else
        {
            in_word = 0;
        }
        i++;
    }

    printf("Number of words: %d\n", word_count);

    return 0;
}
```

## Output:
<img width="628" height="225" alt="image" src="https://github.com/user-attachments/assets/244c3e96-f433-4d5e-90a6-de851ffc7ca2" />



## Result:

Thus, the program that counts the number of words in a given sentence is verified 
successfully.
