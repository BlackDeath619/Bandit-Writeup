# Bandit-Writeup
This is repository for Over The Wire.
This will be my understanding of how I have worked on OTW.

## Level 0
Understood the working of an SSH and how it allows us to connect to a remote server securely through a specific port

![image](https://github.com/BlackDeath619/Bandit-Writeup/assets/148000474/27fe852b-1add-4e62-b206-fe01924e41c3)

## Level 0->1
Use of command ls which is to view the list present in the server by using linux.
In order to view the files present in the list, the 'cat' standing for catenation command, has to be used
Using command exit to break connection from the remote server

![image](https://github.com/BlackDeath619/Bandit-Writeup/assets/148000474/6dfc9b81-581b-4614-9207-98138feeb1b2)

## Level 1->2
Since - is an illegal file name, we use a special command to read the file . ' ./- '

![image](https://github.com/BlackDeath619/Bandit-Writeup/assets/148000474/88204216-da78-4477-a797-650d5ab6fe4b)

## Level 2->3
A filename should be continuous hence we put in quotation or we can use backslash
![image](https://github.com/BlackDeath619/Bandit-Writeup/assets/148000474/f65c621e-4782-4458-89c4-dfeb432ed4d3)

## Level 3->4
A hidden file in a different directory can be accessed by first using 'cd' command to change to that directory (in this case, 'inhere' directory) and using command 'cat .hidden' in order to read the hidden contents of the directory
![image](https://github.com/BlackDeath619/Bandit-Writeup/assets/148000474/77650bd9-062c-46da-be2d-bef9259c990b)

## Level 4->5
In this level there were multiple files
The clue was 'human readable' hence, we check the data type of each file in the 'inhere' directory by using the file command
Since all files were starting with illegal symbol '-', we use './-' command
![image](https://github.com/BlackDeath619/Bandit-Writeup/assets/148000474/019e79e2-8941-4bad-b6fd-5c663d6d6d60)

## Level 5->6 
In this level there were multiple directories with multiple files
hence using man find I have found out a variant of using the 'find' command to check the size of a specific file in a certain directory
we specify using 'c' the byte size, and the syntax used here is :
![image](https://github.com/BlackDeath619/Bandit-Writeup/assets/148000474/c2f2fddf-24cd-442d-a9f0-5006ad485ded)

## Level 6->7
Here I have learnt the usage of '.' which is used to find files all over the directory whereas '/' is used to find files all over the server
hence we use specific syntax i.e. -type, -size, -user, -group to narrow down our search results and get the flag
![image](https://github.com/BlackDeath619/Bandit-Writeup/assets/148000474/2e3013b7-2576-488f-84fa-7d5eedcab932)
![image](https://github.com/BlackDeath619/Bandit-Writeup/assets/148000474/f2aaddb1-611d-4ecd-b0a2-b6668de34124)
z7WtoNQU2XfjmMtWA8u5rN4vzqu4v99S

## Level 7->8
TESKZC0XvTetK0S9xNwm25STk5iWrBvP
Here we have used the 'grep' command haviing syntaxt grep [string name] [file name]
![image](https://github.com/BlackDeath619/Bandit-Writeup/assets/148000474/03e6e426-aa49-49a9-a670-6b9dd516746c)

## Level 8->9
Here we have used the uniq function, particularly '-c' since our key only repeats once 

EN632PlfYiZbn3PhVK3XOGSlNInNE00t
![image](https://github.com/BlackDeath619/Bandit-Writeup/assets/148000474/6b224947-a253-4b59-b172-bed31ac8e268)

## Level 9->10
Here we have used "strings" command in our file 'data.txt' in order to print the printable components of it.
Hence we further use 'grep' to find the recurrence of '='
From my understanding, we use the piping command to input 2 separate inputs into our code.
G7w8LIi6J3kTb8A7j9LgrywtEUlyyp6s
![image](https://github.com/BlackDeath619/Bandit-Writeup/assets/148000474/da593dca-de34-4f55-9a21-eed97d6439d6)

## Level 10->11
Here our file contains encoded base64, thus we use 'base64 -d' command to decode it and obtain the key
6zPeziLdR2RKNdNYFNb6nVCKzphlXHBM
![image](https://github.com/BlackDeath619/Bandit-Writeup/assets/148000474/04afd98c-f284-4b3c-8287-c474c25bd4f1)

## Level 11-12
I have used Rot13 decipher online to convert the file 'data.txt' 
JVNBBFSmZwKKOP0XbFXOoW8chDz5yVRv
![image](https://github.com/BlackDeath619/Bandit-Writeup/assets/148000474/8df90941-80a0-4b07-bc1b-467f10553255)

this translates to 'The password is JVNBBFSmZwKKOP0XbFXOoW8chDz5yVRv'









