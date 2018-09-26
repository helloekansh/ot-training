# Assignment1:

1) Create a script to generate a mearge conflict.
```
#!/bin/bash
mkdir gittest
cd gittest
git init
touch f1
cat > f1
git add f1
git commit -m "master commit"
git branch ninja
git checkout ninja
cat > f1
git add f1
git commit -m "ninja commit"
git checkout master
cat > f1
git add f1
git commit -m "master final commit"
git merge ninja

```
2) Create muliple braches and push changes for each branch into remote repo.
```
mkdir gitrepo
   cd gitrepo
   git init
   echo "add content here" >> README.md
   git status
   git add README.md
   git commit -m "first commit"
   git status
   git remote add origin https://github.com/helloekansh/test.git
   git push -u origin master
   git branch n1
   git branch n2
   git branch
   git checkout n1
   touch f1.txt
   git add f1.txt
   git commit -m "added f1.txt file"
   git checkout n2
   touch f2.txt
   git add f2.txt
   git commit -m "added f2.txt file"
   git checkout master
   git push -u origin n1
   git push -u origin n2

```
3) Create a script to clone remote repo and check out all existing remote branch.
```
#!/bin/bash
mkdir clone
cd clone 
git clone https://github.com/helloekansh/test.git
git ls-remote

```
4) Clone a particular folder from a remote repo.
```
mkdir git-completion
cd git-completion
git init
git remote add -f origin https://github.com/helloekansh/test.git
git config core.sparsecheckout true
echo "some/dir/" >> .git/info/sparse-checkout
git pull origin master

```

# Assignment2:

1) Use both https and ssh protocal to clone your remote repo.
- Create a key using ssh-keygen
- copy your public key to github -> settings -> ssh and gpg keys -> new ssh key -> paste your ssh key here
- Now clone using ssh

2) Change your working copy into a clonable remote repo
```
on remote machine firstly we create a directory with .git extention. Then initialize it with  the command 
git init --bare : A bare repository created with git init --bare is for sharing.

Commands perform on remote machine side

cd /var/local/git
mkdir myrepo.git
cd myrepo.git
git init --bare

On local machine side (user side)
git remote add origin ssh://user@host/var/local/git/myrepo.git
git push -u origin master
```
3) Ignore backup, swp and pyc file from being commited.
```
move into git folder
mkdir .gitignore 
$ git config –global core.excludefile ~/.gitignore
cd .gitignore
cat > .gitignore
*.swp
*.pyc
*.tar.gz
touch a.swp b.pyc	
git add .
git status
git commit -m “does not commit file with extensions .swp , .pyc, .tar.gz ”

```
