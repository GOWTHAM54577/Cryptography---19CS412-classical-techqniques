# Rail Fence Cipher
Rail Fence Cipher using with different key values

# AIM:

To develop a simple C program to implement Rail Fence Cipher.

## DESIGN STEPS:

### Step 1:

Design of Rail Fence Cipher algorithnm 

### Step 2:

Implementation using C or pyhton code

### Step 3:

Testing algorithm with different key values. 
ALGORITHM DESCRIPTION:
In the rail fence cipher, the plaintext is written downwards and diagonally on successive "rails" of an imaginary fence, then moving up when we reach the bottom rail. When we reach the top rail, the message is written downwards again until the whole plaintext is written out. The message is then read off in rows.

## PROGRAM:
```
Developed by : GOWTHAM N
Register no  : 212223100008
```
```
#include<stdio.h>
#include<string.h>
#include<stdlib.h>
int main() {
    int i, j, len, rails, count, direction;
    char code[100][1000]; // Changed to char to store characters directly
    char str[1000];
    printf("Enter a Secret Message: ");
    fgets(str, sizeof(str), stdin);  // Using fgets instead of gets
    str[strcspn(str, "\n")] = 0;     // Removing the newline added by fgets
    len = strlen(str);
    printf("Enter number of rails: ");
    scanf("%d", &rails);
    // Initialize the matrix with empty characters
    for (i = 0; i < rails; i++) {
        for (j = 0; j < len; j++) {
            code[i][j] = '\0';
        }
    }
    count = 0;
    direction = 1; // 1 for moving down, -1 for moving up
    // Fill the matrix with the characters following the zigzag pattern
    for (j = 0, i = 0; j < len; j++) {
        code[i][j] = str[j];
        if (i == 0) {
            direction = 1; // Move down when at the top
        } else if (i == rails - 1) {
            direction = -1; // Move up when at the bottom
        }

        i += direction; // Move up or down the rails
    }
    // Print the encrypted message by reading the matrix row-wise
    printf("Encrypted Message: ");
    for (i = 0; i < rails; i++) {
        for (j = 0; j < len; j++) {
            if (code[i][j] != '\0') {
                printf("%c", code[i][j]);
            }
        }
    }
    printf("\n");
    return 0;
}


```
## OUTPUT:

![image](https://github.com/user-attachments/assets/6db1a40f-cb7e-4c6f-b28b-e947a84ce4f0)

## RESULT:
The program is executed successfully
