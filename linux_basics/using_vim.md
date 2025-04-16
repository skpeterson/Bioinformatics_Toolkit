## Using VIM as your text editor

There are multiple options for editing text files on a linux system. I tend to use vim and I always forget the sneaky little commands. 


## Vim has several modes, and these are important, as each changes what happens when you click away at your keyboard 

1. Insert
2. Command
3. Exit

## Viewing and moving around files in Vim

To open a file with Vim 
```
vim file_name.txt
```

This is command mode. Your mouse is no good here and your keyboard keys have new meanings, so we need to remember a few keyboard shortcuts. 

| command | what it does |
| -- | -- |
| j | moves the cursor down one line (can also use the down arrow) |
| k | moves the cursor up one line (can also use the up arrow) |
| 0 | moves the cursor to the start of the line |
| $ | moves the cursor the end of the line |
| gg | moves to the beginning of the file |
| G | moves to the start of the file |

Also a fun tip that I don't see often is that you can preface these commands with a number to execute the command that many times. 
```
6j
```
Command will move the cursor down 6 lines!

## Editing files with Vim

You can edit files two ways. The first, is to stay in command  mode, where you can modify the file with these commands

|command | what it does |
| -- | -- |
| d | starts the deletion operation (can be combined with other things) |
| dgg | will delete to the beginning of the file (cheeky huh?) |
| dG | will delete to the end of the file (also cheeky) |
| d$ | will delete to the end of the line (look familiar?) |
| d0 | will delete to the beginning of the line (also familiar, I hope) |
| u | undo the most recent operation |


Copying and pasting in Vim is also about stacking commands. 
| command | what it does |
| -- | -- |
| V | highlights an entire line |
| y | yanks whatever is highlighted into the copy buffer |
| p | paste whatever is in the copy buffer into the current line |

We can also edit file in insert mode. Here, the commands don't work, but we can physically type in content. The keys should behave as we would normally expect them to when we are typing. We enter this move by pressing the insert key on the keyboard, type/delete what you want (again, your mouse is no good here) and then exit back into command mode by pressing the escape key. 


## Exiting Vim

So you've made your edits and you're ready to close your awesome file. To do this, be sure you are in command mode. Enter ```:``` and a line at the bottom of the window will appear for input. This is where we decide what to do with the file we just edited!

| command | what it does |
| -- | -- |
| w | write the changes you made to the file |
| q | close the file |
| q! | close the file without saving changes |
| wq | write changes to the file and close it |


