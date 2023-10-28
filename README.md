# Bandit-Writeup
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

But this will take time. We use the file command and check all the types of files which are executable using './*' where './' operator is used to execute file
and '\*' signifies all files in the directory

![image](https://github.com/BlackDeath619/Bandit-Writeup/assets/148000474/c526504a-f051-4e01-8d0b-9521bb160165)

![image](https://github.com/BlackDeath619/Bandit-Writeup/assets/148000474/019e79e2-8941-4bad-b6fd-5c663d6d6d60)

lrIWWI6bB37kxfiCQZqUdOIYfr6eEeqR

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

on checking the ports using nmap we get port 31790 which accepts ssl 
Input pass for lvl 16 and we get a private key

![image](https://github.com/BlackDeath619/Bandit-Writeup/assets/148000474/ea76e78d-b726-4d13-a9b8-ee1c2f39a221)
![image](https://github.com/BlackDeath619/Bandit-Writeup/assets/148000474/8997f7a0-8b9f-48f9-9e23-a9ca3d0c51e5)

We create a temporary directory in which we save our nano
Nano can be understood as an editor to save our texts and we can access specific lines in it
![image](https://github.com/BlackDeath619/Bandit-Writeup/assets/148000474/1a01a54a-8d1f-4292-9d0d-462c5b746aab)
![image](https://github.com/BlackDeath619/Bandit-Writeup/assets/148000474/e4213daf-22a9-496f-befb-cb2ccaac7df5)

We convert our key into private by modifying it using chmod
chmod 700 pvt.key
which makes the file pvt.key read+write+executable by 'user only'
we can check this by using ls -l (long format)

![image](https://github.com/BlackDeath619/Bandit-Writeup/assets/148000474/caf12c08-f001-4bdf-a567-1838fdf63cfe)

and hence using this private key we login to bandit17

![image](https://github.com/BlackDeath619/Bandit-Writeup/assets/148000474/d0b037aa-cb18-4749-908a-8193b2c0086d)

password for 17 VwOSWtCA7lRkTfbr2IDh6awj9RNZM5e

## Level 17->18

Here we have learnt a new command 'diff' which compares file to file to find the difference
since the password is in the 'passwords.new' file we used the 2nd password to login to 18

password for 18 hga5tuuCLF6fFzUpnagiMN8ssu9LFrdg

![image](https://github.com/BlackDeath619/Bandit-Writeup/assets/148000474/597aa548-4bd9-4b98-96a2-778ac88ecfcb)

Byebye?

## Level 18->19

In this level, the problem statement says that "Whenever you login to bandit18 you will be kicked out because someone modified it into .bashrc"
A .bashrc modification basically executes the command (here it logs us out saying 'byebye!') when we enter a host

Hence to counter this, we login with ssh using our command that we want to execute in the host by "[command]" 

![image](https://github.com/BlackDeath619/Bandit-Writeup/assets/148000474/f949672a-b26a-4ffd-933d-017d42e73ae0)

password for 19 awhqfNnAbc1naukrpqDYcF95h7HoMTrC

## Level 19->20

Here, we have a file which can only be opened by a certain uid 'bandit20-do'
on checking the long format of the file we see rw**s**r
the s signifies the setuid

Hence on checking the ID on the file by first executing it by './'
./bandit20-do id

We see that our 'euid' or effective ID for that file is bandit20 which can access the file
So, we type the command prompt while opening the file and get the password

![image](https://github.com/BlackDeath619/Bandit-Writeup/assets/148000474/1ee7c0d3-108f-4dc8-8889-73a14f135e0f)

passowrd for 20 VxCazJaVykI6W36BkBU0mJTCM8rR95XT

## Level 20->21

In this, bandit 20 has file which compares the passwords from give from a specific port to the password in the previous problem.
Hence if the passwords are same, it returns the new password to the sender port

Thus we open a new shell and create a new listening port by using 'nc -lvp'
When we switch on this port and connect the binary file in the first shell to this port, the file gets ready to take input.
On putting the correct password we get the password in the 2nd shell

![image](https://github.com/BlackDeath619/Bandit-Writeup/assets/148000474/02dd0977-e12f-431b-a209-af1b7a1a2c8d)

password for 21 NvEJF7oVjkddltPSrdKEFOllh9V1IBcq

## Level 21->22

Here the problem tell us to look into the directory '/etc/cron.d/'
we check the list of files and read the cronjob_bandit22 file
on reading we find that this file is executing '/usr/bin/cronjob_bandit22.sh' every minute
further reading the user file, we see that it is dumping its contents into '/tmp/t7O6lds9S0RqQh9aMcz6ShpAoZKF7fgv'
further reading the dumped on file, we get our password

![image](https://github.com/BlackDeath619/Bandit-Writeup/assets/148000474/8fbb4de8-9dfb-493e-8eb1-fae13ce07542)

Password for 22 WdDozAdTM2z9DiFEQ2mGlwngMfj4EZff








