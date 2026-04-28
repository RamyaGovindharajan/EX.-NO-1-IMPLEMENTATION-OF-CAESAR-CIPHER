# EX. NO: 1(A) : IMPLEMENTATION OF CAESAR CIPHER

## AIM:
To implement the simple substitution technique named Caesar cipher using C language.

## ALOGORITHM:

STEP-1: Read the plain text from the user.

STEP-2: Read the key value from the user.

STEP-3: If the key is positive then encrypt the text by adding the key with each character in the plain text.

STEP-4: Else subtract the key from the plain text.

STEP-5: Display the cipher text obtained above.

## PROGRAM:

```
#include <stdio.h>
#include <ctype.h>
#include <string.h>

void encrypt(char text[], int key) {
    for (int i = 0; text[i] != '\0'; i++) {
        char ch = text[i];

        if (isupper(ch)) {
            text[i] = ((ch - 'A' + key) % 26) + 'A';
        }
        else if (islower(ch)) {
            text[i] = ((ch - 'a' + key) % 26) + 'a';
        }
    }
}

void decrypt(char text[], int key) {
    for (int i = 0; text[i] != '\0'; i++) {
        char ch = text[i];

        if (isupper(ch)) {
            text[i] = ((ch - 'A' - key + 26) % 26) + 'A';
        }
        else if (islower(ch)) {
            text[i] = ((ch - 'a' - key + 26) % 26) + 'a';
        }
    }
}

int main() {
    char text[100];
    int key;

    printf("Enter the plain text: ");
    fgets(text, sizeof(text), stdin);

    printf("Enter the key value: ");
    scanf("%d", &key);

    printf("\nPLAIN TEXT: %s", text);

    encrypt(text, key);
    printf("ENCRYPTED TEXT: %s", text);

    decrypt(text, key);
    printf("DECRYPTED TEXT: %s", text);

    return 0;
}
```

## OUTPUT:


<img width="1320" height="963" alt="Screenshot 2026-04-28 141558" src="https://github.com/user-attachments/assets/c2068077-b1f1-4b59-83fb-5ec4b72fff7b" />



## RESULT :
 Thus the implementation of ceasar cipher had been executed successfully.
