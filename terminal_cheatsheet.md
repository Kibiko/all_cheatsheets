# Terminal Cheatsheet

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
git add <filename or directory>
git rm --cached <filename>
```
### ***Commit Files***
```
git commit -m "[enter message]"
```
### ***Status and Log***
```
git status
git log
```
Flag for log: --raw  (can see which files were added or modified)

### ***Setting Up Remote***
```
git remote add origin [SSH URL]
```
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
## **Extra**

### ***Check SSH Key***
```
ssh git@github.com
```
