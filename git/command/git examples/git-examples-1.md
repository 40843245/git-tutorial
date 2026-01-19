# example 1
Available at [GitLab remote repo](https://gitlab.com/codelover30/git-example-2)

+ To add a local repo at `D:\workspace\tutorial projects\Git\Git-example-2`

```
userJay30@ASUS-B1400CBNGW MINGW64 ~ (master)
$ cd "D:\workspace\tutorial projects\Git\Git-example-2"

userJay30@ASUS-B1400CBNGW MINGW64 /d/workspace/tutorial projects/Git/Git-example-2
$ git init
Initialized empty Git repository in D:/workspace/tutorial projects/Git/Git-example-2/.git/
```

+ To create a C# project named `MyAwesomeApp` using console template,
  
```
userJay30@ASUS-B1400CBNGW MINGW64 /d/workspace/tutorial projects/Git/Git-example-2 (master)
$ mkdir "MyAwesomeApp"

userJay30@ASUS-B1400CBNGW MINGW64 /d/workspace/tutorial projects/Git/Git-example-2 (master)
$ cd "MyAwesomeApp"

userJay30@ASUS-B1400CBNGW MINGW64 /d/workspace/tutorial projects/Git/Git-example-2/MyAwesomeApp (master)
$ dotnet new console
The template "Console App" was created successfully.

Processing post-creation actions...
Restoring D:\workspace\tutorial projects\Git\Git-example-2\MyAwesomeApp\MyAwesomeApp.csproj:
Restore succeeded.
```

+ Ensure the C# project is successfull built.
  
```
userJay30@ASUS-B1400CBNGW MINGW64 /d/workspace/tutorial projects/Git/Git-example-2/MyAwesomeApp (master)
$ ls
MyAwesomeApp.csproj  Program.cs  obj/
```

+ To open `MyAwesomeApp/Program.cs` with notepad.

```
userJay30@ASUS-B1400CBNGW MINGW64 /d/workspace/tutorial projects/Git/Git-example-2/MyAwesomeApp (master)
$ notepad "Program.cs"
```

Then remove the comments, leaving content

```
Console.WriteLine("Hello World!!!");
```

Save it and close the notepad.

+ To look at status of the local repo.

```
userJay30@ASUS-B1400CBNGW MINGW64 /d/workspace/tutorial projects/Git/Git-example-2/MyAwesomeApp (master)
$ git status
On branch master

No commits yet

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        ./

nothing added to commit but untracked files present (use "git add" to track)
```

+ change back to root directory of local repo.

```
userJay30@ASUS-B1400CBNGW MINGW64 /d/workspace/tutorial projects/Git/Git-example-2/MyAwesomeApp (master)
$ cd ..
```

+ Then look the status again,

```
userJay30@ASUS-B1400CBNGW MINGW64 /d/workspace/tutorial projects/Git/Git-example-2 (master)
$ git status
On branch master

No commits yet

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        MyAwesomeApp/

nothing added to commit but untracked files present (use "git add" to track)
```

You will find the fact that 

, in any directory of local repo, `git status` will echo same output. Its echo will NOT be affected by the current working directory.

+ Track all file changes and then stage them

```
userJay30@ASUS-B1400CBNGW MINGW64 /d/workspace/tutorial projects/Git/Git-example-2 (master)
$ git add .
```

+ After tracking files, look at status again.
  
```
userJay30@ASUS-B1400CBNGW MINGW64 /d/workspace/tutorial projects/Git/Git-example-2 (master)
$ git status
On branch master

No commits yet

Changes to be committed:
  (use "git rm --cached <file>..." to unstage)
        new file:   MyAwesomeApp/MyAwesomeApp.csproj
        new file:   MyAwesomeApp/Program.cs
        new file:   MyAwesomeApp/obj/MyAwesomeApp.csproj.nuget.dgspec.json
        new file:   MyAwesomeApp/obj/MyAwesomeApp.csproj.nuget.g.props
        new file:   MyAwesomeApp/obj/MyAwesomeApp.csproj.nuget.g.targets
        new file:   MyAwesomeApp/obj/project.assets.json
        new file:   MyAwesomeApp/obj/project.nuget.cache
```

+ commit staged files with commit message `Part 0:Create empty console project in the solution`

```
userJay30@ASUS-B1400CBNGW MINGW64 /d/workspace/tutorial projects/Git/Git-example-2 (master)
$ git commit -m "Part 0:Create empty console project in the solution"
[master (root-commit) 53a09ef] Part 0:Create empty console project in the solution
 7 files changed, 739 insertions(+)
 create mode 100644 MyAwesomeApp/MyAwesomeApp.csproj
 create mode 100644 MyAwesomeApp/Program.cs
 create mode 100644 MyAwesomeApp/obj/MyAwesomeApp.csproj.nuget.dgspec.json
 create mode 100644 MyAwesomeApp/obj/MyAwesomeApp.csproj.nuget.g.props
 create mode 100644 MyAwesomeApp/obj/MyAwesomeApp.csproj.nuget.g.targets
 create mode 100644 MyAwesomeApp/obj/project.assets.json
 create mode 100644 MyAwesomeApp/obj/project.nuget.cache
```

+ After committing, look at status again,

```
userJay30@ASUS-B1400CBNGW MINGW64 /d/workspace/tutorial projects/Git/Git-example-2 (master)
$ git status
On branch master
nothing to commit, working tree clean
```

+ After committing, look at log in one line,

```
userJay30@ASUS-B1400CBNGW MINGW64 /d/workspace/tutorial projects/Git/Git-example-2 (master)
$ git log --oneline
53a09ef (HEAD -> master) Part 0:Create empty console project in the solution
```

+ To build a remote repo named `git-example-2` in username `codelover30` in GitLab,
  
```
userJay30@ASUS-B1400CBNGW MINGW64 /d/workspace/tutorial projects/Git/Git-example-2 (master)
$ git remote add origin https://gitlab.com/codelover30/git-example-2.git #建立使用者名為codelover30的遠端repo名為git-example-2
```

+ To look at the verbose of the remote repo,

```
userJay30@ASUS-B1400CBNGW MINGW64 /d/workspace/tutorial projects/Git/Git-example-2 (master)
$ git remote -v
origin  https://gitlab.com/codelover30/git-example-2.git (fetch)
origin  https://gitlab.com/codelover30/git-example-2.git (push)
```

+ To look at all created tags of local repo.
  
```
userJay30@ASUS-B1400CBNGW MINGW64 /d/workspace/tutorial projects/Git/Git-example-2 (master)
$ git tag
```

+ To add a new tag named `v0.0.0` in local repo,

```
userJay30@ASUS-B1400CBNGW MINGW64 /d/workspace/tutorial projects/Git/Git-example-2 (master)
$ git tag v0.0.0
```

+ After adding new tag, look at all created tags of local repo.

```
userJay30@ASUS-B1400CBNGW MINGW64 /d/workspace/tutorial projects/Git/Git-example-2 (master)
$ git tag
v0.0.0
```

+ To push commits and tags to the remote repo atomically, 

```
userJay30@ASUS-B1400CBNGW MINGW64 /d/workspace/tutorial projects/Git/Git-example-2 (master)
$ git push --atomic origin master v0.0.0
Enumerating objects: 11, done.
Counting objects: 100% (11/11), done.
Delta compression using up to 12 threads
Compressing objects: 100% (9/9), done.
Writing objects: 100% (11/11), 5.74 KiB | 266.00 KiB/s, done.
Total 11 (delta 1), reused 0 (delta 0), pack-reused 0 (from 0)
remote:
remote:
remote: The private project codelover30/git-example-2 was successfully created.
remote:
remote: To configure the remote, run:
remote:   git remote add origin https://gitlab.com/codelover30/git-example-2.git
remote:
remote: To view the project, visit:
remote:   https://gitlab.com/codelover30/git-example-2
remote:
remote:
remote:
To https://gitlab.com/codelover30/git-example-2.git
 * [new branch]      master -> master
 * [new tag]         v0.0.0 -> v0.0.0
```

+ After pushing, look at log again.

```
userJay30@ASUS-B1400CBNGW MINGW64 /d/workspace/tutorial projects/Git/Git-example-2 (master)
$ git log --oneline
53a09ef (HEAD -> master, tag: v0.0.0, origin/master) Part 0:Create empty console project in the solution
```

Compare the echoed message at the first time we look at log and the second time.

message echoed at the first time we look at log
 
```
userJay30@ASUS-B1400CBNGW MINGW64 /d/workspace/tutorial projects/Git/Git-example-2 (master)
$ git log --oneline
53a09ef (HEAD -> master) Part 0:Create empty console project in the solution
```

message echoed at the second time we look at log

```
userJay30@ASUS-B1400CBNGW MINGW64 /d/workspace/tutorial projects/Git/Git-example-2 (master)
$ git log --oneline
53a09ef (HEAD -> master, tag: v0.0.0, origin/master) Part 0:Create empty console project in the solution
```

We can know that 

`(HEAD -> master)` indicates that the commit is commited but NOT be pushed yet.

`(HEAD -> master, tag: v0.0.0, origin/master)` indicates that the commit is commited and pushed with tag `v0.0.0`.

+ To create a new branch named `feature/ask-me` then switch branch

```
userJay30@ASUS-B1400CBNGW MINGW64 /d/workspace/tutorial projects/Git/Git-example-2 (master)
$ git checkout -b feature/ask-me
Switched to a new branch 'feature/ask-me'
```

+ create `MyAwesomeApp/Program.cs` (if not exists0), then open `MyAwesomeApp/Program.cs` with notepad
  
```
userJay30@ASUS-B1400CBNGW MINGW64 /d/workspace/tutorial projects/Git/Git-example-2 (feature/ask-me)
$ touch "MyAwesomeApp/Program.cs"

userJay30@ASUS-B1400CBNGW MINGW64 /d/workspace/tutorial projects/Git/Git-example-2 (feature/ask-me)
$ notepad "MyAwesomeApp/Program.cs"
```

Then modify the content to

```
Console.WriteLine("What is your name?");
var name = Console.ReadLine();
Console.WriteLine($"Hello, {name}!");
```

+ To look at status again,

```
userJay30@ASUS-B1400CBNGW MINGW64 /d/workspace/tutorial projects/Git/Git-example-2 (feature/ask-me)
$ git status
On branch feature/ask-me
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   MyAwesomeApp/Program.cs

no changes added to commit (use "git add" and/or "git commit -a")
```

+ To track changed but not committed files and stage them,

```
userJay30@ASUS-B1400CBNGW MINGW64 /d/workspace/tutorial projects/Git/Git-example-2 (feature/ask-me)
$ git add .
```

+ After staging them, look at status again,
  
```
userJay30@ASUS-B1400CBNGW MINGW64 /d/workspace/tutorial projects/Git/Git-example-2 (feature/ask-me)
$ git status
On branch feature/ask-me
Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        modified:   MyAwesomeApp/Program.cs
```

+ To commit staged file with commit message `Part 1: prompt user to enter the input`

 ```
userJay30@ASUS-B1400CBNGW MINGW64 /d/workspace/tutorial projects/Git/Git-example-2 (feature/ask-me)
$ git commit -m " "
[feature/ask-me 7518cf4] Part 1: prompt user to enter the input
 1 file changed, 3 insertions(+), 1 deletion(-)
```

+ After committing, look at status again.

```
userJay30@ASUS-B1400CBNGW MINGW64 /d/workspace/tutorial projects/Git/Git-example-2 (feature/ask-me)
$ git status
On branch feature/ask-me
nothing to commit, working tree clean
```

+ After committing, look at log again (third time).

```
userJay30@ASUS-B1400CBNGW MINGW64 /d/workspace/tutorial projects/Git/Git-example-2 (feature/ask-me)
$ git log --oneline
7518cf4 (HEAD -> feature/ask-me) Part 1: prompt user to enter the input
53a09ef (tag: v0.0.0, origin/master, master) Part 0:Create empty console project in the solution
```

+ To add tag named `v1.0.0`.

```
userJay30@ASUS-B1400CBNGW MINGW64 /d/workspace/tutorial projects/Git/Git-example-2 (feature/ask-me)
$ git tag v1.0.0
```

+ After adding tag named v1.0.0, look at created new tag.

```
userJay30@ASUS-B1400CBNGW MINGW64 /d/workspace/tutorial projects/Git/Git-example-2 (feature/ask-me)
$ git tag
v0.0.0
v1.0.0
```

+ To push commit and tag `v1.0.0` to `feature/ask-me` branch of remote repo atomatically,  

```
userJay30@ASUS-B1400CBNGW MINGW64 /d/workspace/tutorial projects/Git/Git-example-2 (feature/ask-me)
$ git push --atomic origin feature/ask-me v1.0.0
Enumerating objects: 7, done.
Counting objects: 100% (7/7), done.
Delta compression using up to 12 threads
Compressing objects: 100% (3/3), done.
Writing objects: 100% (4/4), 471 bytes | 47.00 KiB/s, done.
Total 4 (delta 0), reused 0 (delta 0), pack-reused 0 (from 0)
remote:
remote: To create a merge request for feature/ask-me, visit:
remote:   https://gitlab.com/codelover30/git-example-2/-/merge_requests/new?merge_request%5Bsource_branch%5D=feature%2Fask-me
remote:
To https://gitlab.com/codelover30/git-example-2.git
 * [new branch]      feature/ask-me -> feature/ask-me
 * [new tag]         v1.0.0 -> v1.0.0
```

+ After pushing, look at status again,
  
```
userJay30@ASUS-B1400CBNGW MINGW64 /d/workspace/tutorial projects/Git/Git-example-2 (feature/ask-me)
$ git status
On branch feature/ask-me
nothing to commit, working tree clean
```

+ After pushing, look at log in one line (fourth time),

```
userJay30@ASUS-B1400CBNGW MINGW64 /d/workspace/tutorial projects/Git/Git-example-2 (feature/ask-me)
$ git log --oneline
7518cf4 (HEAD -> feature/ask-me, tag: v1.0.0, origin/feature/ask-me) Part 1: prompt user to enter the input
53a09ef (tag: v0.0.0, origin/master, master) Part 0:Create empty console project in the solution
```

+ To pull from `feature/ask-me` of remote repo in GitLab,

```
userJay30@ASUS-B1400CBNGW MINGW64 /d/workspace/tutorial projects/Git/Git-example-2 (feature/ask-me)
$ git pull https://gitlab.com/codelover30/git-example-2 feature/ask-me
warning: redirecting to https://gitlab.com/codelover30/git-example-2.git/
From https://gitlab.com/codelover30/git-example-2
 * branch            feature/ask-me -> FETCH_HEAD
Already up to date.
```

+ To set the branch origin/feature/ask-me upstream branch is `feature/ask-me` branch in remote repo, 

(that is, the default branch for pushing is `feature/ask-me` branch in remote repo)

```
userJay30@ASUS-B1400CBNGW MINGW64 /d/workspace/tutorial projects/Git/Git-example-2 (feature/ask-me)
$ git branch --set-upstream-to=origin/feature/ask-me feature/ask-me
branch 'feature/ask-me' set up to track 'origin/feature/ask-me'.
```

+ To create a new branch named feature/conflicts and then switch branch,

```
userJay30@ASUS-B1400CBNGW MINGW64 /d/workspace/tutorial projects/Git/Git-example-2 (feature/ask-me)
$ git checkout -b feature/conflicts
Switched to a new branch 'feature/conflicts'
```

+ open `MyAwesomeApp/Program.cs` with notepad 

```
userJay30@ASUS-B1400CBNGW MINGW64 /d/workspace/tutorial projects/Git/Git-example-2 (feature/conflicts)
$ notepad "MyAwesomeApp/Program.cs"
```

Then replace the first line

```
Console.WriteLine("What is my name?");
```

to 

```
Console.WriteLine("What is my name?");
```

And close it.

+ Look at status again,
  
```
userJay30@ASUS-B1400CBNGW MINGW64 /d/workspace/tutorial projects/Git/Git-example-2 (feature/conflicts)
$ git status
On branch feature/conflicts
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   MyAwesomeApp/Program.cs

no
changes added to commit (use "git add" and/or "git commit -a")
```

+ To track file changes and staged them,
  
```
userJay30@ASUS-B1400CBNGW MINGW64 /d/workspace/tutorial projects/Git/Git-example-2 (feature/conflicts)
$ git add .
```

+ After tracking these files, look at status again.

```
userJay30@ASUS-B1400CBNGW MINGW64 /d/workspace/tutorial projects/Git/Git-example-2 (feature/conflicts)
$ git status
On branch feature/conflicts
Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        modified:   MyAwesomeApp/Program.cs

```

+ To commit these staged but uncommited files,

```
userJay30@ASUS-B1400CBNGW MINGW64 /d/workspace/tutorial projects/Git/Git-example-2 (feature/conflicts)
$ git commit -m "Part 2: try to make conflicts to demo"
[feature/conflicts e584d97] Part 2: try to make conflicts to demo
 1 file changed, 1 insertion(+), 1 deletion(-)

```

+ After committing, look at status again,

```
userJay30@ASUS-B1400CBNGW MINGW64 /d/workspace/tutorial projects/Git/Git-example-2 (feature/conflicts)
$ git status
On branch feature/conflicts
nothing to commit, working tree clean
```

+ After committing, look at log in one line again (fifth times),

````
userJay30@ASUS-B1400CBNGW MINGW64 /d/workspace/tutorial projects/Git/Git-example-2 (feature/conflicts)
$ git log --oneline
e584d97 (HEAD -> feature/conflicts) Part 2: try to make conflicts to demo
7518cf4 (tag: v1.0.0, origin/feature/ask-me, feature/ask-me) Part 1: prompt user to enter the input
53a09ef (tag: v0.0.0, origin/master, origin/HEAD, master) Part 0:Create empty console project in the solution
```

+ To create a new tag named `v2.0.0`,

```
userJay30@ASUS-B1400CBNGW MINGW64 /d/workspace/tutorial projects/Git/Git-example-2 (feature/conflicts)
$ git tag v2.0.0
```

+ After creating the new tag named `v2.0.0`, look at created tags.

```
userJay30@ASUS-B1400CBNGW MINGW64 /d/workspace/tutorial projects/Git/Git-example-2 (feature/conflicts)
$ git tag
v0.0.0
v1.0.0
v2.0.0
```

+ To push the commit to remote repo in GitLab atomically,

```
userJay30@ASUS-B1400CBNGW MINGW64 /d/workspace/tutorial projects/Git/Git-example-2 (feature/conflicts)
$ git push --atomic origin feature/conflicts
Enumerating objects: 7, done.
Counting objects: 100% (7/7), done.
Delta compression using up to 12 threads
Compressing objects: 100% (3/3), done.
Writing objects: 100% (4/4), 470 bytes | 36.00 KiB/s, done.
Total 4 (delta 0), reused 0 (delta 0), pack-reused 0 (from 0)
remote:
remote: To create a merge request for feature/conflicts, visit:
remote:   https://gitlab.com/codelover30/git-example-2/-/merge_requests/new?merge_request%5Bsource_branch%5D=feature%2Fconflicts
remote:
To https://gitlab.com/codelover30/git-example-2.git
 * [new branch]      feature/conflicts -> feature/conflicts
```

+ After pushing, look at status again.

```
userJay30@ASUS-B1400CBNGW MINGW64 /d/workspace/tutorial projects/Git/Git-example-2 (feature/conflicts)
$ git status
On branch feature/conflicts
nothing to commit, working tree clean
```

+ After pushing, look at log in one line again (sixth time).
 
```
userJay30@ASUS-B1400CBNGW MINGW64 /d/workspace/tutorial projects/Git/Git-example-2 (feature/conflicts)
$ git log --oneline
e584d97 (HEAD -> feature/conflicts, tag: v2.0.0, origin/feature/conflicts) Part 2: try to make conflicts to demo
7518cf4 (tag: v1.0.0, origin/feature/ask-me, feature/ask-me) Part 1: prompt user to enter the input
53a09ef (tag: v0.0.0, origin/master, origin/HEAD, master) Part 0:Create empty console project in the solution
```

+ To merge from `feature/conflicts` branch to `master` branch,

it is need to switch branch to `master` branch.

```
userJay30@ASUS-B1400CBNGW MINGW64 /d/workspace/tutorial projects/Git/Git-example-2 (feature/conflicts)
$ git checkout master
Switched to branch 'master'
```

Then use `git merge` with `--no-ff` option to merge from current working branch (here is `master` branch) to specific branch (here is `feature/conflicts` branch)

```
userJay30@ASUS-B1400CBNGW MINGW64 /d/workspace/tutorial projects/Git/Git-example-2 (master)
$ git merge --no-ff feature/conflicts
hint: Waiting for your editor to close the file...
```

Then Git opens `.git/MERGE_MSG` to prompt us to fill the merge message since we haven't write it yet.

After that, you will see

```
userJay30@ASUS-B1400CBNGW MINGW64 /d/workspace/tutorial projects/Git/Git-example-2 (master)
$ git merge --no-ff feature/conflicts
Merge made by the 'ort' strategy.
 MyAwesomeApp/Program.cs | 4 +++-
 1 file changed, 3 insertions(+), 1 deletion(-)
```

+ After merging, look at status,

```
userJay30@ASUS-B1400CBNGW MINGW64 /d/workspace/tutorial projects/Git/Git-example-2 (master)
$ git status
On branch master
nothing to commit, working tree clean
```

+ After merging, look at log in one line (seventh time)

```
userJay30@ASUS-B1400CBNGW MINGW64 /d/workspace/tutorial projects/Git/Git-example-2 (master)
$ git log --oneline
8ca3b4b (HEAD -> master) Merge branch 'feature/conflicts'
e584d97 (tag: v2.0.0, origin/feature/conflicts, feature/conflicts) Part 2: try to make conflicts to demo
7518cf4 (tag: v1.0.0, origin/feature/ask-me, feature/ask-me) Part 1: prompt user to enter the input
53a09ef (tag: v0.0.0, origin/master, origin/HEAD) Part 0:Create empty console project in the solution
```

we will see `(HEAD -> master)` indicating there is a merge from other branch to the `master` branch.

and `Merge branch 'feature/conflicts'` indicating there is a merge from `feature/conflicts` branch,

combining them together, we will know that there is a merge from `feature/conflicts` branch to `master` branch.

+ Then we set the global configuration `color.ui` to true, which echos the output with multiple color.

```
userJay30@ASUS-B1400CBNGW MINGW64 /d/workspace/tutorial projects/Git/Git-example-2 (master)
$ git config --global color.ui true
```

+ After that, we can see that Git prints the log with multiple color.

```
userJay30@ASUS-B1400CBNGW MINGW64 /d/workspace/tutorial projects/Git/Git-example-2 (master)
$ git log --oneline
8ca3b4b (HEAD -> master) Merge branch 'feature/conflicts'
e584d97 (tag: v2.0.0, origin/feature/conflicts, feature/conflicts) Part 2: try to make conflicts to demo
7518cf4 (tag: v1.0.0, origin/feature/ask-me, feature/ask-me) Part 1: prompt user to enter the input
53a09ef (tag: v0.0.0, origin/master, origin/HEAD) Part 0:Create empty console project in the solution
```

<img width="595" height="107" alt="image" src="https://github.com/user-attachments/assets/d92075a3-826f-4e20-abb6-d155b79f0584" />

+ Then we set the global configuration `color.ui` to false, which echos the output without multiple color.

```
userJay30@ASUS-B1400CBNGW MINGW64 /d/workspace/tutorial projects/Git/Git-example-2 (master)
$ git config --global color.ui false
```

+ After that, we can see that Git prints the log without multiple color.

```
userJay30@ASUS-B1400CBNGW MINGW64 /d/workspace/tutorial projects/Git/Git-example-2 (master)
$ git log --oneline
8ca3b4b (HEAD -> master) Merge branch 'feature/conflicts'
e584d97 (tag: v2.0.0, origin/feature/conflicts, feature/conflicts) Part 2: try to make conflicts to demo
7518cf4 (tag: v1.0.0, origin/feature/ask-me, feature/ask-me) Part 1: prompt user to enter the input
53a09ef (tag: v0.0.0, origin/master, origin/HEAD) Part 0:Create empty console project in the solution
```

<img width="575" height="106" alt="image" src="https://github.com/user-attachments/assets/25115e26-3b49-49ee-8a75-cc677deebd90" />
