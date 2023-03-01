# GitGuide
Guide to using git/github for the signaling systems lab, written by Allison. A basic introduction is given below, and more advanced uses will be described [within](./Advanced.md) (once I get around to doing that).

## Why use Git?
Git has three main uses for our lab: public accessibility of code, version control, and collaboration. Previously, most lab members have commited repositories of completed code for availability to the public. Though this is useful, continued use of git throughout a project also provides the advantage of version control.

With git's version control, you can always recover previous commits. If you write functioning code, commit to a repository, then break your code, you can recover your previous version. You can also have different versions of your code on different "branches" at any given time. (It's good practice to have one main/master branch with the last functioning version of your code and a separate branch with edits that you merge into your main branch later. This is described in the [advanced file](./Advanced.md)) Git is also useful for collaboration with other lab members and other scientists outside of our lab, which is described in the [advanced file](./Advanced.md).

Though git is useful, it has a bit of a steep learning curve, especially when it comes to branching. It is possible to use git for backups and some version control without using different branches.

## Getting started
### Setup
If you don't already have one, create a Github account. This will be your own personal account, and you will use these account credentials to create/edit/commit to repositories. Set and confirm your primary email address. See Allison to add your account as a member of the signaling systems lab organization.

Next, set up git on your computer. (More info [here](https://docs.github.com/en/get-started/quickstart/set-up-git).) First, [download and install git](https://git-scm.com/downloads). You can then set your user name. This is the name that will appear next to your commits on github. On a Mac/Linux, open your terminal. (On windows, open Git Bash. I think it's a terminal emulator, but I don't know much about this.)
```
$ git config --global user.name "Signaling Bruin"
```

Next, add your email address to associate your commits with your github account.

```
$ git config --global user.email "s.bruin@ucla.edu"
```

You will authenticate your account once you clone or push a repository.

### Step 1. Create a repository on github
#### Personal Repository
You want to create a new repository on github, then initialize the repository in your terminal.
1. Go to https://github.com/ and click the green "new" button
2. Give your repository a name (think carefully about this -- you can't change it!) and a description
3. You can make your repository public or private. This setting can easily be changed later.
4. Press "Create Repository". 
5. Continue to Step 2

#### Signaling Systems repository
All final code should be in the Signaling Systems organizational account. One way to accomplish this is to create a repository within the Signaling Systems organization, instead of in your personal account. This can be done easily as well.
You want to create a new repository on github, then initialize the repository in your terminal.
1. Go to https://github.com/orgs/signalingsystemslab/repositories and click the green "new repository" button
2. Give your repository a name (think carefully about this -- you can't change it!) and a description
3. You can make your repository public or private. This setting can easily be changed later.
4. Press "Create Repository". 
5. Continue to Step 2

### Step 2. Initialize a repository on your computer
We will continue as if the URL of your new repository is ```https://github.com/s.bruin/first_repo```

Navigate to your directory of interest in your terminal. 
#### Brand new directory
If it is a brand new directory, you will want to create a README file with instructions.
```
$ git init
$ git add README.md
$ git branch -M main
$ git remote add origin "https://github.com/s.bruin/first_repo"
$ git status
$ git commit -m "first commit"
$ git push -u origin main
```
```git init``` initializes the repository on your computer (referred to as "local"). ```git add README.md``` tells git that you would like to track the file named README.md. Github also has a feature where it will display the content in your README.md when you or others view your repository on github. ```git branch -M main``` renames your primary branch. Git lets you make separate "branches" of your repository that can each contain separate versions of your code. The default branch is called "master", but we like to rename it to "main". Working with different branches will eventually be explained in the [advanced file](./Advanced.md)) ```git status``` asks git to show you the status of your working tree. You should expect to see something like the following:
```
On branch main
Your branch is up to date with 'origin/main'.

Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
	new file:   README.md
```
```git commit -m "first commit"``` "commits" your change to git's memory, permanently storing it with a specific hash (unique ID) so that it can be directly referenced, restored, reversed, etc. in the future. ```git push -u origin main``` pushes your changes to the "origin", which is your github repository. 

### Existing directory
If it is an existing directory, you will want to add all the files that you want git to track. Let's say you have a subdirectory containing all your important code, titled ```simulation_code```. 
```
$ git init
$ git add simulation_code/
$ git branch -M main
$ git remote add origin "https://github.com/s.bruin/first_repo"
$ git status
$ git commit -m "simulation_code commit"
$ git push -u origin main
```
```git init``` initializes the repository on your computer (referred to as "local"). ```git add README.md``` tells git that you would like to track the file named README.md. Github also has a feature where it will display the content in your README.md when you or others view your repository on github. ```git branch -M main``` renames your primary branch. Git lets you make separate "branches" of your repository that can each contain separate versions of your code. The default branch is called "master", but we like to rename it to "main". Working with different branches will eventually be explained in the [advanced file](./Advanced.md)) ```git status``` asks git to show you the status of your working tree. You should expect to see something like the following:
```
On branch main
Your branch is up to date with 'origin/main'.

Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
	new file:   simulation_code/code1.R
  	new file:   simulation_code/code2.py
  	new file:   simulation_code/code3.cpp
  	new file:   simulation_code/code_wrapper.sh
```
```git commit -m "first commit"``` "commits" your change to git's memory, permanently storing it with a specific hash (unique ID) so that it can be directly referenced, restored, reversed, etc. in the future. ```git push -u origin main``` pushes your changes to the "origin", which is your github repository. 
### Cloning an existing repository
Often, you want to make changes to someone else's code, or you want to be able to access your code from different computers or servers. To do this, you can clone an existing respository onto your local computer or server.
```
$ git clone "https://github.com/s.bruin/first_repo"
```
Be careful when you are working on a repository on different computers (collaborating with yourself). It's easy to make conflicting changes and a minor headache to unravel them, though if you have committed regularly and properly it is always possible. To avoid this, follow this order whenever you make changes: pull all new changes (even if you don't think there are any, it can't hurt!), make your desired changes, then commit and push.
```
$ git pull 
# make changes
$ git commit -m "message about commit"
$ git push -u origin main
```

## Publishing final code
When you submit a paper, make sure all your code is in a Signaling Systems repository. If you already had a Signaling Systems repo, make sure it's updated with current versions of everything. If you previously had a personal repository, you can always add your personal repositories to the organizational account by forking or [transfering the repository](https://stackoverflow.com/questions/8157615/github-how-do-i-add-my-own-projects-to-an-organization-account). 

If you have finalized code on your computer but have not made a Github repository, follow the instructions above to create a repository [within the Signaling Systems organization](Signaling-Systems-repository). Add files by clicking `Add file`>`Upload Files` or initialize your repository from the command line.


### Recovering previous version
https://git-scm.com/book/en/v2/Git-Basics-Undoing-Things
## Other resources
[Git cheat sheet](https://training.github.com/downloads/github-git-cheat-sheet.pdfhttps://training.github.com/downloads/github-git-cheat-sheet.pdf)

[Git commands and explanations](https://git-scm.com/docs)

[Github Guide to Git](https://github.com/git-guides)
