# Installing and using version control git

Git is a version control system (VCS) for code. It is used to keep track of revisions and allow a developer or dev team to work together on a project through branches.

---
## Installation and Set up

1. [Download](https://git-scm.com/downloads) git.

2. Create an account on bitbucket or github:

  * [GitHub](https://github.com/) for public repositories
  * [Bitbucket](https://bitbucket.org/) for private repositories for free.


3. **Create an Online Git repository**

  Create a repository with a chosen name :
  * [GitHub](https://help.github.com/articles/create-a-repo/)
  * [Bitbucket](https://confluence.atlassian.com/bitbucket/create-a-git-repository-759857290.html)

  Repository is a way to  to share your code with your team or public.

4. Configurate SSH Key

  For security reasons SSH key is a measure to give permission to the user to modify the source code remotely.

  Every time you are in a different network, you will have to configure it.

  Follow instructions [here](https://confluence.atlassian.com/bitbucket/set-up-an-ssh-key-728138079.html) for Bitbucket or [here](https://help.github.com/articles/connecting-to-github-with-ssh/) for GitHub.

---
## Learn the basics

### how to create a project repository

After you create your repository in GitHub or Bitbucket:

1. Create a Local Project and enter the folder:
```Shell
mkdir project-local
cd project-local
```

2. To prepare your project to be a Git repository type:
```Shell
git init
```
This will create a ".git" directory with files that will start version controlling your folder.

3. Configure your global Git account
```
git config --global user.name "Firstname Lastname"
git config --global user.email username@email.com
```

4. To **link** your local directory with the repository we made at github.com or bitbucket, for example:
```
git remote add origin https://github.com/your_username/project_name
```

5. Check the status of your local repository.
```
git status
```

6. Add ALL the files to the repo :
```Shell
git add .
#or individually
git add filename1 filename2 filename3 ...
```
7. Commit tracked files to the master branch

  Commit is a common command that after you update a change in your code you will *record* it changes and take a note to what have you done:
```
git commit -m "Type here changes you've made on your work"
```
In this section, you should type changes you've made on your code so you can track them later.

8. Send files to the Git repo at github.com or bitbucket:
```Shell
git push origin master
```
---
## Git Ignore

Create a file named ".gitignore"
---
## New Branches
If you have one issue or a **BRAND NEW FEATURE THAT WILL REVOLUTIONIZE THE WORLD** and don't want to mess with the main code (MASTER), is good to create a branch for this code:

1. Create new branch
```Shell
git branch example
```
2. Start working on your new branch
```Shell
git checkout example
```
3. [*On the new branch*] to commit the branches:
```Shell
git push origin example
```

---

## Merging Branchs
After your tasks on branch are over, you will have to merge the changes on the **master** branch, to do so":

1. checkout to master
```Shell
git checkout master
```
2. merge branch on the master:
```Shell
git merge example
```
3. push your change to the repository:
```Shell
git push origin master
```

---
## Cloning a git repository
Sometimes you will have to clone a repository, i.e get the repository locally:
1. define your repository path:
```Shell
cd path/to/repository
```
2. in the github or bitbucket copy the https path protocol:
  * GitHub
![github](img\git\github_clone.PNG)
  * bitbucket
![bitbucket](img\git\bitbucket_clone.PNG)

3. now just clone it:
```
git clone git://github.com/schacon/grit.git
```
---
## If you're not up to date with the origin

Here are a few useful commands to help you with that.

If you want to **cancel** your last commit:
```Shell
git reset --hard origin/master
```
#### **<< edit files as necessary >>**
---
To  Pull origin files:
```
git pull origin master   
```
Important: pull the origin of the branch you are currently working on, it is not necessarily the master branch.


## bibliography

* [GIT Documentation](https://git-scm.com/book/en/v2)
* [Bitbucket](http://bitbucket.org)
* [Github](https://github.com/)
