# Github First Step Project

This project will keep track on my learning progress concerning git / github.

Assumptions:
- windows 8.1 machine
- chocolatey already installed

1. Create this Readme.md
create a directory named `githubFirstStep` and create this file
```
mkdir githubFirstStep
cd githubFirstStep
edit README.md
```

getting git for windows https://msysgit.github.io/
```
choco install git -y
```

Initialize the local directory
and stage files for the first commit
```


git init
git add .
git commit -m "First commit"
git remote add origin git@github.com:evobatch/githubFirstStep.git
git push -u origin master
```

first, I cancelled push because of this message `the authenticity of host can't be established`
--> check fingerprint is 16:27:ac:a5:76:28:2d:36:63:1b:56:4d:eb:df:a6:48 and add it to your known_hosts

From now on i use Git Bash
create ssh key
ssh-keygen -t rsa -C "your_email@example.com"

start ssh agent
eval $(ssh-agent -s)

add the whole key to it
ssh-add ~/.ssh/id_rsa

copy to clipboard the public key
clip < ~/.ssh/id_rsa.pub
go to setting add sshkey and paste it


2. Create a new repo on github

click on add a new repo, set the name, make it public.

Install Beyond Compare has the comparing tool
git config --global diff.tool bc4
git config --global difftool.bc4.cmd "\"c:/program files (x86)/beyond compare 4/bcomp.exe\" \"$LOCAL\" \"$REMOTE\""
git config --global merge.tool bc4
git config --global mergetool.bc4.cmd "\"c:/program files (x86)/beyond compare 4/bcomp.exe\" \"$LOCAL\" \"$REMOTE\" \"$BASE\" \"$MERGED\""
git config --global mergetool.bc4.trustExitCode true



Git Fundamentals

3 configuration file : 
git config --system --list
git config --global --list       ~/.gitconfig   
git config --list                 


git config --global user.name "myname"
git config --global user.email "developer@evobatch.com"
git config --global core.editor "C:/Program Files (x86)/GitExtensions/GitExtensions.exe"
git config --global core.editor "'C:/Program Files/Sublime Text 3/subl.exe' -w"
git config --global help.autocorrect 1
git config --global color.ui auto
git config --global core.autocrlf true
true when working on a cross platform project, false when only windows
git config --unset core.autocrlf will remove this property on local repo
git config --global push.default simple

add all modified files (including deleted ones)
git add -u
git diff cd2f1d..00f8ea
git diff HEAD~1..HEAD
git diff HEAD~1..

add all new files and remove deleted ones
git add -A

revert changes
git checkout README.md
git reset --hard
git reset --soft HEAD~1  (all changes will become staged changes)

// remove untracked files
git clean -n
git clean -f