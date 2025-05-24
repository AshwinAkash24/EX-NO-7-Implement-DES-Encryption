# EX-NO-7-Implement-DES-Encryption
## Submitted By: Ashwin Akash M
## Reference Number:212223230024
## Aim:

To use the Data Encryption Standard (DES) algorithm for a practical application, such as securing sensitive data transmission in financial transactions.

## ALGORITHM:

1. Input Message and Key: Read the user input for the message and the key, allowing
spaces.
2. Encryption: XOR each character of the message with the key, repeating the key if it's
shorter than the message.
3. Print Encrypted Message: Display the encrypted message as hexadecimal values.
4. Decryption: XOR the encrypted message with the same key to get back the original
message.
5. Display Decrypted Message: Print the decrypted message to verify it matches the original.

## Program:
```
#include <stdio.h>
#include <string.h>
void encrypt(char *message, char *key, char *encryptedMessage, int messageLength)
{
int keyLength = strlen(key);
for (int i = 0; i < messageLength; i++)
{
encryptedMessage[i] = message[i] ^ key[i % keyLength];
}
encryptedMessage[messageLength] = '\0';
}
void decrypt(char *encryptedMessage, char *key, char *decryptedMessage, int
messageLength)
{
int keyLength = strlen(key);
for (int i = 0; i < messageLength; i++)
{
decryptedMessage[i] = encryptedMessage[i] ^ key[i % keyLength];
}
decryptedMessage[messageLength] = '\0';
}
int main()
{
char message[100];
char key[100];
printf("\n**Simulation of DES encryption and decryption\n\n");
printf("Enter the message to encrypt: ");
scanf("%[^\n]%*c", message);
printf("Enter the encryption key: ");
scanf("%[^\n]%*c", key);
int messageLength = strlen(message);
char encryptedMessage[100];
char decryptedMessage[100];
encrypt(message, key, encryptedMessage, messageLength);
printf("Original Message: %s\n", message);
printf("Encrypted Message: ");
for (int i = 0; i < messageLength; i++)
{
printf("%02X ", (unsigned char)encryptedMessage[i]);
}
printf("\n");
decrypt(encryptedMessage, key, decryptedMessage, messageLength);
printf("Decrypted Message: %s\n", decryptedMessage);
return 0;
}
```



## Output:
![Screenshot 2025-04-18 095226](https://github.com/user-attachments/assets/43334f2f-8172-4b5d-b671-b1a5d6693b48)
![Screenshot 2025-04-18 095255](https://github.com/user-attachments/assets/66287ac8-cdf5-48e5-99e6-80a447b35c77)


## Result:
The program is executed successfully

