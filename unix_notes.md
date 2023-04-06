# Exercise 1
**Use the information in the man page to determine how to get date to print out the abbreviated day of the week.**
```
date "+%A"
```
# Exercise 2
**What happens if you type echo mycolor? Do you get something different without the $?\
In general what does the echo command do and why does its behavior depend on the $?**\
If I type `echo mycolor` I get `mycolor` as the output.\
If I type `echo $mycolor` I get `blue` as the output.\
In general the `echo` command just returns whatever was the input. It changes depending on `$` because it indicates a user variable.

# Exercise 3
**Your instance’s main file system is located at /dev/sda1. Using what you know about Unix commands and the df function, print out how much free space your instance has available in a human-readable format.**\
Using `df /dev/sda1 -h' it looks like there's 59 gigs of free storage.

# Exercise 4
**The file ~/data/A.thaliana/Araport11_genes.201606.pep.fasta.gz contains all of the predicted protein sequences from genes in the Arabidopsis genome. Using the commands you have learned so far, write a command or set of commands to display the name of the last protein in the file. In your answer include both the commands that you used (formatted as a code block) and the output from those commands.**\

#### Input
```
gunzip -c ~/data/A.thaliana/Araport11_genes.201606.pep.fasta.gz | grep "protein" | tail -1
```
#### Output
```
>ATMG01400.1 | hypothetical protein | ChrM:363725-364042 FORWARD LENGTH=105 | 201606
```
# UNIX AND GIT NOTES
General Format is: COMMAND OPTIONS FILEPATH

## extra useful commands
‘man’ for documentation
ls
+ `-F` Shows what's a directory or not
+ `-L` Long format
+ `-a` shows all of the files
+ `-l` shows aliases and permissions

ln -s -> Makes an alias
+Ex: `ln -s Stuff/foo ./foof` links `Stuff/foo` to `foof` in the `./` directory

rm -r [directory]
+ removes even non empty directories
### Commands

1. date
2. history
3. df
    + returns free disk space (-h for human readable)
4. du
    + like df but returns used disk space (also has -h)
5. touch
    + make file
6. cat
    + concatenate to file
7. head and tail
    + Just see the first/last lines of a file
8. less and more
    + Look at file page by page in terminal
9. nano
    + file editor `^o` then `^x`
10. pwd
    + prints working diretory
11. mv
    + moves AND renames
12. chmod
    + can change permissions USER -> GROUP -> PUBLIC
    + Common ones
      + 777 -> All ON
      + 444 -> Read only
      + 600 -> read write others nothing
13. grep
    + cmd+f but for a file
    + ex: `gunzip -c genome.gz | grep ">"`
14. gzip and gunzip
    + compress and decompress file
15. top OR htop
    + Task Manager in terminal
16. ^C
    + stops process
17. ^Z + fg
    + Pause and continue process.
18. kill
    + can kill processes. kill `[PID]` from `top`
    
### Syntax
\> redirects and overwrites existing files

### Other
+ unix files generally all lowercase, no space
+ Directories should have a capital

+ for tables the colons in `:--:` justify the text versus just leaving it alone

### Git 
+ do often
+ `git add` -> `git commit -m "[message]" [file]` -> `git push` \



+ new repo
  + `mkdir` -> `git add [file]` -> `git commit -m [message]`
  + `git remote add origin [ssh url]`
  + `git push -u origin master`
  
+ cloning a repo
  + `git clone [ssh url]`

+ git merge [branchname]
  + merge cuttent branch into [branchname]

+ auth 
  + git config --global user.username "rhpineda"
  + git config --global user.email "rhpineda@ucdavis.edu"
