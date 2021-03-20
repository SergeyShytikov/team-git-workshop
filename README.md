# Git workshop for team

## Structure and commands

## Stage 0 (self-prepare steps before workshop)

1.

### Install brew - The Missing Package Manager for macOS

Homebrew installs the stuff you need that Apple (or your Linux system) didn’t.

```bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

---

2.

### Install iTerm2

iTerm2 is a terminal emulator for macOS that does amazing things

```bash
brew install --cask iterm2
```

basic commands

```bash
ls
cd
cd ~/
cd /
cd ..
touch
mkdir
echo
echo "Some text" > smth
echo "Some text" >> smth
cp
mv
rm
rm -rf
rmdir
pwd
cat
less
chmod
sudo
```

---

3.

### Install Git on Mac

```bash
brew install git

#check version
git --version
```

---

4.

### VScode install

```bash
brew install --cask visual-studio-code
```

---

5.

### Basic setup git

open terminal and paste this commands

```bash
git config --global user.name "John Doe"
git config --global user.email johndoe@example.com
git config --global core.editor code --wait
```

---

6.

### [github.com](http://github.com) sign up

use the same email as basic setup git "johndoe@example.com"

---

## Stage 1 (steps we will do on workshop)

### Create working directory

- open terminal and make directory for our workshop

  ```bash
  ~
  mkdir -p projects/git_workshop
  cd projects/git_workshop
  ```

---

### Markdown

we will working with markdown file, it's just text with a few special symbols

#### Headers

```markdown
# This is an <h1> tag

## This is an <h2> tag

###### This is an <h6> tag
```

#### Emphasis

```markdown
_This text will be italic_
_This will also be italic_

**This text will be bold**
**This will also be bold**

_You **can** combine them_
```

#### **Lists**

##### **Unordered**

```markdown
- Item 1
- Item 2
  - Item 2a
  - Item 2b
```

##### **Ordered**

```markdown
1. Item 1
1. Item 2
1. Item 3
   1. Item 3a
   1. Item 3b
```

#### Images

```markdown
![GitHub Logo](/images/logo.png)
Format: ![Alt Text](url)
```

#### [https://guides.github.com/features/mastering-markdown/](https://guides.github.com/features/mastering-markdown/)

---

### Prepare team repository

what a content will be at repo?

- teammates with personal info about hobbies, musical preferences, pets, most interesting trips
- team of avatars - what superhero does everyone associate with
- some useful info about team, unspoken rules, important presentation about behave in team
- suggestions of music, movies, books, learning corses
- career or learning plans

---

### Git basic commands

most our work we will do with existing repo which we clone from GitHub, but git ≠ GitHub. to see it we initialise a new repo at local machine

- #### local repo

  - init

    into working directory

    ```bash
    mkdir test && cd test
    touch test.md && code .
    ```

    in terminal execute follow command

    ```bash
    git init
    ```

  - making changes at file readme.md, save it

    ```bash
    code .
    git status
    ```

  - add

    ```bash
    git add README.md
    ```

  - commit

    ```bash
    git commit -m "I'm super puper gitter add a few headers"
    git status
    ```

  - branch

    ```bash
    git branch BRANCH_NAME.
    ```

  - checkout

    ```bash
    git checkout BRANCH_NAME.

    # we can create new branch and swich to it by one command
    git checkout -b BRANCH_NAME.
    ```

  - merge

    ```bash
    git checkout BRANCH_NAME && git merge master
    ```

- #### How to make a pull-request to remote repo?

  - fork repo

    ```bash
    https://github.com/SergeyShytikov/team-git-workshop.git
    ```

  - clone

    return to projects dir and clone your fork to your local machine from GitHub

    ```bash
    git clone https://github.com/SergeyShytikov/team-git-workshop.git
    ```

    change directory on repo

    ```bash
    cd team-git-workshop
    ```

  - add repo to upstream

    Add this repository <link parent repo> as an upstream

    ```bash
    git remote add upstream https://github.com/SergeyShytikov/team-git-workshop.git
    ```

  - checkout

    ```bash
    git checkout master 

    #and then create new branch, naming is up to you (aka feature branch) 
    git checkout -b BRANCH_NAME.
    ```

  - making changes at file README and save it

    Make some changes to your local repository. It could be anything, really. If you have found a typo in README - great! Take care to give your PR a meaningful name and description.

    ```bash
    code .
    git status
    ```

  - add

    ```bash
    git add README.md
    ```

  - commit

    Сommit your changes to newly created feature branch

    ```bash
    git commit -m "I'm super puper gitter add a few headers"
    git status
    ```

  - checkout

    Сheckout master branch:

    ```bash
    git checkout master
    ```

  - pull

    Pull latest changes from upstream master branch:

    ```bash
    git pull upstream master
    ```

  - merge

    Merge master branch into your feature branch:

    ```bash
    git checkout BRANCH_NAME && git merge master
    ```

    Resolve any merge conflicts if there are any

  - push

    Push feature branch to your remote repository:

    ```bash
    git push --set-upstream origin BRANCH_NAME
    ```

  - pull request

    Make pull-request from your repository to [this](https://github.com/Kottans/mock-repo) repository via GitHub web-interface

- #### making GitHub Pages from repo
