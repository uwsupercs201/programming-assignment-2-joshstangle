# Programming Assignment 3

## Goal: Learn the use of loops for processing strings.

Our code will use a cipher to encrypt a message. The encryption works by creating a correspondence of the English alphabet (A-Z,a-z) to itself. Then, given a message to encrypt, it encrypts it by changing each character to the character given by the correspondence. So, if our correspondence was 

```
ABCDEFGHIJKLMNOPQRSTUVWXYZabcdefghijklmnopqrstuvwxyz
|
V
LFjNgnZbvmuewxTIJPfDpMtAzXsiUdqGhayWQrlOEBKoRkCSHYVc
```

The message

```
I love computers
```

Would be encypted as

```
vrESqUElBCkqoR
```

(Note: we will ignore spaces in the original statement when we excrypt, this makes our message more secure and is unlikely to cause the decrypted message to be unreadable)

We will do this in 2 stages:

## Part 1: Cipher generator

We need to generate the correspondence from the alphabet to itself. We'll do so by starting with the string 

```
String base_alphabet = "ABCDEFGHIJKLMNOPQRSTUVWXYZabcdefghijklmnopqrstuvwxyz"
```

We don't want the user (or hackers) to know the cipher string, so we'll generate it. But, we want to ensure the user can generate the same cipher each time (as this will be the only way to decrypt the message!). To do so, we'll generate random numbers but set a seed each time so the random numbers are "repeatable". 


## Part 2: Message Encryption

Once the cipher is excrypted, we can take a user entered string called ```stringToEncrypt``` and encrypt it by 

1) removing all white spaces, punctuation, and numbers.
2) replacing each letter in the string by the corresponding letter in the cipher. 

### Your Assignment:

Create a Java class called `Encryptor`. Within the `main` method, you will prompt the user for an integer between 1 and 1000. This will be the `encryptionNumber`. It will also prompt the user for a message to encrypt called the `messageToEncrypt`

The class should also contain methods:

- `createCipher` which has an `int` parameter and returns a `String`. This method should take `encryptionNumber` as the parameter, and return the 
string `cipher` which is the string containing all letters in a random order.
- `encrypt` which has two `String` parameters and returns a `String`. This method should take the 'cipher' and 'messageToEncrypt' as parameters and return the ecrypted method to the `main.` From the `main` method, the ecrypted message should be printed.

### Example

```
Enter a number 1 to 1000:52
Enter a message to encrypt:I love computers
Encrypted Message:vrESqUElBCkqoR
```


If another user enters the same integer and message, the encrypted message should be identical.

### Implementation Hints:
For the cipher:
- create an empty `String` to hold the cipher.
- You can use the `Random` class to generate random integers from 65-90 [A-Z] or 96-122 [a-z]. Casting each integer as a `char` will give you a character.
- Use the `ecryptionNumber` to set a predictable seed each time you generate a new integer[for repeatability]
- check whether the new character is already added to cipher and, if not, add it. If the new character IS already in the cipher, create a new character and re-check. 
- Each time you create a new integer, you should change the seed since it will generate the same `int` whenever the seed is the same.
- Once the cipher is 52 characters long, it is complete. 

For the encryption: 
- Proceed once character at a time through `messageToEncrypt`. Find the index in `base_alphabet` of the character and replace that character in `messageToEncrypt` with the `char` from the same index from `cipher`.

## Submitting the Assignment

When you're done, you can upload your files to this Repo and commit the changes.

Click Add files at the top right of the Repo page.

There are two options:

A) Click "Add Files" to create new Java files in the repo manually. Create a new file with name `Encryptor` You can re-type or copy paste your code into those files.

B) Click "Upload Files" to just upload the `.java` files you already created. Navigate to the src folder on your computer and upload `Encryptor.java`

Once you've created the file you want, or uploaded them, navigate to the bottom of the Page and hit "Commit changes". Ensure "Commit directly to the main branch." is selected.


