![image](https://github.com/BlackDeath619/Bandit-Writeup/assets/148000474/eb567f12-70c1-468c-a864-1572137a1453)# Bandit-Writeup
This is repository for Over The Wire.
This will be my understanding of how I have worked on OTW.

## Level 0
Understood the working of an SSH and how it allows us to connect to a remote server securely through a specific port

Learning : ssh -p can be understood as keywords

![image](https://github.com/BlackDeath619/Bandit-Writeup/assets/148000474/27fe852b-1add-4e62-b206-fe01924e41c3)

## Level 0->1
Use of command ls which is to view the list present in the server by using linux.
In order to view the files present in the list, the 'cat' standing for catenation command, has to be used
Using command exit to break connection from the remote server

![image](https://github.com/BlackDeath619/Bandit-Writeup/assets/148000474/6dfc9b81-581b-4614-9207-98138feeb1b2)

## Level 1->2
Since - is an illegal file name since our termnial views it as an input/output command, we use a special command to read the file . ' ./- ' or ' cat < -'

![image](https://github.com/BlackDeath619/Bandit-Writeup/assets/148000474/88204216-da78-4477-a797-650d5ab6fe4b)

## Level 2->3
A filename should be continuous hence we put in quotation or we can use backslash
cat "spaces in this filename"
cat spaces\ in\ this\ filename\

![image](https://github.com/BlackDeath619/Bandit-Writeup/assets/148000474/f65c621e-4782-4458-89c4-dfeb432ed4d3)

## Level 3->4
A hidden file in a different directory can be accessed by first using 'cd' command to change to that directory (in this case, 'inhere' directory) and using command 'cat .hidden' in order to read the hidden contents of the directory
To find the name of the hidden file i.e. '.hidden' I have used ls -al which shows me all the files in the directory, substitutes for -al can be '-a' or '-A' which does not ignore entries starting with . or not listing . and .. respectively.

![image](https://github.com/BlackDeath619/Bandit-Writeup/assets/148000474/77650bd9-062c-46da-be2d-bef9259c990b)

## Level 4->5
In this level there were multiple files
The clue was 'human readable' hence, we check the data type of each file in the 'inhere' directory by using the file command
Since all files were starting with illegal symbol '-', we use './-' command

lrIWWI6bB37kxfiCQZqUdOIYfr6eEeqR

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

## Level 11->12
I have used Rot13 decipher online to convert the file 'data.txt' 
JVNBBFSmZwKKOP0XbFXOoW8chDz5yVRv

![image](https://github.com/BlackDeath619/Bandit-Writeup/assets/148000474/8df90941-80a0-4b07-bc1b-467f10553255)

this translates to 'The password is JVNBBFSmZwKKOP0XbFXOoW8chDz5yVRv'

## Level 12->13
Use of xxd is used here to reverse the hexdump 
Initially we create a directory to and copy data.txt to the said directory, here I have used directory name as 'BD'
mkdir /tmp/BD
cp data.txt /tmp/BD
cd /tmp/BD

we use the xxd command to reverse the hexdump and save the data into another file in the BD directory
xxd -reverse daata.tx > dump

on using file command we find out that the reversed hexdump is actually compressed, hence we convert the file to gzip (to decompress) format by
mv dump dump.gz
gunzip dump.gz

We also use tar command to open tar files which is analogous to .exe files in windows

We extract files from the given saved file in our directory
![image](https://github.com/BlackDeath619/Bandit-Writeup/assets/148000474/668c7c55-0f14-4591-95d8-937f0f7e6f2d)
![image](https://github.com/BlackDeath619/Bandit-Writeup/assets/148000474/a12649a5-e69f-41ba-8ece-cbd674901a5d)
![image](https://github.com/BlackDeath619/Bandit-Writeup/assets/148000474/873b4a01-da28-4873-a236-d9298af211e9)

The password is wbWdlBxEir4CaE8LaPhauuOo6pwRmrDw

## Level 13->14

Here we use the -i variant of ssh, basically it selects the file from within our directory for a private login

ssh -i 

We can use ls -l which gives us a long format and tells us about the owner and readers of the file
and this time the machine we will be logging on will be localhost and not bandit.labs.overthewire.org

![image](https://github.com/BlackDeath619/Bandit-Writeup/assets/148000474/cc6817dc-1885-48d0-95b9-dbe4190d0258)
![image](https://github.com/BlackDeath619/Bandit-Writeup/assets/148000474/6a4bb9f7-7d5a-42bc-9206-11422bba6b22)

pass for 14 fGrHPx402xGC7U7rXKDaxiWFTOiF0ENq

## Level 14->15

From the previous level we know that lvl 14's password is in /etc/bandit_pass/bandit14
the condition here is that lvl 14's password will give us the password for lvl 15

here we use a new command netcat which allows us to connect remote hosts with different ports
here our host is localhost with port 30000
Hence we use 
nc localhost 30000

and enter the password we have found by entering cat /etc/bandit_pass/bandit14

![image](https://github.com/BlackDeath619/Bandit-Writeup/assets/148000474/5e1b8f7c-6366-459f-8fd9-1c2ba740dd29)

pass for 15 jN2kgmIXJ6fShzhT2avhotn4Zcka6tnt

## level 15->16

Here we use Secure Socket Layer instead of Secure Shell
syntax : openssl s_client -connect [host name]:port

first we get the password for bandit15 found previously and input that into our ssl
![image](https://github.com/BlackDeath619/Bandit-Writeup/assets/148000474/86cacf45-df3f-47dd-9cef-68b4e0dac1bd)
![image](https://github.com/BlackDeath619/Bandit-Writeup/assets/148000474/5e5cd7a4-3c15-4d59-9159-301b13522a16)

pass for 16 JQttfApK4SeyHwDlI9SXGR50qclOAil1

## Level 16->17

Here we have a range of ports given
hence we use nmaps with a specified target and range 31000 to 32000
'nmap' command is a tool to visit multiple ports simultaneously and scan them
a port maybe open, closed, filtered or unfiltered
open - an application is listening for connections
closed - not listening for connections on that port
filtered - scanner cannot tell whether open or closed
unfiltered - the scanner interacts with the port but cannot tell its state i.e. open or closed








