# Terminal Cheatsheet

# Contents

1. [Terminal Commands](#terminal-commands)
2. [GitHub Commands](#github-commands)
3. [GitHub Collaborations](#github-collaborations)
4. [GitHub Branches](#github-branches)
    - [Merging](#merging)
    - [Issue Management](#issue-management)
3. [Extra](#extra)

## **Terminal Commands**

 ### ***Changing directory***

```
cd [Destination]
```
| Destination | Syntax |
| ----------- | ----------- |
| Home | [leave blank] |
| Specific directory e.g documents| `~/Documents` |
| Parent directory| `..`|
| Current directory| `.` |
| Previous directory| `-` |

### ***File Modification***

```
[command] <filename>
```
| Command | Syntax | Flags |
| ----------- | ----------- | --------|
| Create file | `touch` |
| Open file or directory | `open` |
| Remove file | `rm` | `-r` (recursively) `-rf` (+forcefully)  |

*Etiquette*

| Naming Style | Example |
|---|---|
|snake | `my_directory`|
|camel | `myDirectory` |
|passcode| `MyDirectory`|
|kebab (taboo)| `my-directory`|

### ***Moving and Copying Files***

```
mv <filename> <directory/new_filename>
cp <filename> <directory/new_filename>
```

### ***Miscellaneous*** 

| Command | Syntax | Flags |
| ----------- | ----------- |----------- |
| List files | `ls` | `-a` (all hidden) `-l` (detailed?)|
| Clear terminal | `clear` | |


## **Github Commands**

### ***Create Local Repository***
```
git init
```
### ***Add/Remove File to be Committed***
```
git add <filename or directory> // or gaa
git rm --cached <filename>
```
### ***Commit Files***
```
git commit -m "[enter message]"
git commit --amend      //ammends most recent
```
### ***Status and Log***
```
git status / gst
git log
```
Flag for log: --raw  (can see which files were added or modified)

### ***Setting Up Remote***
```
git remote add origin [SSH URL]
```

origin is the alias for the SSH URL

### ***Downloading Repository***
```
git clone [SSH URL]
```
### ***Setting Up a Branch***
```
git branch -M main
```
### ***Push and Pull***
```
git push origin main
git pull origin main
```
### ***Configure Username and Email***
```
git config --global user.name "[your name]"
git config --global user.email [your email]
```

### ***Previous Versions***

```
git checkout [ID from git log]
```

### ***Change Branches***

```
git checkout main
```

## **GitHub Collaborations**

Currently,

1. One creates project on laptop
2. Pushes to repository
3. Paired programming using CodeTogether
4. Git clone to get a copy

Now...

1. Create one repository
2. Push code
3. Add people as collaborators
4. Collaborator Git clone
5. Collaborator modifies and Git push
6. Original Git pulls
7. Original modifies and Git push
8. Repeat pull and push

## **GitHub Branches**

Used to stop people from overwriting each others changes to code.

![branches](/images/branches.png)

### How to manage branches

- Main branch is solid, tested and running up online
- **You never work on the main branch!**

To create a developer branch to test and code,

```
git branch develop
git checkout develop


or git checkout -b develop
```

After making changes to the developer branch, you can check it doesn't affect the main by,

`git checkout main`

Use `git log` to check commits.

### Merging

The ideal process is 

- Pull from `main` branch and see if there are changes since your checkout
- Merge the code and solve conflicts on your branch
- Checkout to `main` and merge with `develop`

```
git checkout main
git pull
git checkout develop
git merge main //merges the main branch to develop and see if there are conflicts
git checkout main
git merge develop
```

(Steps 2-4)

![merging](/images/merging_branches.png)

### Solving Merge Conflicts

```java
<<<<<<< HEAD
    //some code
=======
    //other code
>>>>>>> main
```

Head is current branch, `main` is the incoming change when we pull and merge with main. To resolve it, just delete everything but the code you want. Then,

`git status` to check the current issues

`git add .` to now add the files

`git commit -m"fixing merge conflicts"`

### Git Uploading Branches

`git push origin develop`

![develop branch](/images/develop_branch.png)

### Pull Requests

These are used to create requests to merge with another branch. Essentially a border control for anyone who has authority to merge branches together

![flow pull](/images/flow_pull_request.png)

*(Note that you will not be able to merge to main but in this example is just the general flow of what to do if wanting to merge your developing branch with a different branch)*

We change the `main` branch by added new README.md file, `echo "# My readme" >> README.md`

We create a new branch called `readme_changes` and checkout by, `git checkout -b readme_changes`

We now see a `Compare & pull request` icon in GitHub. 

![pull request](/images/pull_request.png)

Check the base and compare branches. Pull request can not go through unless conflicts are solved.

![check base](/images/check_branches.png)

Fill out all details the make it easier for person reviewing the code you have made to request a merge.

You can add a reviewer and in `Files changed` you can add a comment or Start a review.

When issues are fixed and comments are added, the reviewing can click `Finish your review` with rejection or LGTM (looks good to me).

You can not review your own code and approve it. Therefore you must find someone else to approve it and finally `Merge pull request`.

After changes by anyone, make sure to checkout to `main`, `git pull`, checkout to `develop`, `git merge main`.

### Issue Management

- Sometimes known as bug tracking (expected in our group projects)
- Every project of notable size will need a way to track issues/bugs
- Way of managing and resolving issues
- Ways to do this, Trello, Jira, Asana and Basecamp, GitHub issues
- A pull request is proposing a fix to a bug whereas an issue is flagging the problem/bug

**Why track issues/bugs?**

- Can be difficult to manage
- Typically we need:
    * Somewhere to store issues
    * A way to assign issues to team members
    * Prioritise issues in some manner

**Git Issues**

- issues can be used on a repository to tag people in the message, assign yourself or other people to receive email
- add label with different tags such as documentation, bugs, etc (able to make new labels too)
- you can close the issue after when it is completed
- you can link an issue to a branch or a pull request
- Trello has power ups that allow for linking with GitHub to link issues to tickets on Trello

## **Extra**

### ***Check SSH Key***
```
ssh git@github.com
```
### ***SSH Setup***

Generate SSH Key using instructions from Github and then copy public SSH Key to Github account