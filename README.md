# over-the-wire-bandit
## Bandit Level 0
First, to log into the game, we will be using `ssh` command.
To log into the server we have used:
```bash
ssh bandit0@bandit.labs.overthewire.org -p 2220
```
> Password for the same is bandit0
 
Now we are logged into the host server :)
## Bandit Level 0 → Level 1

First, we will list all the files present in that directory using `ls` command.
```bash 
ls
```
Now, we will read the file named "readme" using `cat` command.
```bash
cat readme
```
We got the password for the next level  as the output. 
```bash
NH2SXQwcBdpmTEzi3bvBHMM9H66vVXjL
```
Now we will log into the **bandit1** server using this password. But first `exit` from the bandit0 server.
```bash
ssh bandit1@bandit.labs.overthewire.org -p 2220
```
Successfully, now we are in the bandit1 server :)
## Bandit Level 1 → Level 2
To read the filename "-", we have to use `<-` to make it readable as a name rather than - this treated as _options_.
```bash
cat <-
```
This will give us the password for the next level.
```bash
rRGizSaX8Mk1RTb1CNQoXTcYZWU6lgzi
```
Now we will log into the bandit2 server in the same way as the last time but using username as **bandit2** this time.
We are now in the **bandit2** server :)
## Bandit Level 2 → Level 3
This time we will be writing the file name _spaces in this filename_ within double quotes so that it is read as a single file rather than read as 4 different files.
```bash
cat "spaces in this filename"
```
This gives us the password for the next server.
```bash
aBZ0W5EmUfAf7kHTQeOwd8bauFJ2lAiG
```
Now log in to the next level using this password:)
## Bandit Level 3 → Level 4
We have used the following commands. `cd inhere` -> `ls -a`. We used `ls -a` command to list all(including all the hidden files/directories). Now:
```bash
cat .hidden
```
Password:
```bash
2EW7BBsr6aMMoJ2HjW067dm8EgX26xNe
```
Now log in to the next level using this password:)
## Bandit Level 4 → Level 5
We have used the following commands. `cd inhere` -> `ls -a`. We now use `file` command to read the type of files whick are present in out present directory.
```bash
file ./*
```
We get this output:

```bash
./-file00: data
./-file01: data
./-file02: data
./-file03: data
./-file04: data
./-file05: data
./-file06: data
./-file07: ASCII text
./-file08: data
./-file09: data
```
As we can see the filenamed _-file07_ is text type file. So we know that password is contained in this file :)
```bash
cat <-file07
```
Password :
```bash
lrIWWI6bB37kxfiCQZqUdOIYfr6eEeqR
```
## Bandit Level 5 → Level 6
we will be using `find` command in this level.
```bash
find -type f -size 1033c
```
Here, we have used this command to find a common file type/human readable (so used _-type f_) and to find file of size 1033 bytes (so used _1033c_ for bytes).
Password :
```bash
P4L4vucdmLnm8I7Vl7jG1ApGSfjYKqJU
```
## Bandit Level 6 → Level 7

we will be using `find /` command in this level to search in whole server.
```bash
find / -group bandit6 -user bandit7 -size 33c
```
This gives a very long lists of files in which most of them are mentioned as _Permission denied_. So to remove all these type of files we have a command `2>/dev/null`.
```bash
find / -group bandit6 -user bandit7 -size 33c 2>/dev/null
```
This gives the output:
`/var/lib/dpkg/info/bandit7.password`
We will now navigate to this file for the password using `cat` command.
```bash
cat /var/lib/dpkg/info/bandit7.password
```
Password :
```bash
z7WtoNQU2XfjmMtWA8u5rN4vzqu4v99S
```
## Bandit Level 7 → Level 8











