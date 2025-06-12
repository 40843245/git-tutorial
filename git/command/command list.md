# git
## command
### look at version of git
#### `git -v`

+ To look at version of git

```
git -v
```

### look at specific command

+ To open the document to look at specific command

```
git help <command-name>
```

where 

`<command-name>` is the git command you want to know its info,

such as `clone`

+ To print the info of specific command on git command line

```
git help <flag>
``` 

where 

`<flag>` are one or more flag which is available .

##### examples
###### example 1

```
git help checkout
```

will open the document about `checkout` located at `C:/../../Git/mingw64/share/doc/git-doc/git-checkout.html` to look at info of `checkout` command.

<img width="880" alt="image" src="https://github.com/user-attachments/assets/2e87f335-3596-4d49-a92c-0d14bfe67edf" />

###### example 2

```
git help -a
```

will print info of all commands on git command line

<img width="455" alt="image" src="https://github.com/user-attachments/assets/15ad2621-a2e6-4041-8017-2df4ac497082" />

### initialize the local repo

When you want to do git control on the specific directory in local device.

Please change directory to desired directory in Git Terminal.

Then initialize the local repo with following command 

```
git init
```

### clone from remote repo to local repo
#### `clone`

+ To clone from remote repo to local repo

```
git clone <remote-repo-url>
```

where

`<remote-repo-url>` is the url of remote repo

such as `https://github.com/40843245/git-tutorial.git`

### switch branch
#### `checkout`
+ To switch current branch `main` to `main-backup` branch,

I can type

```
git checkout main-backup
```

### copy a local branch to new local branch
#### `branch`

+ To copy a local branch `main` to new local branch `main-backup`,

we have to switch current branch to `main` branch (if current branch is NOT `main`)

```
git checkout main
```

and copy a new branch `main-backup`

```
git branch main-backup
```

+ it can even be shorten as

```
git branch main-backup main
```

##### reference
+ [Google Gemini's response -- How to copy branch with git command?](https://g.co/gemini/share/8e93564e75bd)

### copy current local branch to a local branch and switch to the new created branch
#### `checkout --track` or `checkout -b`

`-b` is shorten for `--track`.

`git checkout` command NOT ONLY can switch branches (without `--track` and `-b` flags) 

BUT ALSO can copy current local branch to a local branch and switch to the new created branch (with one of `--track` or `-b` flags)

+ To copy current local branch `main` to a local branch `new-local-branch` and switch to the new created branch (here is `new-local-branch`)

```
git checkout --track new-local-branch # creates and switches to a new 'new-local-branch' branch
```

or

```
git checkout -b new-local-branch # creates and switches to a new 'new-local-branch' branch
```

##### reference
+ [Google Gemini's response -- How to copy branch with git command?](https://g.co/gemini/share/8e93564e75bd)

### copy a remote branch to a local branch
#### `checkout --track` or `checkout -b`
+ To copy a remote branch `remote-main` in remote repo `origin` to a local branch `local-main-backup`,

```
git checkout -b new-local-branch origin/remote-branch
```

or 

```
git checkout --track new-local-branch origin/remote-branch
```

explanation:

    - `git checkout` is used to switch branch.  
    - `-b` is shorten for `--track` which used to create a new branch from remote branch in a remote repo.
    - thus, `-b new-local-branch` is used to create a new branch named `new-local-branch`.
    - `origin/remote-branch` indicates copy a remote branch `remote-branch` in a remote repo named `origin`.

##### reference
+ [Google Gemini's response -- What does it mean? `git checkout -b new-local-branch origin/remote-branch`](https://g.co/gemini/share/4cfdbc0c97bd)

### copy a new local branch from a specific commit
#### `branch`
+ To copy a new local branch `new-branch` from a specific commit,

we need to find the old-SHA of the commit, then type

```
git branch new-branch <commit-sha>
```

where 

`<commit-sha>` is the old-SHA of the commit.

### stage one or more specific files
#### `add`
You can use `git add` followed file name (with regex rule) to stage one or more specific files that matches the files with given regex.

The regex rule is same as that of command in Windows Terminal.

+ To stage `words.txt`

```
git add words.txt
```

+ To stage all changes in the current directory

```
git add .
```

+ To stage all changes (new, modified, and deleted tracked files)

```
git add -A
```

+ To stage all files that ends with `.txt`

```
git add "*.txt"
```

+ To stage all modified and deleted tracked files (but not new, untracked files)

```
git add -u
```

### unstage one or more specific files
#### `restore --staged`
`git restore --staged` is the cleanest way to unstage the files.

+ To unstage one file named `words.txt`

```
git restore --staged words.txt
```

+ To unstage all staged files

```
git restore --staged .
```

or

```
git restore --staged --worktree
```

##### reference
+ [Google Gemini's response -- How to unstage a file with git command?](https://g.co/gemini/share/ccc035f7447c)

#### `reset`
Although `git reset` can unstage files, it have boarder usage so that you sometimes are confused.

Therefore, I don't recommend to use it.

+ To unstage one file named `words.txt`

```
git reset HEAD words.txt
```

+ To unstage all staged files
  
```
git reset
```

or

```
git reset HEAD
```

##### reference
+ [Google Gemini's response -- How to unstage a file with git command?](https://g.co/gemini/share/ccc035f7447c)
  
### commit the staged files
#### `commit`

+ To commit the staged files with commit description `rename CH2 to CH3`

```
git commit -m "rename CH2 to CH3"
```

here `-m` flag means the commit description.

+ To commit the staged files

```
git commit
```

however, git command line will prompt the user to enter the commit description.

+ To stages all changes to tracked files (modified and deleted files) and commit with commit description `Implement user authentication with JWT`,

there is a shortcut command.

```
git commit --all -m "Implement user authentication with JWT"
```

or 

```
git commit -a -m "Implement user authentication with JWT"
```

or even shorter

```
git commit -am "Implement user authentication with JWT"
```

explanation:

`--all` or `-a` in `git commit` indicates that it will stages all changes to tracked files (modified and deleted files) before committing.

##### reference
+ [Google Gemin's response -- How to commit the file changes with git command?](https://g.co/gemini/share/5239566aa5af)

### show changes where your `HEAD` or branch pointers are pointing of local repo
#### `reflog`
+ To show changes where your `HEAD` or branch pointers are pointing of local repo

```
git reflog show HEAD
```

or can be shorter

```
git reflog show
```

or even shorter

```
git reflog
```

It will print the info of every actions that changes where your HEAD or branch pointers are pointing. Including these info

    - action's type: such as `commit`, `checkout`
    - description of the action
    - old-SHA of the action
    - enrty's id

the format of output will be

```
<old-SHA> <enrty's id> <type> <description>
```

for example, it may print

```
# <old-SHA> <enrty's id> <type> <description>
a1b2c3d HEAD@{0}: commit: Add new feature X
e4f5g6h HEAD@{1}: checkout: moving from main to feature/X
i7j8k9l HEAD@{2}: commit (initial): Initial commit
```

##### restrictions
It can **only** be used for local repo. 

It will not show changes where your `HEAD` or branch pointers are pointing for a shared repo and a remote repo etc

##### Remarks
1. These entries have an expiration time
   
   - by default, 90 days for reachable entries
   - by default, 30 days for unreachable ones

After an entry expires, it will be freed (or pruned) by garbage collection in Git (`git gc`)

##### reference
+ [Google Gemini's response -- How to show tracking of commit?](https://g.co/gemini/share/6db04d2667d4)
+ [Google Gemini's response -- git reflog show](https://g.co/gemini/share/c8a6596507f0)

### configuration
#### `config`

+ To view git configuration

```
git config --list
```

+ To check user name 

```
git config user.name
```

+ To set user name as `Jay`

```
git config user.name Jay
```

+ To check email

```
git config user.email
```

+ To set email as `40843245@gm.nfu.edu.tw`

```
git config user.email 40843245@gm.nfu.edu.tw
```

##### reference
###### official docs
+ [1.6 Getting Started - First-Time Git Setup (Git)](https://git-scm.com/book/en/v2/Getting-Started-First-Time-Git-Setup)

###### forum
+ [How to know the git username and email saved during configuration? (stackoverflow)](https://stackoverflow.com/questions/46941346/how-to-know-the-git-username-and-email-saved-during-configuration)
