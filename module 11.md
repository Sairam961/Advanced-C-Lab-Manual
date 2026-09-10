

EXP NO:21 C PROGRAM TO CREATE A FUNCTION TO FIND THE GREATEST NUMBER
Aim:
To write a C program to create a function to find the greatest number

Algorithm:
1.	Include the necessary header #include <stdio.h>.
2.	Use a series of if and else if statements to compare the values and return the maximum among them.
3.	Declare variables n1, n2, n3, n4, and greater to store user input and the result.
4.	Use scanf to take four integers as input.
5.	Call the max_of_four function with the input integers and store the result in the greater variable
 
Program:
```
#include <stdio.h>
int max_of_four(int a, int b, int c, int d) {
    if (a >= b && a >= c && a >= d) return a;
    else if (b >= c && b >= d) return b;
    else if (c >= d) return c;
    else return d;
}
int main() {
    int n1, n2, n3, n4, greater;
    scanf("%d %d %d %d", &n1, &n2, &n3, &n4);
    greater = max_of_four(n1, n2, n3, n4);
    printf("%d\n", greater);
    return 0;
}
```
Output:

<img width="1593" height="663" alt="image" src="https://github.com/user-attachments/assets/bd939bda-c105-4eeb-9776-896672afdbcb" />

Result:
Thus, the program  that create a function to find the greatest number is verified successfully.


 
EXP NO:22 C PROGRAM TO PRINT THE MAXIMUM VALUES FOR THE AND, OR AND  XOR COMPARISONS
Aim:
To write a C program to print the maximum values for the AND, OR and XOR comparisons

Algorithm:
1.	Define a function calculate_the_max that takes two integers n and k as parameters.
2.	Declare variables a, o, and x to store the maximum values for AND, OR, and XOR operations, respectively.
3.	Use nested loops to iterate through pairs of integers (i, j) from 1 to n.
4.	Within the loops, check conditions for AND, OR, and XOR operations and update the corresponding maximum values (a, o, x).
5.	Declare variables n and k to store user input.
6.	Use scanf to take two integers as input.
7.	Call the calculate_the_max function with input values.
 
Program:
```
#include <stdio.h>
void calculate_the_max(int n, int k) {
    int a = 0, o = 0, x = 0;
    for (int i = 1; i <= n; i++) {
        for (int j = i + 1; j <= n; j++) {
            int and_val = i & j;
            int or_val = i | j;
            int xor_val = i ^ j;
            if (and_val < k && and_val > a) a = and_val;
            if (or_val < k && or_val > o) o = or_val;
            if (xor_val < k && xor_val > x) x = xor_val;
        }
    }
    printf("%d\n%d\n%d\n", a, o, x);
}
int main() {
    int n, k;
    scanf("%d %d", &n, &k);
    calculate_the_max(n, k);
    return 0;
}
```
Output:

<img width="1587" height="795" alt="image" src="https://github.com/user-attachments/assets/1dac5faa-db82-4f42-acdf-863603500c45" />

Result:
Thus, the program to print the maximum values for the AND, OR and XOR comparisons
is verified successfully.


 
EXP NO:23 C PROGRAM TO WRITE THE LOGIC FOR THE REQUESTS
Aim:
To write a C program to write the logic for the requests

Algorithm:
1.	Declare variables noshel and noque to store the number of shelves and the number of queries, respectively.
2.	Use scanf to take two integers as input for the number of shelves and queries.
3.	Declare a 2D array shelarr to represent shelves and books, and an array nobookarr to store the number of books on each shelf.
4.	Declare variables k and c to keep track of the book index and the total number of books.
5.	Use a for loop to iterate over the queries.
 
Program:
```
#include <stdio.h>
#include <stdlib.h>
int main() {
    int noshel, noque;
    scanf("%d %d", &noshel, &noque);
    int *nobookarr = (int*)calloc(noshel, sizeof(int));
    int **shelarr = (int**)malloc(noshel * sizeof(int*));
    for (int i = 0; i < noshel; i++) shelarr[i] = NULL;
    for (int i = 0; i < noque; i++) {
        int type;
        scanf("%d", &type);
        if (type == 1) {
            int x, y;
            scanf("%d %d", &x, &y);
            int k = nobookarr[x];
            shelarr[x] = (int*)realloc(shelarr[x], (k + 1) * sizeof(int));
            shelarr[x][k] = y;
            nobookarr[x]++;
        } else if (type == 2) {
            int x, y;
            scanf("%d %d", &x, &y);
            printf("%d\n", shelarr[x][y]);
        } else if (type == 3) {
            int x;
            scanf("%d", &x);
            printf("%d\n", nobookarr[x]);
        }
    }
    free(nobookarr);
    for (int i = 0; i < noshel; i++) if (shelarr[i]) free(shelarr[i]);
    free(shelarr);
    return 0;
}
```
Output:

<img width="1465" height="1076" alt="image" src="https://github.com/user-attachments/assets/d7613431-6d48-4967-b59f-54635c997edf" />


Result:
Thus, the program to write the logic for the requests is verified successfully.


 
EXP NO:24 C PROGRAM PRINT THE SUM OF THE INTEGERS IN THE ARRAY.
Aim:
To write a C program print the sum of the integers in the array.

Algorithm:
1.	Declare a variable n to store the number of integers.
2.	Use scanf to take an integer n as input.
3.	Declare an array a of size n to store the integers.
4.	Declare a variable sum and initialize it to zero.
5.	Use a for loop to iterate n times:
6.	Use scanf to input each integer and add it to the sum.
7.	Print the final sum using printf.


Program:
```
#include <stdio.h>
int main() {
    int n, sum = 0;
    scanf("%d", &n);
    int a[n];
    for (int i = 0; i < n; i++) {
        scanf("%d", &a[i]);
        sum += a[i];
    }
    printf("%d\n", sum);
    return 0;
}
```
Output:

<img width="1175" height="507" alt="image" src="https://github.com/user-attachments/assets/153a8131-acb9-4cba-b500-39f3b7795b59" />


Result:
Thus, the program prints the sum of the integers in the array is verified successfully.

 
EXP NO 25: C PROGRAM TO COUNT THE NUMBER OF WORDS IN A      SENTENCE


Aim:

To write a C program that counts the number of words in a given sentence.

Algorithm:

1.	Input the sentence: Take a sentence from the user.
2.	Initialize a counter variable: This will keep track of the number of words.
3.	Process each character of the sentence:
o	Iterate through the sentence, checking each character.
o	If a character is not a space, it may belong to a word. If it's the first non-space character after a space or at the start, increment the word count.
4.	Handle spaces and punctuation: Skip over spaces, punctuation marks, and consider each word as a sequence of characters separated by spaces.
5.	Display the result: After processing the sentence, output the total word count.
 

Program:
```
#include <stdio.h>
#include <string.h>
int main() {
    char str[1000];
    scanf("%[^\n]", str);
    int count = 0, inWord = 0;
    for (int i = 0; str[i] != '\0'; i++) {
        if (str[i] != ' ' && str[i] != '\t' && str[i] != '\n') {
            if (!inWord) {
                count++;
                inWord = 1;
            }
        } else {
            inWord = 0;
        }
    }
    printf("%d\n", count);
    return 0;
}
```
Output:

<img width="1500" height="767" alt="image" src="https://github.com/user-attachments/assets/0128a6c3-4686-4ef7-90de-9e354a4bf1e9" />



Result:

Thus, the program that counts the number of words in a given sentence is verified 
successfully.
