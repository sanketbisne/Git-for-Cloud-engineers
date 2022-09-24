<h3> Hey Everyone , In this Repository I have covered some Basic Git Commands that are used Daily For the Job Role of Cloud / DevOps Engineer. </h3>
-------------------------------------------------------------------------------------------------------------

We will Start by What is Git to Pushing our very First code to Remote Repository

What is Git?
Git is a Version Control System to Track our Code and will keep a track of records of who changes what and when?

What is Github / GitLab / Bitbucket / Google Source Repository / CodeCommit
So Simply, these are all Remote Repository to Host Our Code

Google Source Repository and Amazon CodeCommit and Private Repository which are been used and are restricted and accessed securely by giving IAM Roles on  project.

Before Hosting Our Code on Remote Repository , We can to Run that Code Locally on our VM or Our PC.

After the code is initialized , added and commited , then the code can be pushed to any remote repository.

As Everyday we use only 3 commands  to be frank, ie

- git add
- git commit 
- git push

But git is more beyond that , and understanding Basic concepts properly will give you edge over others and make you a good engineer.

So basically there are 4 Stages of code in local repository

  1. Working Directory
  2. code entered in staging area
  3. code added in local repository
  4. code added in remote repository

## Below are the Steps for getting started with git and pushing those changes in remote repo.

Installing Git in Linux

First step is to open a terminal and install Git by using the below command:

`sudo apt install git`

Confirm the git installation by checking for a git version:

`git --version`

To set the author name and email address respectively to be used with your commits.

`git config --global user.name "your name"`

`git config --global user.email "your email"`

Open your terminal on VM / Linux / or Gitbash

- Creating a Directory

   `mkdir my-data`

- Navigating to Directory

   `cd  my-data`

- Initialize the Repository

   `git init`

- Create the Sample File

   `touch sample.txt`

- Check the Untracked / Tracked Files
 
   `git status`

- Add the files from your working directory to Staging Area (specific file)
 
   `git add sample.txt`

OR 

  Add the files from your working directory to Staging Area(all files)
 
   `git add .`

- Save Changes to Your Local Repository and Capture a Snapshot of staged changes
 
  `git commit -m "Your message here"`

- To Display the commit value and shows the history of local repository
 
  `git log --oneline --graph `

- Now Lets add our remote repo
 
  Create a Repository in Google Cloud / Gitlab / Github / BitBucket from the below command or for Console.

> Go to Github

> Click on Create new  Repo

> Decide to make it Public or Private

> Add Description

> Click on Create

- Go to Local machine

- Add your remote repository url

  `git remote add origin <https://github.com/<your username>/<your repo name>.git>`

- Or You can Clone your existing Repository by automatically upstream is set when you clone repo 

  `git clone < repository url>`

- To set the Remote Upstream because Remote Repo doesn't know about your branch.

  git push --set-upstream origin master
 
  git push -u origin master
 
- Do some changes in file and push in repo
 
  `nano sample.txt`
- add some content > "hello v1"

  `git add sample.txt`

  `git commit -m "added hello v1"`

  `git push`

- To Create a New Branch and Switch to branch`
 
  git checkout -b dev

- To Switch to another / Master Branch
 
  `git checkout master`

- Merge the Changes to master
 
  `git merge dev`

- To see  the Branches
 
  `git branch`

- To Delete the Branch
 
  `git branch -d dev`

- To Pull the Latest Code on repository
 
  `git pull`

- To revert any commited changes`
 
  `git log`

` git revert <commit_id>`

- clone the existing repository
 
 ```

 git clone  <your remote repo name>
 git add 
 git commit -m "your message"
 git push 

 ```


## Dont Track Certain files

- touch .gitignore

Add this files to your project(root Directory)

To exclude certain folders or files from git to be tracked 
like pycache, .class files, lib , .cache .env, nodemodules
folders - build/

## To remove files from staging Area

- git restore --staged <filename>   ( for specific file)
- git restore --staged .            ( for all current staged files.)

## To remove commit  and delete by one

- git reset --hard HEAD~1

## To remove commit  and move back to staging area

- git reset --soft HEAD~1

## To remove specific commit  and delete it

- git reset --hard <commit id >

## To Stash your incomplete work and to move to another branch / Save WIP changes

if dev branch has  local changes , and you dont want to commit those changes, and want to move into another branch say master.

- your current branch -> Dev
- your incomplete work
- you  do `git stash` to save your incomplete work in temporary memory
- now your work is saved 
- move to another branch say master
- git checkout master
- again come to your Dev branch 
- type "git stash pop" start your work where you left off. and now you can get back to your work and continue.

Thank you
 
## Git Rebase

If we have 2 branches dev and master and we want dev branch should take the latest code from master branch, instead of merging again and again , we can rebase the dev with master.

now after Rebase , dev branch contain all the recent changes that master branch has

if we are in dev branch, then type

" git rebase master "

When we rebase, we are copying commits from one branch to another.
So we are generally modifying the git history , as new hash is created.

 
Also git rebase allows us to modify the git history on certain branch before rebasing.

if suppose many commits are there on specific branch, then we can combine them into one specific commit.

"git rebase -i HEAD~4"
```

pick <hash> Added 2nd line
pick <hash> changes to 2nd line
pick <hash> more changes to 2nd line
pick <hash> started 2nd story

```

Here we can see pick option , we need to replace pick with the below lines.

```

pick <hash> Added 2nd line
squash <hash> changes to 2nd line
squash <hash> more changes to 2nd line
squash <hash> started 2nd story

```
save the changes and exit.


now the squash commits -> will be merge with 1st pick  and new specific commit will be created.


## Cherry Pick

if we are having specific commit on a different branch, and we want to copy that specific commit into another branch, so in that case cherry pick comes into picture.


Go to master -> git checkout master, git log --oneline , copy the commitid.

Go to Dev branch -> git checkout Dev, then git cherry-pick <commit id>

that's it.