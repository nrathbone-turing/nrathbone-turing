# Ruby
## ruby ruby ruby

### Git Repo order of operations notes

[Handy Atlassian documentation page about git](https://www.atlassian.com/git/tutorials/setting-up-a-repository/git-init)  

1. `git init` - creates a `.git` subdirectory in the current directory for git
- only necessary when creating own new repository, when cloning a forked repo, git will automatically be initialized, but generally we always want to make sure git is up and running before developing either way
    - `.git init <directory>` - creates an empty Git repository in the specified directory. Running this command will create a new subdirectory called ＜directory＞ containing nothing but the .git subdirectory  
2. `git clone` - clones a local or remote repository; if remote make sure to fork the repo or the branch first before cloning
    - `.git clone git@github.com:nrathbone-turing/nrathbone-turing.git` - example of how to create a local copy of a central repository stored on a server accessible at {SSH KEY}
    - `cd <directory>` or `cd nrathbone-turing.git` changes the directory to the new one you just made by cloning
    - you can set the default branch after cding to the new directory with `git push -u origin main` - do this
    - `git clone <repo> <directory>` - clones the repository located at `＜repo＞` into the folder called `~＜directory＞!` on the local machine.
    - `git clone --branch`  
4. `git remote -v` - shows you the current origin location both locally and remotely
    - example would look like this as the output in console:
    ```origin	git@github.com:nrathbone-turing/nrathbone-turing.git (fetch)
    origin	git@github.com:nrathbone-turing/nrathbone-turing.git (push)```  
5. `git add` - adds the changes you've made to a staging area before you make the changes apply to the file or directory; once you have a project up and running you can use `git add` to add new files or to record changes to existing files. **NOTE:** Git doesn’t differentiate between staging changes in new files vs. changes in files that have already been added to the repository
    - `git add <file>`
    - `git add <directory>`  
6. `git status` - Shows you which changes have been staged, which haven’t, and which files aren’t being tracked by Git. Note that this command's output does not show you any information regarding the committed project history; to do this, you need to use `git log` instead.  
7. `git commit <file> "Commit message"` -- acts as a snapshot that acts as a way to restore previous versions if needed where you can roll back (revert) to a previous state
    - [here's a good resource](https://cbea.ms/git-commit/)on formatting and ettiquette for commit messages (first letter of first word capital, present tense, short and concise summary)
    - `git commit` - commit the staged snapshot from previous step
    - `git commit -a` - create a snapshot of all made changes in the working directory (that have been captured since initializing git)
    - `git commit -m "Commit message"` - lets you add the commit message directly via console, if you don't have one it will require you to enter one in vs code before continuing  
8. `git push` - uploads your local repository content to a remote repository.; the counterpart to `git fetch`, but whereas *fetching imports commits to local branches*, **pushing exports commits to remote branches** (Remote branches are configured using the git remote command. Pushing has the potential to overwrite changes, caution should be taken when pushing)
    - `git push <remote> <branch>` - pushes the specified branch to , along with all of the necessary commits and internal objects; this also creates a local branch in the destination repository  
