There are 3 Stages of code in local repository

- Working Directory

- git add .
code entered in staging area
- git commit -m "added code "
code added in local repository
-git push 
code added in remote repository

## Below are the Steps for getting started with git and pushing those changes in remote repo.

`To sets the author name and email address respectively to be used with your commits.`

git config --global user.name <username>

git config --global user.email <email>

- `Creating a Directory`
 
mkdir my-data

- `Navigating to Directory`
 
cd   my-data

- `Initialize the Repository`
 
git init

- `Create the Sample File`
 
touch sample.txt

- `Check the Untracked / Tracked Files`
 
git status

- `Add the files from your working directory to Staging Area (specific file)`
 
git add sample.txt

OR 

`Add the files from your working directory to Staging Area(all files)`
 
git add .

- `Save Changes to Your Local Repository and Capture a Snapshot of staged changes`
 
git commit -m "Your message here"

-`To Display the commit value and shows the history of local repository`
 
git log

-`Now Add our Google Cloud Source Repository`
 
Create a Repository in Google Cloud from the below command or for Console.

> Go to Github>> Click on Create new  Repo
> Decide to make it Public or Private
> Add Description
> Click on Create

- Go to Local machine

- Create a Folder

 mkdir data

- initialise Git in that Folder

 git init

- Add your remote repository url

git remote add origin https://github.com/<your username>/<your repo name>.git


` To set the Remote Upstream`
 
> git push --set-upstream origin master

> git push -u origin master
 
`Do some changes in file and push in repo`
 
nano sample.txt
add some content > "hello v1"

git add sample.txt
 
git commit -m "added hello v1"
 
git push

`To Create a New Branch and Switch to branch`
 
git checkout -b dev

`To Switch to another / Master Branch`
 
git checkout master

` Merge the Changes to master `
 
git merge dev

` To see  the Branches `
 
git branch

` To Delete the Branch `
 
git branch -d dev

` To Pull the Latest Code on repository`
 
git pull

` To revert any commited changes`
 
- git log
- git revert <commit_id>

`clone the existing repository`
 
- git clone  <your remote repo name>
- git add 
- git commit -m "your message"
- git push 


## Dont Track Certain files
- touch .gitignore
Add this files to your project(root Directory)
To exclude certain folders or files from git to be tracked 
like pycache, .class files, lib , .cache .env, nodemodules
folders - build/

## To remove files from staging Area
git restore --staged <filename>   ( for specific file)
git restore --staged .            ( for all current staged files.)

## To remove specific commit 
git reset --hard 

## To Stash your incomplete work and to move to another branch / Save WIP changes
if dev branch has  local changes , and you dont want to commit those changes, and want to move into another branch say master.
-your current branch -> Dev
-your incomplete work
-you  do `git stash` to save your incomplete work in temporary memory
-now your work is saved 
-move to another branch say master
-git checkout master
-again come to your Dev branch 
-type `git stash pop` start your work where you left off.

Thank you
 

it will take your local changes and store temporary.

>> git checkout master
>> git checkout master

git stash pop

now you can get back to your work and continue.

I will add more content like 
git reset,  git cherry-pick , git reset --hard HEAD~n etc

Thank You
 
 

