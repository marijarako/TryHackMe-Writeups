# LINUX FUNDAMENTALS (Pt1)
## Commands
Using the virtual Ubuntu machine I have practised commands:
- whoami - tells you who you are on the system
- echo - output some specific text that is provided
- ls - list what's in the current folder
- cd - change directory — move into a folder
- cat - show the contents of a file
- pwd - print working directory — "where am I?"
- find - search for files by their name. For example, find -name passwords.txt
- grep - searches inside for text. For example, grep "password123" passwords.txt
#### Combine commands and capture their output
- & - Runs the command, but does not wait for it to finish before you can do anything else. The command runs in the backgorund, and is helpful for commands that might take a while to complete, or ones that you want to keep running.
- && - Runs both commands, but waits for the first command to finish first, before the next. Like a set of dominoes.
- '>' - Used to redirect output. We can take the output of a command and send it to a file. This operator will overwrite anything that exists in the file.
- '>>' - This redirector does the same thing, but instead of overwriting, it will just add the output to the bottom of the file.

# LINUX FUNDAMENTALS (Pt2)
## Accessing Linux Remotely 
- SSH (Secure Socket Shell) is a protocol that lets two devices talk to each other securely over a network. SSH allows us to login to computers remotely for us to use.
- To use SSH to login to our remote computer we need two things. IP address of the remote computer, as well as the username and password. Then, the command we need to run would look like this *ssh tryhackme@10.113.158.205*
## Extending Commands: Arguments 
- Using --help argument, we can see all he arguments available for the each command
- Using man command, we can see the whole manual page of the command
## Managing Files on Linux
|Command|Full Name|Purpose|
|---|---|---|
|touch|touch|Create File|
|mkdir|make directory|Create a folder|
|cp|copy|Copy a file or folder|
|mv|move|Move a file or folder|
|rm|remove|Remove a file or folder|
* cp copies the entire contents of the existing file into a new file. Example: *cp recipe recipe2*
* Moving a file uses the mv command, which also takes two arguments like cp. The difference is that mv doesn't copy the file, it moves or renames the original. You can use it to move a file into a different folder, or to rename a file or folder in place. Example: *mv recipe recipe2*
## Common Directories
* /etc - The etc folder is a commonplace location where system and program files are stored. that are used by Linux.
* /var - It stores data that services and applications write to or read often, like log files (kept in /var/log), and other data not tied to a specific user, such as databases.
* /root - Unlike the /home directory, the /root folder is actually the home for the "root" system user. There isn't anything more to this folder other than just understanding that this is the home directory for the "root" user.
* /tmp - Short for "temporary", the /tmp directory is temporay and is used to store data that is only needed to be accessed once or twice. Unlike any other directory on Linux, any user can store things here!
## Permissions: Users and groups
Permissions are:
1. Read
2. Write
3. Execute
#### The difference between Users & Groups
- A file has one owner, but you can also assign a group (of users) to that file, and give that group its own set of permissions, separate from the owner's. So the group of users may only be to read the file while the owner has full control, or any other combination, without changing who actually owns it.
#### Switching between users
- command su: su -l user2

# LINUX FUNDAMENTALS (Pt3)
- Nano - text editor *nano filename*
- VIM - more complex text editor
- wget - downloading something from internet wget *https://assets.tryhackme.com/additional/linux-fundamentals/part3/myfile.txt*
- scp - secure copy, unlike the regular cp command, this command allows you to transfer files between two computers using the SSH protocol to provide both authentication and encryption. *scp important.txt ubuntu@192.168.1.30:/home/ubuntu/transferred.txt* *scp ubuntu@192.168.1.30:/home/ubuntu/documents.txt notes.txt*
## Serving Files From Your Host - WEB
-  Python helpfully provides a lightweight and easy-to-use module called "HTTPServer". This module turns your computer into a quick and easy web server that you can use to serve your own files, where they can then be downloaded by another computing using commands such as curl and wget.
-  We run the command *python3 -m  http.server* in the terminal
-  We use wget to to download the file using the address and the name of the file. For example: *wget http://10.114.153.119:8000/myfile*
-  One flaw with this module is that you have no way of indexing, so you must know the exact name and location of the file that you wish to use.
## Processes 101
- Processes are the programs that are running on your machine. They are managed by the kernel, where each process will have an ID associated with it, also known as its PID. The PID increments for the order In which the process starts. I.e. the 60th process will have a PID of 60.
### Viewing Processes
- We can use ps command to provide a list of the running processes as our user's session and some additional information such as its status code, the session that is running it, how much usage time of the CPU it is using, and the name of the actual program or command that is being executed.
- To see the processes run by other users and those that don't run from a session (i.e. system processes), we need to provide aux to the ps command like so: ps aux
- Another very useful command is the top command; top gives you real-time statistics about the processes running on your system instead of a one-time view. These statistics will refresh every 10 seconds, but will also refresh when you use the arrow keys to browse the various rows. Another great command to gain insight into your system is via the top command
### Managing Processes
- To kill a command, we can use the appropriately named kill command and the associated PID that we wish to kill. i.e., to kill PID 1337, we'd use kill 1337.
- SIGTERM - Kill the process, but allow it to do some cleanup tasks beforehand
- SIGKILL - Kill the process - doesn't do any cleanup after the fact
- SIGSTOP - Stop/suspend a process
