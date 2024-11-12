# NextFlow_UNC_Longleaf

High performance computing at UNC happens on several clusters, one of which is Longleaf. Longleaf is a linux-based computing system with resources managed through a fair-share algorithm using SLURM as the resource manager.  

For more thorough documentation on please visit the official documentation here: https://help.rc.unc.edu/ where you will find information about Longleaf and well as an additional cluster called Dogwood. 

You can ssh into longleaf using your UNC credentials in your chosen terminal application on a linux based system

```
ssh -X <onyen@longleaf.unc.edu>
```
On a windows based system (like me!) I prefer to use MobaXTerm to interact with the cluster via CLI. To use MobaXTerm,  use the session icon to create a Longleaf SSH session using longleaf.unc.edu for "Remote Host" and your onyen for the "username". Leae port at 22. 


Great!!! You're in!!

To get started working on longleaf, begin a tmux session with 
```
tmux new -s session_name
```
