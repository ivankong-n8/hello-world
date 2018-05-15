## 2. Configuring
focus on `.gitconfig` file, we can configure our user name and email into Git
### 2.1 Configuration levels
- tags: `--system`,`--global`, `--local`
- At each level, there is `.gitconfig` file.
- edit by
    - `git config <tag> user.name <username>`
    - `git config <tag> --edit`, which will open the configuration file in a editor.

### 2.2 System Configuration
With tag `--system`, the configuration will be applied to entire machine. That is, they will apply to all repositories and all users on the OS

### 2.3 Global Configuration
use `-- global` tag,  any configurations made at a global level apply to all repositories of **a specific user** of an operating system. Naturally, all the configuration data is stored in the ~/.gitconfig file

### 2.4 Local Configuration
- Any configurations made using the --local tag will apply only to the local repository itself, meaning that different repositories are can be individually customized.
- The configuration data is held in a config file within the .git directory of the repository (ie. in .git/config).
- e.g. `git config --local user.name ivan`

### 2.5 The Hierarchy of Configuration
Configuration works as a hierarchy with system configurations at the bottom and local configurations at the top.

### 2.6 Usage of the Git Config Command
In `.gitconfig` file, information is recorded in `[section]`. The content in each section can be configured by the following skeleton command:

- `git config --<configuration level> <section>.<subsection> "<value>"`
- e.g. `git config --local user.name ivan`

### 2.7 Aliases
`[alias]` is another section in config file, which records the command line equivalent of a shortcut.

e.g. 
``` bash
$ git config --local alias.cf config
$ git cf --local user.name "zy"
```

### 2.8 See More
https://git-scm.com/docs/git-config

## 3. Adding Files to the Git Repository
### 3.1 Staging Files (Git Add)
```bash 
$ git add <file or folder>
$ git add .     # add ALL untracked files to staging area

# Remove files from staging area
$ git rm --cached <file or folder> 
$ git rm -r --cached . # -r means recursive
```

### 3.2 Making Commits (Git Commit)
``` bash
$ git commit # open a editor to imput message
$ git commit -m <message>
$ git commit -a # commit without 'add'
$ git commit -am <message> # Not open editor
```
### 3.3 Interactive Staging Session
``` bash
$ git add -p 
#show more detail about the change
```
Command	Action  | Function 
---- | ----------
y |	Stage the chunk.
n |	Ignore the chunk.
s |	Split the chunk into smaller chunks.
e |	Edit the chunk manually.
q |	Quit the interactive staging session.
g |	Select a chunk to go to.
a |	Stage the Chunk and all others in the file.
d |	Do not stage the chunk or any of the others in the file.
/ |	Search for chunk using regex.
j |	Leave current chunk undecided and move to the next undecided chunk.
J |	Leave current chunk undecided and move to the next chunk.
k |	Leave current chunk undecided and move to the previous undecided chunk.
K |	Leave current chunk undecided and move to the previous chunk.
? |	Print all of the possible commands to the console.

### 3.4 Git Stash
``` Bash
# after making some changes, no matter staged or not

# stash changes
# 'save <message> is optional
$ git stash save <message> 

# use -p tag to 

```
flag | function
-|-
-p | open an interactive session
-u | stash new and unstaged files
-a | stash all, including ignored files

``` Bash
# show the stash list
$ git stash list

# show differences between stash and current working directory
$ git stash show
$ git stash show -p

# <Stash Identifier> looks like stash@{0}. It will be showed in stash list.

# The applied stash will remained in the list
$ git stash apply <Stash Identifier>

# command [pop] will add the stashed changes and remove if from the stash list
$ git stash pop <Stash Identifier>

# [drop] will delete a specific stash. 
$ git stash drop <Stash Identifier>

# clear all the stashes.
$ git stash clear
``` 



