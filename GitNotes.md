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
### 3.4 Git Stash


