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
