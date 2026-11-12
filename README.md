EXPERIMENT 1

git --version
git config --global user.name "Your Name"
git config --global user.email "your@email.com"
git config --global --list
mkdir Gitlab
cd Gitlab
git init
ls -a
git status
touch program1.txt
git status
nano program1.txt
git status
git add program1.txt
git status
git commit -m "VERSION 1"
git log
git log --oneline
git show HEAD
nano program1.txt
git status
git diff
git add program1.txt
git commit -m "VERSION 2"
nano program1.txt
git commit -am "Update semester"


EXPERIMENT 2

cd Gitlab
git log --oneline
git branch
git branch feature-branch
git branch
git checkout feature-branch
git branch
ls
nano file1.txt
git status
git add file1.txt
git status
git commit -m "This file is created in feature-branch"
git log --oneline
git checkout master
git branch
git log --oneline
ls
git merge feature-branch
git status
ls
git log --oneline
git log --oneline --graph --all
git branch
git branch -v
git branch --merged
git branch -d feature-branch
git branch


EXPERIMENT 3

cd Gitlab
git log --oneline
git branch
git checkout feature-branch
git branch
ls
nano student.txt
git status
git stash save "My temporary changes on student.txt"
git status
git stash list
git checkout master
git branch
ls
git stash list
git add .
git stash apply
git status
ls
cat student.txt
git stash list
git stash drop
git stash list
git stash clear


EXPERIMENT 4

cd Desktop
mkdir Experiment4
cd Experiment4
git clone https://github.com/YourUsername/Experiment4.git
ls
cd Experiment4
git status
git remote -v
ls
cat README.md


EXPERIMENT 5

cd Desktop
cd Experiment4
cd Experiment4
pwd
ls -a
git branch
git status
git remote -v
git switch main
git pull origin main
notepad local-notes.txt
git add local-notes.txt
git commit -m "Add local notes for Experiment 5"
git log --oneline
git fetch origin
git status
git branch
git rebase origin/main
git log --oneline
git push origin main


EXPERIMENT 6

cd Desktop
cd Experiment4
cd Experiment4
pwd
ls -a
git status
git branch
git remote -v
git pull origin main
git branch feature-branch
git switch feature-branch
notepad book-search.txt
git add book-search.txt
git commit -m "Add book search feature"
git log --oneline
git switch main
git branch
git merge --no-ff feature-branch -m "Merge book search feature"
git status
git show HEAD
git branch --merged
git push origin main
