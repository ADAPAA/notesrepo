## What is Github?

Github is a version control system.  
Version control system: It management system that manages the changes in the project till the end. Changes may include adding new files, modifying older files, deleting files.  
Rollback:The purpose of version control system is we can always go back to any of the previous versions at any time if we want to.      
Collaboration  
## Why version control?  
Storing versions: You don¿t have to remember or document what all are changed from one version to other version.  
Back up: All the developers will have a copy of all the files at central server. At the start of the day, they fetch all the files from central server and store it into the local machine. At the end of the day they transfer all the files to the central server.   Even in crisis, if central server is crashed, all the developers will have a local copy.   
Analyse: easy to make analysis of the project. For every version, version control system provides you with proper description of what was changed and when was it changed. It helps to analyse how the project has evolved.   
## Version control tools:   
* Git  
* Apache subversion(SVN)  
* CVS(Concurrent version system)  
* Mercurial  
* SVN and CVS are centralised version control system do not provide a local copy. All the developers will be working on central repository.  
* Git and Mercurial are the distributed version control system.  
## GIT and GITHUB:  
Git is a version control tool that allows operations like fetch, push the files to central server(repository)  
Github is a code hosting platform for version control collaboration. It is a company that allows you to host your central repository in a remote server.  
## Features of GIT:  
### Distributed:  
 The project is distributed over different places. Each of the developer may work from different locations of the world.  
### Compatible:   
if you want to migrate from other version control system say SVN to Git, you don¿t have to transfer all the files to git. But you can use the same SVN central repository as Git central repository. Git is compatible with existing systems and protocols like ssh. So you don¿t have to change lot of things when migrating  
### Non-linear:  

 Git records the current state of project by creating a tree graph from index. It facilitates non-linear by branching
### Branching:  
 Git is the only one which has branching model. It allows creating multiple branches of your local repository. Master branch is main branch starts from the start of the project to the end of the project and  contain the entire project.  
### Light weight:  
 Maintaining local repo, updating all the files each and every file of each version might look like lot of files but the storage is all compressed. Only when you fetch from local repository to your workspace, it is converted.when you push it again it is compressed again and stored with very minimal space.  
### Speed:  
 Since you have a local repository, you don¿t have always travel over network to get that data.  It¿s 10 times faster than other VCS according to mozilla performance test. It is faster because Git is written in C and C is very close to machine languages. It reduces all the runtime overhead.  
### Open Source:  
 Linus Torvalds creator of linux kernel, used a VCS called bit keeper. It was made paid version. So, he wrote his own vcs called git and made it open source.  
### Secure:  
 Uses SHA-1 algorithm. Once you committed, you cannot change it without knowing it to others.  
### Economical:   
Free to download. People use heavily on local repo. They use the central server only when they are sure about the work. They are not experimenting on central repo. So central repo may be very simple and does not require complex and powerful hardware. So it is economical.  
## What is repository:  
It is a directory or storage space where all your files are store.  
**Two types of repo are**  
* Local repo  
* Central repo          
**Local repo:**    
Resides on your local machine  
Resides as .git folder  inside your project folder  
Only the owner/admin i.e you can work on this.  
**Remote repo:**  
Resides on remote machine  
Resides as .git folder  
It is for sharing and exchanging data. So anyone in the team can work on it.  
## Git operations and commands:  
Create repo: git init  
Syncing repos: add origin, push, pull  
Making changes: status, add, commit  
Parallel development: branch, merge, rebase  
### Create repo:  
We need local and central repo.  
Central repo: Host the central repo on github. So create an account and create a repo.  
Local repo:  
Install git on your machine.  
**git init :** to create a local repo ff you are starting a new project  
**git clone :** to download repo from central repo if you join an ongoing project. Clones master by default  
**git clone -b branchname repo-url:** clones particular branch  
### Syncing repos:  
Link remote repo and your local repo to know which repo to push into. Remote repo is called origin  
Http method:  
git remote add origin **remote repo link**  
SSH method:  
ssh-keygen  
Generates the public key. Copy the key and paste it in the ssh keys in settings menu on the git hub.  
settings-> ssh and gpg keys -> add ssh key   
Connect to github:  
ssh -T git@github.com  
Fetch all the files from central repo to local repo:  
git pull origin master  
Fetch from master branch  
Push the chang?es to central repo. Switch to the correct branch before pushing.  
Git push   
git push origin firstbranch  
Creates a branch named firstbranch at the remote central repo and pushes all the changes from local repo to first branch.  
git push origin master  
Pushes all the changes from local repo master to central repo master  
### Making changes:  
Git has an intermediate layer between your workspace and the local repo  
If you want to commit the changes to your local repo, you have to add them to index first. You cannot commit if they are not in index. Files which are not added to index are called untracked files.  
#### git add:  
 To add files to index  
git add filename: adds the file to index  
git add -A(upper case) : to add all untracked files to index  
#### git status:  
 To see which files are in the index  
#### git commit: 
To make the changes in local rep  
git commit -m <message>: commit with message  
git commit -a(lower case) : to commit all files  
Also adds the modified file to the index if the file is added to index before. I will not add if it is not added before.  
#### git log:   
Git stores all the commits with date,time, message and other details.  
### Parallel development:  
  #### Branch:  
Why branching is needed??  
Create: git branch branchname  
Switching to the branch: git checkout branchname  
Create and switch to that branch: git checkout -b branchname  
#### List branches:  
List local branches: git branch  
List remote branches: git branch -ar  
#### Delete branch:  
Delete in local repo:  
``` $ git branch -d branchname ```  
Delete in remote repo:  
``` $ git branch origin --delete branchname ```  
#### Merging:  
Combine the work of branches to master  
Switch to the target branch by using checkout command and run the following command  
``` $git merge branchname ```  
If  you want to merge branch A to branch B, switch to b and run the command **git merge a**  
Branch a is still separate and you can again work on it if you want to. 
#### Rebase:??  
Another kind of merging.  
Integrate changes from one branch to another.   
#### Gitstash:??  
#### Revert:   
git checkout <first 8 digits of the hashcode of the version > filename  
You can get the hash code from **git log**  
Git pull and git fetch difference:??  
git pull gets all the files from central repo to master branch of your local repo.  
git fetch gets all the files from central repo to a different branch. It needs a git merge to see the changes in local repo.  
git pull = git fetch + git merge  
#### See origin:  
git  remote
            
## Tasks:
*Given a repo, how to checkout using http and ssh, kraken  
*Change files, view diff, commit , push  
*Create a branch, add files, change,view diff, commit branch, push, branch to master  
*switching/Checkout branches with and without dirty- stash  
*Pull changes from other branch and Merge to master   






Quiz 1:
https://github.com/ravicm/sandbox

Makes your sample changes in different branches and push it 
https://github.com/prudhviadapa/kube-ingress-aws-controller/tree/master

Vani repo:

https://github.com/vanim02/kube-ingress-aws-controller

??? - Delete a branch in local and remote repository but if i do git checkout < delete branch name >. Iam still gettinf the branch 

https://github.com/github




# TASK:
Create a Reo or Clone a Repo  and Create a text file(githubnotes) in the repo and Commit the file and also do the Pull request
**Step 1:-**  
    Create a Repo (or) Clone a repo
``` $git init reponame (or) git clone <URL of Repo to clone> ```
-push an existing repository from the command line  
``` $git remote add origin https://github.com/ADAPAA/notes.git ```  
```    $git push -u origin master```  
**Step2:-**  
    Create a Branch for the Master in Repo.  
     ```  $git branch branchname```  
**Step3:-**  
Move to the branch and work on it.  
``` $git checkout branchname ```  
**Step4:-**  
     Create a File in that Branch 
     ``` $vi filename.txt```   
**Step5:-**  
Know the status of the file whether the file is in index or what's the status actually.  
``` $git status ```  
**Step 6:-**    
    Add all new/modified (untracked) files in the current directory and all subdirectories to the Index,this preparing them to be included in the next commit.  
   ``` $git add filename```  
**Step7:-**  
      Commit  record your changes to the local repository.
   ``` $git commit```  
**Step8:-** To updtae from local to remote  
  ``` $git push  <REMOTENAME> <BRANCHNAME> ```  
**Step9:-** Create Pull request with the number of reviews and protect the origin master  
**Step10:-** Once done with pull request sent it for Merge Pull request and select the merge pull request(Create a merge Commit,Squash and merge,Rebase and merge).

  
  Push Request  done successfully :+1:
