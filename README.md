# Welcome to Some Learning and Development

This repo should be used to do some basic L&D around DevOps activities.

Please feel free to contribute to this by adding new exercises, links to good quality information pages plus improvements around making these notes inclusive and relevant.

### What You Will Need
* A discardable github account (e.g. one using a discardable email maybe) that you can delete when you're done with these exercises.
* A personal computer able to run Bash e.g. a Linux distro like Ubuntu, a Mac or a modern version of Windows that can run a Linux VM, WSL or Docker.
* **git** installed on that computer (on ubuntu this is `apt install git`), **be sure to update your git config username and email with the git hub account you created above**)

#### Exercise 1
1. From your Bash terminal clone this repo to your local machine. Cloning using the [https link](https://github.com/paxide1383/Learn.git) means you won't have to setup an SSH key, but will require you to enter username and password for pushes (which is preferable here).<br>
Command: `git clone https://github.com/paxide1383/Learn.git`
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

In addition, setlling on some particular text editor(s) or IDE is a good idea. There are a range of options here and the process can be more involved than picking one, downloading it and installing. Some are  run from a terminal window (Vim, eMacs), some are GUI driven (Atom, Sublime, Notepadd++, Notepad) and some are closer to programmatic development environments (MS Visual Studio Code, PyCharm, IntelliJ). It's good to invest time in familiarising yourself on these.  I think Vim and one of either Atom or Sublime are good investments, Atom has a great markdown preview package for instance which is what I'm writing this in.

## When you're ready, move on to [Exercise 2 on Docker in this guide](https://github.com/paxide1383/Learn/blob/master/Ex2_Docker/README.md)

## Alternatively...
Here are some topics along with suggested links to learning resources that can be good diving-off points for learning:

* [Git](https://www.freecodecamp.org/news/learn-the-basics-of-git-in-under-10-minutes-da548267cc91/)
* [Docker](https://www.freecodecamp.org/news/docker-simplified-96639a35ff36/) or [this great video](https://www.youtube.com/watch?v=fqMOX6JJhGo). [Docker Cheat Sheet PDF](https://design.jboss.org/redhatdeveloper/marketing/docker_cheatsheet/cheatsheet/images/docker_cheatsheet_r3v2.pdf)
* [Ansible](https://linuxhint.com/ansible-tutorial-beginners/) or [this getting started](https://docs.ansible.com/ansible/latest/network/getting_started/first_playbook.html)
* [Python Tutorials](https://realpython.com/) or [Automate the Boring Stuff](https://automatetheboringstuff.com/)
* [Prometheus & Grafana](https://prometheus.io/docs/prometheus/latest/getting_started/) or [PromQL Cheat Sheet](https://promlabs.com/promql-cheat-sheet/)
* [Elastic/ELK Getting Started](https://www.elastic.co/guide/en/elastic-stack-get-started/current/get-started-elastic-stack.html) or [This Intro Guide](https://logz.io/learn/complete-guide-elk-stack/#intro)
* [Linux SysAdmin](https://www.tecmint.com/free-online-linux-learning-guide-for-beginners/) or [Linux Journey](https://linuxjourney.com/), [command line fu](https://www.commandlinefu.com/commands/browse), [pipes & streams PDF](https://www.ibm.com/developerworks/linux/library/l-lpic1-v3-103-4/l-lpic1-v3-103-4-pdf.pdf)
* [Terraform](https://learn.hashicorp.com/collections/terraform/aws-get-started?utm_source=WEBSITE&utm_medium=WEB_IO&utm_offer=ARTICLE_PAGE&utm_content=DOCS)
* [Openshift Learning Portal](https://learn.openshift.com/) or [RH Getting Started](https://developers.redhat.com/products/openshift/getting-started)
* [AWS Getting Started](https://aws.amazon.com/getting-started/)
* [Bamboo](https://confluence.atlassian.com/bamboo/getting-started-with-bamboo-289277283.html)
* [Vim Cheat Sheet](https://stackoverflow.com/questions/5400806/what-are-the-most-used-vim-commands-keypresses/5400978#5400978)
* [Github Repo full of free programming links and resources](https://denic.hashnode.dev/github-repositories)
* [Links to free repo resources for practically every subject](https://github.com/ripienaar/free-for-dev)
