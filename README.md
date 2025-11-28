# EX. NO: 1(A) : IMPLEMENTATION OF CAESAR CIPHER

STEP-2: Read the key value from the user.

STEP-3: If the key is positive then encrypt the text by adding the key with each character in the plain text.

STEP-4: Else subtract the key from the plain text.

STEP-5: Display the cipher text obtained above.

## PROGRAM:

```
#include <stdio.h> 
#include <string.h> 
#include <ctype.h> 
 
int main() { 
    char text[100]; 
    int keyval; 
    prin ("Enter the plain text: "); 
    fgets(text, sizeof(text), stdin); 
    text[strcspn(text, "\n")] = '\0'; 
    prin ("Enter key value: "); 
    scanf("%d", &keyval); 
    for (int i = 0; i < strlen(text); i++) { 
        char ch = text[i]; 
        if (isalpha(ch)) { 
            char base = isupper(ch) ? 'A' : 'a'; 
            ch = (ch - base + keyval) % 26; 
            if (ch < 0) ch += 26; 
            text[i] = ch + base; 
        } 
    } 
    prin ("Cipher text: %s\n", text); 
 
    for (int i = 0; i < strlen(text); i++) { 
        char ch = text[i]; 
        if (isalpha(ch)) { 
            char base = isupper(ch) ? 'A' : 'a'; 
            ch = (ch - base - keyval) % 26; 
            if (ch < 0) ch += 26; 
            text[i] = ch + base; 
        } 
    } 
    prin ("Decrypted text: %s\n", text); 
    return 0; 
} 
} 

```
## OUTPUT:
<img width="632" height="468" alt="image" src="https://github.com/user-attachments/assets/339a6ba5-30c2-4fce-84dd-e3c87dc9f7ba" />


## RESULT :
 Thus the implementation of ceasar cipher had been executed successfully.
