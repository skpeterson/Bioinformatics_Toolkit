# UNC_Longleaf

High performance computing at UNC happens on several clusters, one of which is Longleaf. Longleaf is a linux-based computing system with resources managed through a fair-share algorithm using SLURM as the resource manager.  

For more thorough documentation on please visit the official documentation here: https://help.rc.unc.edu/ where you will find information about Longleaf and well as an additional cluster called Dogwood. 

You can ssh into longleaf using your UNC credentials in your chosen terminal application on a linux based system

```
ssh -X <onyen@longleaf.unc.edu>
```
On a windows based system (like me!) I prefer to use MobaXTerm to interact with the cluster via CLI. To use MobaXTerm,  use the session icon to create a Longleaf SSH session using longleaf.unc.edu for "Remote Host" and your onyen for the "username". Leave port at 22. 

Great!!! You're in!!

Let's talk about some basics. First, Longleaf is a module based computing system, to view the available modules, type 
```
module avail
```
and to view the versions of module or search within module space if you don't know the exact name of the module you want 
```
module spider <<module_name>>
```

To access and use modules, we simply need to load them into our environment, using the load command 
```
module load <<module_name>>
```

To get started working on longleaf, begin a tmux session with 
```
tmux new -s <<session_name>>
```

A couple of notes on tmux sessions. First, they are useful because they allow you're interactive sessions to keep running even when you disconnect.This allows you to work on a remote system (longleaf) without worrying about maintaining the SSH connection we made. To detach from a tmux session (but keep the tmux session running in the background) type ctrl + b, d. Then when you're ready to re-connect, you can use 
```
tmux at -t session_name
```
**Note: You'll need to be on the same node you initialized the session from, if you're not, you can type (change the -login# accordingly  
```
ssh onyen@longleaf-login4
```

Up until now we have been working on a log-in node, which is fine for moving small files, and cd-ing around directories. We however, cannot do any computation on the log-in nodes as they don't have enough resources. We can get assigned to a node by starting an interactive session using the following command 
```
srun -t 5:00:00 -p interact -N 1 -n 1 --mem=8g --x11=first --pty /bin/bash
```

this will start an interactive session where:
-t 5:00:00 = 5 hour session, HH:MIN:SEC \
-p interact = the type of node, in this case, an interactive  node \
-N 1 = how many nodes do you want, in this case, one compute node \
-n 1 = how many computers you want on that node, in this case, 1 \
--mem = 8g of memory allocated \
--pty bash = pseudo terminal to run bash scripts in \

I personally don't like to have to remember this command, so instead, I made a script which contains only that line, saved it as start.sh (run_script), and run it (only once you'll need to make the script executable using chmod +x start.sh) 
```
bash start.sh
```


To summarize, you have now
1. Logged into longleaf
2. Loaded modules 
3. Started a tmux session
4. Started an interactive session

You are now ready to kick off jobs and do stellar computational work! Happy science-ing!!


