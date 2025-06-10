# git
## command
### look at version of git
#### `git -v`

+ To look at version of git

```
git -v
```

### open the document of specific command

+ To open the document of specific command

```
git help <command-name>
```

where 

`<command-name>` is the git command you want to know its info,

such as `clone`

### initialize the local repo

When you want to do git control on the specific directory in local device.

Please change directory to desired directory in Git Terminal.

Then initialize the local repo with following command 

```
git init
```

### clone from remote repo
#### `clone`

+ To clone from remote repo to local repo

```
git clone <remote-repo-url>
```

where

`<remote-repo-url>` is the url of remote repo

such as `https://github.com/40843245/git-tutorial.git`

###
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
