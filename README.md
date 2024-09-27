# Personal Git Wiki (commands and notes for personal use)

1. [Git Fundamentals](#id1)
2. [Git Commands](#id2)<br>
2.1 [Git Config - Get and set repository or global options](#id2.1)<br>
2.2 [Git Essential Commands](#id2.2)<br>
2.3 [Git Repository Management](#id2.3)<br>
2.4 [Git File Management](#id2.4)<br>
2.5 [Git Commit Management](#id2.5)<br>

<a name="id1"> </a>
## Git Fundamentals

### Main or Master
When you create a git repository, the default brands are Main or Master, often the main ones.

### Git states
  - Modified: 
    The file has changed but there is no confirmation to send.
  - Staged:
    The file is modified and marked as ready.
  - Committed:
    The file is saved in the repository.

### Head
The pointer that references the current point in the commit history

### .gitignore
The file indicates that Git should ignore certain file names from being tracked in the repository. <br> 
Also is possible to create a .gitignore global file in the home user directory  -> "~/.gitignore_global and write" -> "git config --global core.excludesfile" ~/.gitignore_global in the terminal
> Files that should be ignored
>
> Credentials or .env files
>
> ide configuration files
>
> systems files like .DS_Store
>
> log files
>
> Static or build files like /dist or /build directory

<a name="id2"> </a>
## Git Commands

<a name="id2.1"> </a>
### Git Config - Get and set repository or global options
> add --system, --global or local to a git config command to specify where the configuration will be established
> 
> --system -> The configuration will be applied for the entire systems and repository including all the users
> 
> --global -> The configuration will be applied for the current user"
> 
> --local -> The configuration will be applied for the current repository"
- Show current git configuration "add --system, --global or --local to filter the configuration you want to see"
```
git config --list
```
- Associate username and email to commits in your device
```
git config  user.name "<your name>"
git config  user.email "<your email>"
```
- Set git default editor
```
git config --global core.editor "editor name"
```

<a name="id2.2"> </a>
### Git Essential Commands
- Show installed git version
```
git version
```
- Show a command description
```
git <verb> --help
```

<a name="id2.3"> </a>
### Git Repository Management
- Initialize a new repository in the folder located
```
git init
```
- Show repository status
```
git status
git status -s # Shows the output of the command in a simplified form.
```

<a name="id2.4"> </a>
### Git File Management
- Track a file and add it to the staging area
```
git add <file>
git add -A #add all the files that have been modified in the repository to the staging area
```
- Stop file tracking and remove it from the staging area
```
git reset <file>
```
- Undo a modified file
```
git restore <file>
git checkout -- <file>
```
- Delete all new untracked files (not added to the staging area)
```
git clean -n # shows which files will be deleted
git clean -f # delete the files
```
- Delete a file from the repository but keep it in your file directory
```
git rm --cached <file>
```

<a name="id2.5"> </a>
### Git Commit Management
- Creates a commit in the repository history with the current state of the files added to the staging area
```
git commit # This will open the previously configured editor to add the message
git commit -m "title" -m "description" # Write the commit title and description directly using the terminal
```

- Add the files to the staging area and commit simultaneously
```
git commit -a -m 'message'
```

- Move HEAD to a previous commit
```
git reset --soft HEAD~1 # The files committed in the last commit will be moved to the staging area
git reset HEAD~1 # The files committed will remain but as unstaged
git reset --hard HEAD~1 # The files committed will lose any changes made and new files will be removed
```

- Add new changes and/or change the message of the last commit
```
git commit --amend -m "message"
```












  

