Knowledge Base
========================

Git
-------------------

- Git fix weird untracked file (can’t reset file): 
`git ls-files -m | xargs -I {} git update-index --assume-unchanged {}`

_______________________________________________

- Delete old git branch autocomplete
`git fetch --prune --all`

_______________________________________________
- Rename branch
1. If you are on the branch you want to rename:
	`git branch -m new-name`
	

If you are on a different branch:	
	`git branch -m old-name new-name`

2. `git push origin :old-name new-name`
3. `git push origin -u new-name`

________________________________________________
- Squash x commits into one commit
	`git squash`
	Change `pick` to `s`
	edit commit messages

________________________________________________
- Squash commits into one commit

- Create new branch
`git checkout --orphan new-master master`

- Add message
`git commit -m "init"`

- Overwrite the old branch
`git branch -M new-master master`

________________________________________________

- Rebase
	`git pull development`
	`git checkout branch`
	`git rebase development`
	`git push —force`

________________________________________________

- Reset back to remote branch
`git reset --hard <branch>`

________________________________________________

- Set git user for folder
`git config <setting-name> <setting-value>`

________________________________________________
https://help.github.com/articles/changing-a-commit-message/

- Modify last commit message: 
`git commit --amend`

________________________________________________
https://help.github.com/articles/about-git-rebase/

- Modify last 3 commit messages:
`git rebase -i HEAD~3`

Change to REWORD
```
pick e499d89 Delete CNAME
reword 0c39034 Better README
reword f7fde4a Change the commit message but push the same commit.
```

`git push --force`

________________________________________________

- Get current git hash
`git log -1 --format="%H"`

_______________________________________________

- git squash

`git rebase -i HEAD~4`
change pick —> s
_______________________________________________

- Save changes without committing
`git stash`
`git stash apply`

- Delete all stash
`git stash clear`

- Save
`git stash save -m "my_message"`

_______________________________________________

Docker
-------------------

- Clean docker completely:
`docker system prune -a`
________________________________________________

- Clear container logs
`echo "" > $(docker inspect --format='{{.LogPath}}' container-name)`

________________________________________________
- Remove volumes

`docker-compose down -v`

________________________________________________

- Remove stale container processes

`docker rm -f $(docker ps -qa)`
________________________________________________

- Remove stale container processes

`docker image rm $(docker image ls) -f`
________________________________________________
- Format docker 

`docker ps --format "table {{.Names}} \t\t {{.Status}}"`
`docker ps --format "table {{.Status}} \t\t {{.Names}}" | sort -k 2 -n`

_______________________________________________

- Get docker image SHA:

`docker inspect --format='{{index .RepoDigests 0}}' $IMAGE`

_______________________________________________

- Generate MAC Address:

`docker run -d --mac-address="02:42:$(openssl rand -hex 4 | sed 's/\(..\)/\1:/g; s/.$//')"`

_______________________________________________

Vim
-------------------

- GO START LINE: `0`
- GO END LINE: `$`
- INSERT: `i`
- DELETE LINE: `dd`
- SAVE: `ESC :wq` 
- QUIT: `ESC :q`
_______________________________________________

Bash
-------------------

Tests: 
- Equals: `-eq`
- Not equals: `-ne`
- Check empty string: `-z`
- Less than: `-lt`
- Greater than: `-gt`
- Less than or equal: `-le`
- Greater than or equal `-ge`
_______________________________________________

Commands
-----------
- List files `ls`
- Go to diretory `cd`
- Print current directory `pwd`
- Open file `open`
- Get description of file `file`
- Current directory `.`
- Create directory `mkdir`
- Move file `mv`
- Copy file `cp`
- Copy dir `cp -r`
- Print file `cat`
- Follow file `tail -f`
- File editors
	- `nano`
	- `vi`
	- `vim`
_______________________________________________

Files
-----------
`ls -l`
`-/---/---/---`
`file/dir/symlink -- OWNER/GROUP/OTHER`


_______________________________________________

Permissions
-----------
- `chmod`
- `chown`
- `chgrp`
<br>
- User `chmod u=rwx`
- Group `chmod g=rwx`
- Other `chmod o=rwx`
<br>
- Make file executable for everyone `chmod +x`

_______________________________________________

Variables
-----------

- Set variable
`myVariable=test`
`echo $test`
`echo ${test}`
<br>
- Unset variable
`unset myVariable`
<br>
- Save command as variable
`myVariable=ls`
`${ls}`
_______________________________________________

- Important env variables
`$USER`
`$HOME`
`$PATH`
_______________________________________________

- command substitution
`myVariable=$(ls -l)`
_______________________________________________

- grep
`grep myString`
<br>

- Ignore case sensitive
`grep -i myString`
<br>

- Exclude grep 
`grep -v myString`

_______________________________________________

- Get input
`read myVariable`
`read -p "please type input: " myVariable`
`read -s myPassword`


Linux
-------------------

- Get filesystem access:

`mount -o remount,rw /;`
_______________________________________________

- Bring process to foreground 
`fg`

_______________________________________________

- Get RPi model
`cat /proc/device-tree/model`

_______________________________________________

- Modify bash profile
`vi ~/.bash_profile`

<br>

- Reload bash profile
`. ~/.bash_profile`

_______________________________________________

- Get size of terminal
`stty size`

_______________________________________________

- Generate SSH key
`ssh-keygen -t rsa -C “your.email@email.com” -b 4096`

- View key
`cat .ssh/id_rsa.pub`

_______________________________________________

- Create file with 10mb
`dd if=/dev/zero of=/path/my_file bs=10485760 count=1`

_______________________________________________

Terminal
-------------------
`Ctrl+A`	Move cursor to the beginning of the command line.
`Ctrl+C`	End a running program and return the prompt, see Chapter 4.
`Ctrl+D`	Log out of the current shell session, equal to typing exit or logout.
`Ctrl+E`	Move cursor to the end of the command line.
`Ctrl+H`	Generate backspace character.
`Ctrl+L`	Clear terminal.
`Ctrl+R`	Search command history, see Section 3.3.3.4.
`Ctrl+Z`	Suspend a program, see Chapter 4.