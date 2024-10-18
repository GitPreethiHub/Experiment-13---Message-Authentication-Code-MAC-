# Experiment-13---Message-Authentication-Code-MAC
## Aim: 
To implement Message Authentication Code (MAC) for verifying message integrity.

## Algorithm Steps:
1) Generate a shared secret key.
2) Create a message and compute the MAC using the key.
3) Send the message and the MAC to the recipient.
4) The recipient verifies the MAC using the shared key.
5) If the MAC matches, the message is authenticated.

## Program
```
#include <stdio.h>
#include <string.h>

void compute_mac(char *message, char *key, char *mac) {
    for (int i = 0; i < strlen(message); i++) {
        mac[i] = message[i] ^ key[i % strlen(key)];
    }
}

int main() {
    printf("Experiment 13 - Message Authentication Code (MAC)\n");
    printf("Developed by: Preethi M 212222100037\n");

    char message[] = "preethi";
    char key[] = "secret";
    char mac[100];

    compute_mac(message, key, mac);

    printf("Message: %s\n", message);
    printf("Key: %s\n", key);

    printf("MAC (in hex): ");
    for (int i = 0; i < strlen(message); i++) {
        printf("%02X", (unsigned char)mac[i]);
    }
    printf("\n");

    return 0;
}

```

## Output
![image](https://github.com/user-attachments/assets/a102b98e-d41b-4741-a391-bad3f2060e18)

## Result
The MAC for the given message is successfully computed using a secret key.
