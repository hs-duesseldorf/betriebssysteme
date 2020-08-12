- [How to save your code with git and GitHub](#how-to-save-your-code-with-git-and-github)
  - [First Time Setup](#first-time-setup)
    - [1 - Create GitHub Account](#1---create-github-account)
    - [2 - (Optional) Create GitHub private repository](#2---optional-create-github-private-repository)
    - [3 - Create local directory](#3---create-local-directory)
    - [4 - (Optional) Open with VsCode](#4---optional-open-with-vscode)
    - [5 - (Optional) Install Microsoft C/C++ Extension](#5---optional-install-microsoft-cc-extension)
    - [6 - Open in terminal and setup git credentials](#6---open-in-terminal-and-setup-git-credentials)
    - [7 - (Optional) Init git repository](#7---optional-init-git-repository)
    - [8 - (Optional) Add remote](#8---optional-add-remote)
    - [9 - (GUI Alternative) Publish to GitHub](#9---gui-alternative-publish-to-github)
  - [Repetive steps](#repetive-steps)
    - [git add](#git-add)
    - [git commit](#git-commit)
    - [git push](#git-push)
    - [(GUI Alternative) With the VsCode source control UI](#gui-alternative-with-the-vscode-source-control-ui)
- [Internship 01](#internship-01)
  - [Learning Linux bash basics](#learning-linux-bash-basics)
    - [mkdir](#mkdir)
    - [cd](#cd)
    - [pwd](#pwd)
    - [cp](#cp)
    - [ls](#ls)
    - [more & tail](#more--tail)
    - [mv](#mv)
    - [rm](#rm)
    - [cat](#cat)
  - [Create a C program that returns its arguments](#create-a-c-program-that-returns-its-arguments)
  - [compile](#compile)
  - [run](#run)

# How to save your code with git and GitHub

## First Time Setup

### 1 - Create GitHub Account

![01_create_github_account](images/01_create_github_account.png)

### 2 - (Optional) Create GitHub private repository

If you plan to use only the command line to perform git commands, use this step to create a repository in your GitHub space. If you plan to use the source control panel from within vscode, skip this step:

![02_create_repository](images/02_create_repository.png)

### 3 - Create local directory

![03_create_local_directory](images/03_create_local_directory.png)

### 4 - (Optional) Open with VsCode

![04_open_with_other_application](images/04_open_with_other_application.png)

![04_open_with_vscode](images/04_open_with_vscode.png)

### 5 - (Optional) Install Microsoft C/C++ Extension

If you want to have code completion and synthax check, you may install the official C/C++ VsCode extension from Microsoft:

![05_install_cc_pp_extension](images/05_install_cc_pp_extension.png)

### 6 - Open in terminal and setup git credentials

![06_open_in_terminal](images/06_open_terminal.png)

*Alternatively, if you do not want to use VsCode for this, you can press **CTRL + SHIFT + T** to open a new terminal in Ubuntu.*

Enter your GitHub git username and email into the terminal with
```bash
git config --global user.name YOUR_USERNAME
git config --global user.email YOUR_USER_EMAIL
```

so everytime you make a git commit, your username and email will be written into this commit.

### 7 - (Optional) Init git repository

Initialize your new local git repository with __EITHER__ using the git init command:
```bash
git init
```

__OR__ by using the VsCode source control section form the left panel.

**Attention**: Skip this step if you want to use the GitHub integration to publish a new repository (Step 9).

![06_init_git_repository](images/07_init_git_repository.png)

### 8 - (Optional) Add remote

Connect your GitHub repository to your local git repository with:
```bash
git remote add origin https://github.com/YOUR_GITHUB_ACCOUNT_NAME/YOUR_GITHUB_REPOSITORY_NAME.git
```
Skip this step if you plan to use the VsCode UI for this.

### 9 - (GUI Alternative) Publish to GitHub

If you skipped steps 2, 7 and 8 you can now click the "Publish to GitHub" button, to create a private repository on GitHub, add the GitHub repository as a remote to your local repository and publish your local repository for the first time - all in one click. You will be asked to authorize VsCode to be connected to GitHub, so you do not need to enter your GitHub credentials every time you push a commit:

![08_publish_to_github](images/08_publish_to_github.png)

![08_publish_to_github_2](images/08_publish_to_github_2.png)

## Repetive steps

Everytime you want to "upload" changes to your GitHub git repository, you need to follow these steps.

### git add

Before you can bundle changes into a git commit you need to add files to your staging area, from which the commit is created.

With this command you add a file to the git staging area
```
git add NAME_OF_YOUR_FILE
```

or add all files you've changed to your staging area
```
git add *
```

### git commit

Now you can finalize a git commit (think of a bundled package of changes). Enter the following command to create a git commit with your staged files and a commit message:
```
git commit
```

### git push

Now your local repository has new changes bundled as (a) commit(s). To update your remote repository on GitHub you need to use the push command.
You can either just use
```
git push
```
to "upload" the current branch you are in (if you did not change, it should be named "master") to the origin remote, or decide which branch to push to which remote:

```
git push REMOTE_NAME BRANCH_NAME
```

### (GUI Alternative) With the VsCode source control UI

Alternatively, you can use VsCode (or any other git client) to stage, commit, switch branch, pull, push, fetch or to use any other git command.


![](images/09_stage_and_commit.png)

![10_push_to_remote](images/10_push_to_remote.png)

# Internship 01

## Learning Linux bash basics

Information about how to use GNU utils can be gathered with calling the terminal program ```man```. 

For example:

```bash
man cd
```

```man``` should be your primary source of information about a terminal program in the following internships. It comes preinstalled with most Linux distributions and does not need any internet connection.

### mkdir

With ```mkdir``` you can create/make directories in Linux/Unix.

Create the directory ```test```:

```bash
mkdir test
```

### cd

With ```cd``` you can **c**hange the **d**irectory. Change to your newly created directory:

```bash
cd test
```

### pwd

With ```pwd``` you can **p**rint the current **w**orking **d**irectory to your terminal:

```bash
pwd
```

### cp

With ```cp``` you can **c**o**p**y files and directories (```-r```).
Copy the file ```passwd``` (which was used by the program ```passwd```) into your current working directory:

```bash
cp /etc/passwd .
cp passwd passwdcopy01
cp passwd passwdcopy02
```
### ls

With ```ls``` you can print a list of files and (sub)directories in a given directory.

Use:

```bash
ls
ls -lt
ls -l passwdcopy01
ls -l p*
```

### more & tail

With ```more``` and ```tail``` you can print the content of files, view the manual for further information and differences:

```bash
man more
man tail
more passwdcopy02
more *
tail passwdcopy01
```

### mv

With ```mv``` you can **m**o**v**e or rename files and directories.
Rename your passwdcopy01 to passwdcopy01_renamed with:

```bash
mv passwdcopy01 passwdcopy01_renamed
```

### rm

**r**e**m**ove your renamed copy01 of passwd with:

```bash
rm passwdcopy01_renamed
```

### cat

Create a file and write into it from within the terminal, when you are done quit with **CTRL + D**:

```bash
cat > my_new_file
my name is Hans # quit with CTRL + C
```

## Create a C program that returns its arguments

Use either terminal editors like ```vi``` or ```nano``` or a more comfortable solution like vscode & C/C++ extension to create a C program that returns the arguments that you've entered.

## compile

Compile your created C program with the following shell command, where ```MyArg``` is the name of the *output file* (thus the argument ```-o```) which you can chose and ```MyArg.c``` is the C file you've previously created and the source of the compilation:

```bash
gcc -o MyArg MyArg.c
```

## run

To run your program in the terminal run it with a trailing ```./``` before its file name:

```bash
./MyArg
```

Add any strings you can chose to have arguments as your output:

```bash
./MyArg 2020 is the year of the linux desktop
```