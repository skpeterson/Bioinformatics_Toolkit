# Bopping around files using your linux command line interface

There are multiple ways to interact with a computer's file system. Most commonly, people use the graphical user interface (GUI) to meander through a file system. This works on your local computer where if you want to edit a document you can click it, open it, edit it, save it, and be on your merry way. 

When we are working on high performance computing systems or a system running linux, it can be easier to interact with files via the command line interface (CLI) of a terminal. For example, if you're working on a HPC and you want to modify a file, if you did this via a GUI, you would need to download the file locally, make your edits, and place the file back on the cluster. OR, we could do this all on the cluster by starting a bash session, going to that file location via the command line, opening and editing that file directly via the CLI, and then saving the file. This requires no file transfer from one computer to the other!

## Moving around

The first thing you'll want to do is being able to move around your directories in the file system. We do this is via the change directory or ```cd``` command. This command will take you to your home dir.
```
cd ~
```

We can use the same command to go wherever we want
```
cd /dir/we/want/to/be/in
```

We can use both relative or absolute paths to get places. If we add ```.``` before the first slash we can use relative paths, meaning we can start where we are. Without this, we must use full paths that start from the root of the directory
```
cd ./dir/we/want/to/be/in
```

We can also move backwards in our directories. We do this using two dots ```..``` for each level we want to go back. So this command would us from ```/dir/we/want/to/be/in``` to ```/dir/we/want/to/be``` 
```
cd ..
``` 

## Seeing what's inside

Now we are in the directory we want, and we would like to see it's contents.
```
ls -l
```
This lists the files in long format - so you can see permission, timestamps, and sizez ets. 

A useful tool is a wildcard symbol, *, which helps to list only the things we want. For example, we can use ```*``` to only list files that end in .bam, helping us search the directory more effectively

```
ls -l *.bam
```

There are many fun add-ons to the ls -l command like:
| flag | what it does |
|--|--|
| h | make's the file sizes human readable (ie KB, MB, GB) |
| t | list the files in order of when they were last modified |
| a | will list hidden files as well (files starting with .) |

## Making and removing things

Need a new folder for the result of that awesome analysis you just did?
```
mkdir dir_name
```

Need to delete an old file that folde?

```
rm file_name
```

You can also delete an entire directory (this will also delete all it's contents)

```
rm -r dir_name
```

Excellent! We can now move and groove through our files, directories in the interminal!
