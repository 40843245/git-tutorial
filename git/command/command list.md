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
git help <command> <option>
``` 

where 

`<command>` are one or more command which is available with option `<option>`.

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

### look at status of the repo
#### `status`
+ To look at status of the repo,

```
git status
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

### Look at file changes
+ To look at files changes,

```
git diff
```

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

### Remove tracked files
+　To remove all tracked files,

```
git rm --cached -r
```

+　To remove all tracked specific files using regex,

```
git rm --cached -r <files-using-regex>
```

It will remove tracked files that are matched by regex `<files-using-regex>`.

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

+ To specify git look at current commit,

```
git reset --hard HEAD
```
##### reference
+ [Google Gemini's response -- How to unstage a file with git command?](https://g.co/gemini/share/ccc035f7447c)
  
### commit the staged files
#### `commit`

+ To commit the staged files with commit description `rename CH2 to CH3`

```
git commit -m "rename CH2 to CH3"
```

here `-m` option means the commit description.

+ To commit the staged files

```
git commit
```

however, git command line will open `~/.git/COMMIT_EDITMSG` file (which is a **hidden** file so that by default it can NOT seen in `File Explorer`)

and prompts user to fill the commit description in the **first line**.

<img width="911" alt="image" src="https://github.com/user-attachments/assets/22510c2f-ec95-4ab4-8ebb-8ab370d74c6a" />

after filling, closing the file to try to commit.

Then, if the commit is success, then you will see the entry info followed by commit description and a successful message.

<img width="262" alt="image" src="https://github.com/user-attachments/assets/36a22144-f09e-4c50-9b91-f3769643c02f" />

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

##### Remarks
1. By default, in `~/.git/COMMIT_EDITMSG` file, it will look like this
 
```

# Please enter the commit message for your changes. Lines starting
# with '#' will be ignored, and an empty message aborts the commit.
#
# On branch master
#
# Initial commit
#
# Changes to be committed:
#	new file:   git-command-demo
#
# Changes not staged for commit:
#	modified:   git-command-demo (untracked content)
#
```

2. If user enters nothing (i.e. enters an empty string or string consist of whitespace or comments or both), then the commit will be aborted.
3. a line will be considered as a comment if the line starts with `#`.

### commit all files and folder under the directory
> [!IMPORTANT]
> Core concept:
>
> + Each folder is considered as a module
> 
> + The folder located the root directory of local repo is considered as the **root module**.
>
> + The folder that is a child of the folder located at the root directory of local repo is considered as
> 
> a child of the root module (and of course, it is a **submodule** relative to root module).
>
> Furthermore, its **superproject** is the root module.
>
> Similarly, we can say that the root module has a **subproject**.

Since Git takes granularity of control (that is, it split a folder under directory as a submodule and a git just git control a submodule, 

NOT all files and folder under the root directory of the repo),

If a file changes or a directory changes, **only** its parent module can track it 

(that is, recognize the file or the directory has been changed).

Other modules can NOT track it.

So we have to stage the files and commit staged files from bottom to top 

(that is, start from submodule which has direct child that contains a changed file, to root module).

To do that, we need follow these instructions.
    
    Step 1. change directory to the submodule which has direct child that contains a changed file or submodule.

    Step 2. stage file changes.

    Step 3. commit the staged file. (Now, its parent module can recognize there is a change in the submodule.

    Step 4. repeat the Step 1. to Step 3. until the root module.

There is a convenience command (generated by Google Gemini's) to do that.

NOT directly use git command.

write shell command as alias where the shell command contains lots of git commands that 

can recursively iterate for all file and directory changes.

> [!NOTE]
> The shell commend can **ONLY** recursively iterate for all file and directory changes, staging them then commit them.
>
> It can **ONLY** be used for all file and directory changes,
>
> can NOT iterate specific file or directory changes
>
> can NOT iterate with filters.

```
git config --global alias.commit-all '!f() { \
  git submodule foreach --recursive "git add . && git commit -m \"Submodule update: $(git rev-parse --short HEAD)\""; \
  git add . && git commit -m "$@"; \
}; f'
```

then we can use the alias

```
git commit-all "My big update including submodule changes"
```

explanation:

+ [Google Gemini's response -- How to commit all changes (including files changes in submodule) with single git command?](https://g.co/gemini/share/273247a3caed)

##### reference
+ About commit files
  - [Google Gemin's response -- How to commit the file changes with git command?](https://g.co/gemini/share/5239566aa5af)

+ About commit all files and directory
  - [Google Gemini's response -- How to commit all changes (including files changes in submodule) with single git command?](https://g.co/gemini/share/273247a3caed)

### remove all staged files
+ To remove all staged files.

```
git rm --cached -r
```
### push to remote repo
#### push to remote repo
```
git push origin <remote-branch-to-push> <commits>
```

```
<commits> := <commit>+
```

`<commit>` can be commit-sha or tag to push

#### push to remote repo with rollup
To push to remote repo with rollup (i.e. consider many commits as one transcation, all commits are pushed if all commits are pushed successfully, or none commits are pushed otherwise,

```
git push --atomic origin <remote-branch-to-push> <commitsS>
```

### tag
#### list all tags
+ To list all tags,

```
git tag
```

#### add specific tag to this unpushed commit
+ To add specific tag to this unpushed commit,

```
git tag <tag-name>
```

### look at specific to test
+ When you fail the test at present but you remember specific commit can pass the test, you can try to search good commit by biary search algorithm.

```
git bisect start # start to try to search good commit by biary search algorithm.
git bisect bad # mark current commit as bad commit (commit which fails the test)
git bisect good <good-commit-sha> # mark commit with <good-commit-sha> as good commit (commit which passes the test)
```

### rebase the branch
+ To rebase the branch,

```
git rebase <branch-to-rebase>
```

+ To rebase the branch interactively,

```
git rebase -i <branch-to-rebase>
```

+ To continue the rebase,

```
git rebase --continue
```

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
<old-SHA> (<source-branch> -> <destination-branch>) <enrty's id> <type> <description>
```

in Git Bash with current version of git (`git version 2.49.0.windows.1`).

For example, it may print

```
# <old-SHA> (<source-branch> -> <destination-branch>) <enrty's id> <type> <description>
4bc70b5 (HEAD -> master) HEAD@{0}: commit (initial): First practice
```

<img width="441" alt="image" src="https://github.com/user-attachments/assets/c0c1ec47-f020-435f-ad96-fb76b3cea80d" />

##### restrictions
It can **only** be used for local repo. 

It will not show changes where your `HEAD` or branch pointers are pointing for a shared repo and a remote repo etc

##### Remarks
1. These entries have an expiration time
   
   - by default, 90 days for reachable entries
   - by default, 30 days for unreachable ones

After an entry expires, it will be freed (or pruned) by garbage collection in Git (`git gc`)

2. `git log` can look at (commit) history of local repo, but it prints with different format than `git reflog` (see `log` section)

and there are slightly difference between their behavior.

3. see above restrictions.
   
##### reference
+ [Google Gemini's response -- How to show tracking of commit?](https://g.co/gemini/share/6db04d2667d4)
+ [Google Gemini's response -- git reflog show](https://g.co/gemini/share/c8a6596507f0)

### show the commit history of a repository
#### `log`
+ To show all commits history of a repository

```
git log
```

The format will be following

```
<type> <checksum of old-SHA> (<source-branch> -> <destination-branch>)
Author: <username in Git settings> <<email address in Git settings>>
Date:    <timestamp of commit> <its timezone offset>

  <description>
```

where 

`<timestamp of commit>` indicates the timestamp of commit was made (NOT the commit was sent).

`<checksum of old-SHA>` indicates shortened `checksum of old-SHA`. You can think it as the hash of commit id.
    
NOTE:

there is a `<>` to quote `<email address in Git settings>`


For example, it may print

```
# <type> <checksum of old-SHA> (<source-branch> -> <destination-branch>)
# Author: <username in Git settings> <<email address in Git settings>>
# Date:    <timestamp of commit> <its timezone offset>
#
#    <description>
commit 4bc70b566526cde604751c829a86be67c9cb25db (HEAD -> master)
Author: jayhuang820 <<email address in Git settings>>
Date:   Thu Jun 12 16:45:58 2025 +0800

    First practice
```
<img width="434" alt="image" src="https://github.com/user-attachments/assets/eb2b9cdb-4107-4d34-b310-f07ae5ffd800" />

+ To show all commits history of a repository (each record is shorten to one line)

```
git log --oneline
```

The format will be following

```
<old-SHA> (<source-branch> -> <destination-branch>) <description>
```

For example, it may print

```
# <old-SHA> (<source-branch> -> <destination-branch>) <description>
4bc70b5 (HEAD -> master) First practice
```

<img width="425" alt="image" src="https://github.com/user-attachments/assets/249953a2-2c6a-43fc-963c-46a1607f82f3" />

+ To show the full changes introduced by each commit

```
git log --patch
```

or can be shorter

```
git log -p
```

It will output the result of `git log` 

then append new line and full changes introduced by each commit.

For example, it may print

<img width="445" alt="image" src="https://github.com/user-attachments/assets/edbb494c-c2f8-41b1-9ae1-8baeeeb62897" />

+ To show commit history graphically

```
git log --graph
```

It will output the result of `git log`,

it will use asterisk to make a bullet list (each record is an item in the bullet list)

For example, it may print

<img width="437" alt="image" src="https://github.com/user-attachments/assets/86e9b64d-503e-4b77-9f1e-4df7797b7b3f" />

+ To show commit history (branch and tag names) next to their respective commits

```
git log --decorate
```

For example, it may print

<img width="424" alt="image" src="https://github.com/user-attachments/assets/08dac7ad-0655-40ae-877c-d7de35276026" />

+ To shows the commit history for all branches

```
git log --all
```

For example, it may print

<img width="442" alt="image" src="https://github.com/user-attachments/assets/c6928d4e-8230-45ad-8c06-a3de2cea6860" />

+ To shows the commit history for all branches graphically, you can combine these above options together

```
git log --graph --oneline --all
```

For example, it may print

```
$ git log --graph --oneline --all
* 4b2e759 (HEAD -> master) 修改新問的問題
| * 93a5a68 (refs/stash) WIP on master: adf499f Add: 增加詢問使用者名稱的功能
|/|
| * 36111ba index on master: adf499f Add: 增加詢問使用者名稱的功能
|/
* adf499f (feature/ask-name, conflict-test) Add: 增加詢問使用者名稱的功能
* 777b53f Initial: 建立 C# 控制台專案基礎架構
```

##### reference
+ [Google Gemini's response -- `git log`](https://g.co/gemini/share/ee46ccc9b2ad)
+ [Google Gemini's response -- What does the output of `git log` stands for?](https://g.co/gemini/share/1a063de40631)

### list staged files
+ To list all staged files

```
git ls-files --stage
```

+ To list all staged files under local directory,

```
git ls-files --stage <directory>
```
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
