/*
    Staging Area
    Atomic commits     
*/
Git’s collaboration model is based on repository-to-repository interaction. 
Instead of checking a working copy into SVN’s central repository, you push or pull commits from one repository to another.
Developing a project revolves around the basic edit/stage/commit pattern
Git developers have the opportunity to accumulate commits in their local repo.
Staging area is a buffer between the working directory and the project history.
lets developers work in an isolated environment, deferring integration until they’re at a convenient break point.
SVN commit consists of a diff compared to the original file added to the repository. Git, on the other hand, records the entire contents of each file in every commit.


git init
The git init command creates a new Git repository.
Needs to be executed only once.
Common use is to create a central repository.

git init <directory>
Create an empty Git repository in the specified directory

git init --bare <directory>
Initialize an empty Git repository, but omit the working directory. 
Doesn’t have a working directory
Impossible to edit files and commit changes in that repository.
Central repositories should always be created as bare repositories.
All Git work-flows, the central repository is bare, and developers local repositories are non-bare
example
SSH <user>@<host>
cd path/above/repo
git init --base <my-central-project.git>

git clone
Copies an existing Git repository.
something similar to svn checkout
Additionally
full-fledged Git repository
has its own history
is a completely isolated environment from the original repository
automatically creates a remote connection called "origin" pointing back to the original repository.

git clone <repo>
Clone the repository located at <repo> onto the local machine
original repository can be located on the local filesystem
original repository can be located on remote machine accessible via HTTP or SSH

git clone <repo> <directory>
Clone the repository located at <repo> into the folder called <directory> on the local machine.
most common way for users to obtain a development copy
generally a one-time operation

git config
lets you configure your Git installation (or an individual repository) from the command line.
Define everything from user info, preferences, behavior of a repository
All configuration options are stored in plaintext files, so the git config command is really just a convenient command-line interface
<repo>/.git/config – Repository-specific settings.
~/.gitconfig – User-specific settings. This is where options set with the --global flag are stored.
$(prefix)/etc/gitconfig – System-wide settings.

git config user.name <name>
Define author name to be used for all commits in the current repository

git config --global user.name <name>
Define the author name to be used for all commits by the current user.

git config --global user.email <email>
Define the author email to be used for all commits by the current user.

git config --global alias.<alias-name> <git-command>
Create a shortcut for a Git command.

git config --system core.editor <editor>
Define the text editor used by commands like git commit for all users on the current machine


git add
The git add command adds a change in the working directory to the staging area
tells Git that you want to include updates to a particular file in the next commit.
git add doesn't really affect the repository in any significant way—changes are not actually recorded until you run git commit.

git add <file>
Stage all changes in <file> for the next commit.

git add <directory>
Stage all changes in <directory> for the next commit.

git add -p
(Use y to stage the chunk, n to ignore the chunk, s to split it into smaller chunks, e to manually edit the chunk, and q to exit.)

git commit
Commit the staged snapshot
will launch a text editor prompting you for a commit message

git commit -m "<message>"
instead of launching a text editor, use <message> as the commit message

git commit -a
Commit a snapshot of all changes in the working directory
should have been added with git add

git status 
To view the state of the working directory and the staging area.







or create a new repository on the command line
echo # quick-git >> README.md
git init
git add README.md
git commit -m "first commit"
git remote add origin https://github.com/touchchandra/quick-git.git
git push -u origin master

echo # quick-git >> README.md
git init
git add README.md
git commit -m "first commit"
git remote add origin https://github.com/touchchandra/quick-git.git
git push -u origin master

push an existing repository from the command line
git remote add origin https://github.com/touchchandra/quick-git.git
git push -u origin master


