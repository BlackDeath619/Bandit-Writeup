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
A filename should be continuous hence we put in quotation or we can use
![image](https://github.com/BlackDeath619/Bandit-Writeup/assets/148000474/f65c621e-4782-4458-89c4-dfeb432ed4d3)

## Level 3->4
A hidden file in a different directory can be accessed by first using 'cd' command to change to that directory (in this case, 'inhere' directory) and using command 'cat .hidden' in order to read the hidden contents of the directory
![image](https://github.com/BlackDeath619/Bandit-Writeup/assets/148000474/77650bd9-062c-46da-be2d-bef9259c990b)

## Level 4->5
In this level there were multiple files
The clue was 'human readable' hence, we check the data type of each file in the 'inhere' directory by using the file command
Since all files were starting with illegal symbol '-', we use './-' command

![image](https://github.com/BlackDeath619/Bandit-Writeup/assets/148000474/019e79e2-8941-4bad-b6fd-5c663d6d6d60)


