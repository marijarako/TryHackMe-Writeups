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
### Combine commands and capture their output
- & - Runs the command, but does not wait for it to finish before you can do anything else. The command runs in the backgorund, and is helpful for commands that might take a while to complete, or ones that you want to keep running.
- && - Runs both commands, but waits for the first command to finish first, before the next. Like a set of dominoes.
- > - Used to redirect output. We can take the output of a command and send it to a file. This operator will overwrite anything that exists in the file.
- >> - This redirector does the same thing, but instead of overwriting, it will just add the output to the bottom of the file.
