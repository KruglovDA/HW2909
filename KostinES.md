# GIT USUAGE MANUAL 
*This present manual will provide you with main git commands and concepts*

## Initial steps 

1. ``` "init" ``` command is used to initialize your git repositary.
Once ``` "init" ``` command is used your files will be tracked.

2. When a file is created it needs to be added to the git repositary with ``` "git add" ``` command.

3. Now its time to make fist save of file state. Use ``` "git commit" ``` to make 1st save point. You may also use ```-m``` option in order to leave "comments and discriptions" of changes made in the file. 

## usefull commands

* ``` "git status" ``` - shows the current state of your Git working directory and staging area.

* ```"git log"``` - provides with a list of changes made is a function of the git log command.

* ```"git checkout"``` - switches between branches or restores working tree files.

## Working with Remotes

1. Initializing a Repository in an Existing Directory ``` "git init" ```
2. Track files and do an initial commit. You can accomplish that with a few git add commands that specify the files you want to track, followed by a git commit:

``` git add *.c ```
``` git add LICENSE```
``` git commit -m 'Initial project version' ```

3. Clone a repository with git clone <url>.

``` git clone https:// ```

4. Incorporates changes from a remote repository into the current branch with ``` git pull ```

5. ``` git-push ``` - Update remote refs along with associated objects

6. Using www.github.com when you hit the 'Create pull request' button, the owner of the project you forked will get a notification that someone is suggesting a change and will link to a page that has all of this information on it.

