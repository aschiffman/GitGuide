# GitGuide
Guide to using git/github for the signaling systems lab, written by Allison. A basic introduction is given below, and more advanced uses are described [within](./Advanced.md).

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

### Create a repository on your computer

### Committing to a repository

### Create a repository on github

### Recovering previous version

## Other resources
[Git cheat sheet](https://training.github.com/downloads/github-git-cheat-sheet.pdfhttps://training.github.com/downloads/github-git-cheat-sheet.pdf)
