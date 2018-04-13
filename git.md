# Installing and using version control git

Git is a version control system (VCS) for code. It is used to keep track of revisions and allow a developer or dev team to work together on a project through branches.

---
## Installation and Set up

1. [Download](https://git-scm.com/downloads) git.

2. Create an Online Git repository

You can create your account on [GitHub](https://github.com/) for public repositories or [Bitbucket](https://bitbucket.org/) for private repositories for free.


3. Configurate SSH Key

Follow instructions [here](https://confluence.atlassian.com/bitbucket/set-up-an-ssh-key-728138079.html) for Bitbucket or [here](https://help.github.com/articles/connecting-to-github-with-ssh/) for GitHub.

---
## Learn the basics

1. Create a Local Project
```
mkdir project-local
```

2. Start Git
```
git init
```
3. Configure your global Git account
```
git config --global user.name "Firstname Lastname"
git config --global user.email username@email.com
```

4. Hook up local directory with the repo we made at github.com or bitbucket, for example:
```
git remote add origin https://github.com/you/project
```

5. Check the status of your local repository.
```
git status
```
6. Add ALL the files to the repo.
```
git add .
```
7. Commit tracked files to the master branch
```
git commit -am "Type here changes you've made on your work"
```
In this section, you should type changes you've made on your code so you can track them later.

8. Push the files to the Git repo at github.com.
```
git push origin master
```

---
## New Branches

1. Create new branch
```
git branch exemplo
```
2. Start working on your new branch
```
git checkout exemplo
```
---
