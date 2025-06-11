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

will open the document about `checkout` `C:/../../Git/mingw64/share/doc/git-doc/git-checkout.html` to look at info of `checkout` command.

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

### copy a remote branch to a local branch

+ To copy a remote branch `remote-main` from  to a local branch `local-main-backup`,

```
git checkout -b new-local-branch origin/remote-branch
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
