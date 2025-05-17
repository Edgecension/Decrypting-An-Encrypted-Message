# Decrypting-An-Encrypted-Message

## Project Description  
Complete a series of tasks to obtain instructions for decrypting an encrypted file. Encryption of data in use, at rest, and in transit is critical to security functions.

## Read The Contents Of A File
Using the **ls** command to list the files in the current working directory, two files, **Q1.encrypted** and **README.txt**, and a *subdirectory*, *caesar*, are listed:

<img width="756" alt="Screenshot 2025-05-17 at 5 38 05 PM" src="https://github.com/user-attachments/assets/fa1bbc12-d65c-431e-bfbb-2f2fc0649773" />

- The **README.txt** file contains an important message with instructions to follow.
- The **cat** command to list the contents of the **README.txt** file.
The message in the **README.txt** file advises that the *caesar* subdirectory contains a hidden file.

## Find A Hidden File
This task is to find a hidden file in the home directory and decrypt the Caesar cipher it contains.

<img width="756" alt="Screenshot 2025-05-17 at 5 42 22 PM" src="https://github.com/user-attachments/assets/80c47ba4-002f-4ea6-a9fd-d6b7e887ef70" />

- The **cd** command was first used to change to the *caesar* subdirectory of your home directory.
- Then the **ls -a** command to list all files, including hidden files, in the home directory.
- This will display the following output:
- **.leftShift3**
  
The message in the **.leftShift3** file appears to be scrambled. This is because the data has been encrypted using a Caesar cipher. This cipher can be solved by shifting each alphabet character to the left or right by a fixed number of spaces. In this example, the shift is three letters to the left. Thus **"d"** stands for **"a"**, and **"e"** stands for **"b"**.

The Caesar cipher in the **.leftshift3** file can be decrypted by using the following command:
- **cat .leftShift3 | tr "d-za-cD-ZA-C" "a-zA-Z"**

In this case, the command **tr "d-za-cD-ZA-C" "a-zA-Z"** translates all the lowercase and uppercase letters in the alphabet back to their original position. The first character set, indicated by **"d-za-cD-ZA-C"**, is translated to the second character set, which is **"a-zA-Z"**.

Returned to the home directory prior to the next task, **cd ~**

## Decrypt A File 
In this task, the command revealed in **.leftshift3** was used to decrypt a file and recover the the data so it can be read along with the message it contains.

<img width="756" alt="Screenshot 2025-05-17 at 5 46 32 PM" src="https://github.com/user-attachments/assets/4d50fb05-4e44-4920-828b-cb2cd900de75" />

The following command from the previous task was used to decrypt the encrypted file:
- **openssl aes-256-cbc -pbkdf2 -a -d -in Q1.encrypted -out Q1.recovered -k ettubrute**
In this instance, the **openssl** command reverses the encryption of the file with a secure symmetric cipher, as indicated by **AES-256-CBC**. The **-pbkdf2** option is used to add extra security to the key, and **-a** indicates the desired encoding for the output. The **-d** indicates decrypting, while **-in** specifies the input file and **-out** specifies the output file. The **-k** specifies the password, which in this example is ettubrute.
- The **ls** command was used to list the contents of your current working directory again.
- The new file **Q1.recovered** in the directory listing is the decrypted file and contains a message.
- The **cat** command was used to list the contents of the **Q1.recovered** file.
