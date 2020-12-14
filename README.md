# Welcome to Some Learning and Development

This repo should be used to do some basic L&D around DevOps activities.

### What You Will Need
* A discardable github account (e.g. one using a discardable email maybe) that you can delete when you're done with these exercises.
* A personal computer able to run Bash e.g. a Linux distro like Ubuntu, a Mac or a modern version of Windows that can run a Linux VM, WSL or Docker.
* **git** installed on that computer (on ubuntu this is `apt install git`, **be sure to update your git config username and email with the git hub account you created above**)

#### Exercise 1
1. From your Bash terminal clone this repo to your local machine. Cloning using the [https link](https://github.com/paxide1383/Learn.git) means you won't have to setup an SSH key, but will require you to enter username and password for pushes (which is preferable here).
2. Create and checkout a new branch from the master repo, use the branch naming convention: deploy/username_Ex1
3. Add a new text file into the directory called Ex1_Space with a name based on today's date e.g. 13Dec20.txt
4. Commit this change to the branch and push the branch back up to GitHub.
5. Create a pull request to have your new branch merged to become the master branch.

**Hints**
To complete this you will need to configure Git global options on your computer and you may need to research some Git commands like git clone, git status, git merge, git stash, git pull, git checkout, git branch, git add, git commit, git push...

*Remember*, the fundamental idea is to version control the master branch and so the basic workflow is to:
1. create a branch either at the repo or after cloning
2. do all necessary updates to the branch
3. push the branch back up to the repo
4. create a 'Pull Request' so others can review your updates and approve the PR so your branch is merged to the master or reject it if there are issuess with it.

[See this Git guide](https://www.freecodecamp.org/news/learn-the-basics-of-git-in-under-10-minutes-da548267cc91/)


Understanding version control and associated tools like Git is a fundamental of running in a known STATE and being able to return to that state if changes are made. It's worthwhile setting up a daily workflow that builds good behaviours towards doing this habitually.

### When you're ready, move on to [Exercise 2 on Docker in this guide](https://github.com/paxide1383/Learn/blob/master/Ex2_Docker/README.md)
