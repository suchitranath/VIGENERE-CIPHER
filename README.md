# VIGENERE-CIPHER
date: 29/03/2025
## AIM:
To implement the Vigenere Cipher substitution technique using C program.

## ALGORITHM:
STEP-1: Arrange the alphabets in row and column of a 26*26 matrix.
STEP-2: Circulate the alphabets in each row to position left such that the first letter is attached to last.
STEP-3: Repeat this process for all 26 rows and construct the final key matrix.
STEP-4: The keyword and the plain text is read from the user.
STEP-5: The characters in the keyword are repeated sequentially so as to match with that of the plain text.
STEP-6: Pick the first letter of the plain text and that of the keyword as the row indices and column indices respectively.
STEP-7: The junction character where these two meet forms the cipher character.
STEP-8: Repeat the above steps to generate the entire cipher text.


## PROGRAM
```
#include <stdio.h>
#include <string.h>
#include <ctype.h>

// Function to encrypt the text
void encryptVigenere(char text[], char key[]) {
    int textLen = strlen(text);
    int keyLen = strlen(key);
    
    for (int i = 0; i < textLen; i++) {
        if (isalpha(text[i])) {
            char base = isupper(text[i]) ? 'A' : 'a';
            text[i] = (text[i] - base + (toupper(key[i % keyLen]) - 'A')) % 26 + base;
        }
    }
}

// Function to decrypt the text
void decryptVigenere(char text[], char key[]) {
    int textLen = strlen(text);
    int keyLen = strlen(key);
    
    for (int i = 0; i < textLen; i++) {
        if (isalpha(text[i])) {
            char base = isupper(text[i]) ? 'A' : 'a';
            text[i] = (text[i] - base - (toupper(key[i % keyLen]) - 'A') + 26) % 26 + base;
        }
    }
}

int main() {
    char text[100], key[100];

    printf("Enter the plaintext: ");
    scanf("%s", text);
    printf("Enter the key: ");
    scanf("%s", key);

    encryptVigenere(text, key);
    printf("Encrypted Text: %s\n", text);

    decryptVigenere(text, key);
    printf("Decrypted Text: %s\n", text);

    return 0;
}

```

## OUTPUT
![image](https://github.com/user-attachments/assets/49ff375b-f6ca-4d36-8b7a-755835907afb)

## RESULT
implementation of Vigenere Cipher substitution technique using C program has been done successfully.
